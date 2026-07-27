# Policy

Guardrails for any session — human-driven or a scheduled Routine run —
working in this repo. The nightly Routine runs with zero permission prompts,
so these rules are the only thing standing between it and a bad outcome.
Follow them even when nothing here explicitly forbids what you're about to
do: if it feels destructive, external-facing, or irreversible, don't.

## Scope per run

- Read every file in `backlog/**/*.md` (skip `_template.md`).
- Score each item with `status: backlog` or `status: in-progress` whose
  `depends_on` are all `status: done`:

  ```
  score = (impact * confidence * priority) / effort
  score = score * 1.5 if status == in-progress else score
  ```

  The 1.5x continuation bonus is deliberate: this project's own research
  (`backlog/research/ai-monetization-overnight-automation.md`, category
  #15) found that autonomous agents most often fail by producing lots of
  *output* — many half-built things — with zero revenue, not by picking a
  bad idea. Finishing one thing beats starting the next shiny one. A fresh
  `backlog` item should only outscore an `in-progress` item on genuinely
  higher (impact × confidence × priority ÷ effort), not on novelty alone.
- Work the single highest-scoring item. If it's exhausted before the run's
  turn budget runs out, move to the next-highest-scoring unblocked item.
  Don't spread a run thin across many low-value items.
- If nothing scores (empty backlog, everything blocked or done), say so in
  the run report and stop. Do not invent busywork to fill the window.
- Before starting work on the top-scoring item, check for open pull
  requests against this repo. `main` only reflects merged work — a prior
  run's PR can already have finished (or gone further on) the very item
  this run is about to pick, while still sitting unmerged. If an open PR
  already covers the item to a further-along or better-verified state,
  don't duplicate it: pick the next-highest-scoring genuinely-unclaimed
  item instead, and flag the overlap in the run report so a human can
  reconcile the open PRs. (Added 2026-07-25 after a run's first attempt
  duplicated, less accurately, work already sitting in an unmerged PR —
  see that day's report.)

## Hard limits

- Never commit secrets, API keys, tokens, or credentials — including ones
  found while researching, e.g. copied from an example config.
- Never push directly to `main`. Only push to `claude/`-prefixed branches
  and open a pull request. This repo intentionally does not enable
  "Allow unrestricted branch pushes" on its Routine — keep it that way.
- Never touch production systems, paid third-party services, or anything
  that spends real money, sends real email/messages, or is visible to
  anyone other than the user, without it being the explicit, stated
  objective of the backlog item.
- Never delete a project file. Move completed work to `done/<category>/`
  instead (`git mv`, so history is preserved).
- If a backlog item's own instructions conflict with this file, this file
  wins.

## Every run must, before finishing

1. Update the picked item's `Checkpoint` section (`Latest state` /
   `Next steps` / append one line to `Learnings`) and its `status` /
   `updated` fields. This is the only memory the next run has — a run that
   makes progress but doesn't checkpoint it has made no progress.
2. If the item is fully done, set `status: done` and `git mv` the file into
   `done/<category>/`.
3. Commit on a `claude/`-prefixed branch and open a PR against `main`.
4. Write `reports/<YYYY-MM-DD>.md` per the format in `CLAUDE.md`.
