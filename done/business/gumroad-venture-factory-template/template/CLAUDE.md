# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working
with code in this repository.

## What this repo is

Not a software project by default — it's the backlog and the operating
memory for an autonomous system: a nightly Cloud Routine reads it, does
the highest-value work it can find, and writes its progress back as
files, since a Routine gets a stateless fresh clone every run with no
memory of previous runs. If a picked backlog item happens to be a coding
task, that item's own project may involve running a build/test suite
*inside its own subdirectory or external repo* — that's scoped to the
item, not to this repo.

Read `README.md` for the one-time manual setup (GitHub push, `/schedule`).
Read `POLICY.md` for the guardrails every run — human or routine — must
follow. Read `ROUTINE_PROMPT.md` for the exact prompt the routine runs.

## Backlog schema

Every project is one Markdown file with YAML frontmatter, under
`backlog/<category>/<id>.md`. The six categories below are a starting
point — rename, add, or remove them to fit what you actually work on, as
long as `CLAUDE.md`, `POLICY.md`, and every project file's `category`
field agree with whatever directories actually exist under `backlog/`.
Start from `backlog/_template.md` when adding a new one; see
`backlog/research/example-first-project.md` for a filled-in example.

| Category | Use for |
|---|---|
| `research` | Open-ended investigation, surveys, competitive scans |
| `coding` | Software you want built, fixed, or shipped |
| `business` | Products, offers, anything aimed at revenue |
| `documentation` | Writeups, references, internal docs |
| `writing` | Long-form content not tied to a product |
| `investments` | Research and tracking for your own money decisions |

Frontmatter fields:

| Field | Meaning |
|---|---|
| `id` | kebab-case, unique, matches nothing else in the repo — used as the filename stem |
| `category` | must match the directory it lives in |
| `status` | `backlog` / `in-progress` / `blocked` / `done` |
| `impact` | 1-5, value if this is completed well |
| `confidence` | 1-5, likelihood of success at the estimated effort |
| `priority` | 1-5, strategic importance to you right now |
| `effort` | 1-5, estimated compute/turns/time to make meaningful progress |
| `depends_on` | list of other `id`s that must be `status: done` first |
| `created` / `updated` | ISO dates |

Body has three sections: `Objective`, `Context`, and `Checkpoint`
(`Latest state` / `Next steps` / `Learnings`). `Latest state` and
`Next steps` are overwritten each run to reflect current reality — they
are not a log. `Learnings` is append-only, one line per run.

## ROI scoring

```
score = (impact * confidence * priority) / effort
score = score * 1.5 if status == in-progress else score
```

Computed fresh each run from the frontmatter above — nothing is
pre-computed or cached. An item is eligible only if every id in
`depends_on` is `status: done`. The routine (per `POLICY.md`) works the
single highest-scoring eligible item to a good stopping point rather than
spreading effort across many.

The 1.5x bonus for `in-progress` items is a deliberate finish-over-novelty
bias: an unattended agent's most common failure mode isn't picking a bad
idea, it's producing lots of *output* — many half-built things — instead
of finishing anything all the way to a usable result. Weight your own
`impact` / `confidence` / `priority` / `effort` estimates honestly rather
than inflating a fresh idea's numbers just to make it outscore something
already underway; a fresh `backlog` item should only outscore an
`in-progress` item on genuinely higher expected value, not on novelty
alone. See `POLICY.md` for the guardrails this bias operates under.

## Completed work

When an item reaches `status: done`, `git mv` it from
`backlog/<category>/` to `done/<category>/` (preserves history via git
rename detection) in the same commit that finishes it. Never delete a
project file outright.

## Reports

Each run appends a file to `reports/<YYYY-MM-DD>.md` (one file per calendar
day the routine runs) covering: tasks touched, files changed, ideas
discovered, open questions, and suggested next actions for you. This is
the "what happened while you were away" surface — write it for a human
skimming it once, not for another session to parse.

## Branch and PR policy

The routine can only push `claude/`-prefixed branches (unrestricted push
is intentionally left disabled — see `README.md` step 3) and always opens
a PR against `main` rather than pushing directly. A human merges.

## Make this yours

This file, `POLICY.md`, and `ROUTINE_PROMPT.md` are meant to be edited —
they're a starting point, not a fixed spec. Things worth customizing early:

- **Categories** (above) — match them to how you actually think about
  your own work, not this template's defaults.
- **Guardrails in `POLICY.md`** — the ones shipped with this template are
  deliberately conservative (no real money, no messages to third parties,
  no production systems) so a fresh setup can't do damage before you've
  seen it run a few times. Loosen them deliberately, in writing, once
  you've built trust in a given category of task — don't just work around
  them in a one-off prompt.
- **A "Deferred to v2" section, if useful** — a place to note ideas you've
  deliberately decided not to build yet (infrastructure, not backlog
  content), so a future run doesn't get confused into thinking it's an
  oversight rather than a decision.
