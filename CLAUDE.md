# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

Not a software project — there is nothing to build, lint, or test here.
This repo *is* the backlog and the operating memory for an autonomous
system: a nightly Cloud Routine reads it, does the highest-value work it
can find, and writes its progress back as files, since a Routine gets a
stateless fresh clone every run with no memory of previous runs. If a
picked backlog item happens to be a coding task, that item's own project
may involve running a build/test suite *inside its own subdirectory or
external repo* — that's scoped to the item, not to this repo.

Read `README.md` for the one-time manual setup (GitHub push, `/schedule`).
Read `POLICY.md` for the guardrails every run — human or routine — must
follow. Read `ROUTINE_PROMPT.md` for the exact prompt the routine runs.

## Backlog schema

Every project is one Markdown file with YAML frontmatter, under
`backlog/<category>/<id>.md`. Categories: `research`, `coding`, `business`,
`documentation`, `writing`, `investments` — matching the top-level
directories. Start from `backlog/_template.md` when adding a new one; see
`backlog/research/example-competitor-scan.md` for a filled-in example.

Frontmatter fields:

| Field | Meaning |
|---|---|
| `id` | kebab-case, unique, matches nothing else in the repo — used as the filename stem |
| `category` | one of the six above; must match the directory it lives in |
| `status` | `backlog` / `in-progress` / `blocked` / `done` |
| `impact` | 1-5, value if this is completed well |
| `confidence` | 1-5, likelihood of success at the estimated effort |
| `priority` | 1-5, strategic importance to the user right now |
| `effort` | 1-5, estimated compute/turns/time to make meaningful progress |
| `depends_on` | list of other `id`s that must be `status: done` first |
| `created` / `updated` | ISO dates |

Body has three sections: `Objective`, `Context`, and `Checkpoint`
(`Latest state` / `Next steps` / `Learnings`). `Latest state` and
`Next steps` are overwritten each run to reflect current reality — they are
not a log. `Learnings` is append-only, one line per run.

## ROI scoring

```
score = (impact * confidence * priority) / effort
```

Computed fresh each run from the frontmatter above — nothing is
pre-computed or cached. An item is eligible only if every id in
`depends_on` is `status: done`. The routine (per `POLICY.md`) works the
single highest-scoring eligible item to a good stopping point rather than
spreading effort across many.

## Completed work

When an item reaches `status: done`, `git mv` it from
`backlog/<category>/` to `done/<category>/` (preserves history via git
rename detection) in the same commit that finishes it. Never delete a
project file outright.

## Reports

Each run appends a file to `reports/<YYYY-MM-DD>.md` (one file per calendar
day the routine runs) covering: tasks touched, files changed, ideas
discovered, open questions, and suggested next actions for the user. This
is the "what happened while you were away" surface — write it for a human
skimming it once, not for another session to parse.

## Branch and PR policy

The routine can only push `claude/`-prefixed branches (unrestricted push is
intentionally left disabled — see `README.md` step 3) and always opens a PR
against `main` rather than pushing directly. A human merges.

## Deferred to v2 (do not build unless asked)

- Idle detection / a local watcher daemon that triggers runs opportunistically via the routine's `/fire` API endpoint, instead of only the nightly schedule.
- Any form of quota/usage polling — there is currently no reliable programmatic way to read remaining rate-limit quota (`/usage` is interactive-only; OpenTelemetry gives historical cost, not remaining budget; parsing `~/.claude/projects/*.jsonl` is explicitly documented by Anthropic as an unstable internal format). v1's only "don't waste downtime" mechanism is the schedule itself.
- Automated ROI-formula tuning from observed outcomes.
- The investment/earnings-research and business-opportunity-scanning *pipelines* described in the original project brief — those are backlog *content* (individual project files a run can pick up), not infrastructure to build.
