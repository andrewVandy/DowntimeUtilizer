# Backlog Autopilot — Buyer's Guide

A guide to setting up your own autonomous "unused Claude Code quota →
shipped work" pipeline, using the template repo included with this
purchase. Read this once end-to-end before touching the template — it'll
save you from a couple of mistakes people make with the raw files alone.

## What you're actually building

If you have a Claude subscription, you're very likely not using all of
your available quota every day — evenings, weekends, whole days you don't
open Claude Code at all. That's compute you already paid for, sitting
idle. This template turns it into a standing, autonomous worker: a
scheduled Cloud Routine that wakes up on a timer, reads a backlog of
projects you've written down, works on the single most valuable one it
can find, and reports back — all without you being at the keyboard.

It is **not** a chatbot, a cron job that runs a fixed script, or a
"set and forget, trust it blindly" system. It's closer to a very
diligent, very literal junior employee who only ever does exactly what's
written down, checkpoints their work obsessively because they know
they'll have amnesia by tomorrow, and always leaves their work for you to
review before it becomes permanent.

## The four ideas that make this work

### 1. Files are the memory, not a database

A Cloud Routine gets a fresh, stateless clone of your repo every single
run. It has no memory of yesterday's run except what's written down in
the files themselves. This sounds like a limitation, but it's the whole
trick: it forces every run to leave the repo in a state a *stranger*
could pick up cold. That discipline is what makes the system reliable
across weeks and months without drifting into an undocumented mess only
one session ever understood.

### 2. One scoring formula, applied honestly

```
score = (impact * confidence * priority) / effort
score = score * 1.5 if status == in-progress else score
```

Four numbers, 1-5 each, that you (or a routine run) estimate honestly for
every project. The formula itself is almost incidental — what matters is
that it forces a *reason* for what gets worked on next, instead of
"whatever's newest" or "whatever's most fun to think about." The 1.5x
bonus for `in-progress` items is the single most important tuning
decision in this whole system: without it, an autonomous agent will
happily start twenty different projects and finish none of them, because
starting something new always *looks* higher-value than grinding out the
unglamorous last 20% of something already underway. The bonus corrects
for that bias on purpose.

### 3. Checkpoints, not logs

Every project file has a `Checkpoint` section with three parts:
`Latest state` (overwritten each run — where things stand *right now*),
`Next steps` (overwritten each run — what to do *next*, in order), and
`Learnings` (append-only — one line per run, the only part that
accumulates). Most people's instinct is to make this a running log of
everything that happened. Resist that. A log is for humans reconstructing
history; a checkpoint is for a stateless agent that needs to know *only*
where things stand right now and what to do next. If you want history,
that's what `git log` and your PR descriptions are for.

### 4. A human merges

The routine can only push to `claude/`-prefixed branches and always opens
a pull request against `main` — it never pushes directly. This is the
single guardrail that matters most. It costs you a few minutes of review
per run. In exchange, nothing an unattended agent decides becomes
permanent without you seeing it first. Don't turn this off, even once
you trust the system — the whole point is that trust shouldn't be
required for safety here.

## Setting it up (the short version)

Full mechanical steps are in the template's own `README.md`. The order
that actually matters:

1. **Seed the backlog with real projects before your first scheduled
   run.** An empty backlog just produces a "nothing to do" report, which
   tells you nothing about whether the system works. Write down 3-5
   things you'd genuinely like done — a mix of easy and ambitious, so you
   can see the scoring formula make a real choice.
2. **Run it once manually ("Run now") before trusting the schedule.**
   Read the PR it opens and the report it writes like you're reviewing a
   new hire's first week, not like you're checking a script's exit code.
3. **Adjust `POLICY.md` based on what you actually see, not what you
   guessed going in.** The shipped guardrails are deliberately
   conservative — no real money, no messages to third parties, nothing
   touching production. Loosen them on purpose, in writing, once you've
   built trust in a specific category of task.

## Adapting the categories and guardrails to your own use case

The six starting categories (`research`, `coding`, `business`,
`documentation`, `writing`, `investments`) are a starting point, not a
spec — rename them to match how you actually think about your own work.
If you're a solo developer, you might want `bugs`, `features`, `refactors`,
`docs`. If you're running a content operation, maybe `drafts`, `research`,
`distribution`, `admin`. Just make sure `CLAUDE.md`, `POLICY.md`, and
every project file's `category` field agree with whatever directories
actually exist under `backlog/` — the routine reads that consistency
literally, it won't infer a category you didn't write down.

The guardrails in `POLICY.md` are the one part of this template you
should read most carefully before your first run, not skim. They're
written to make a fresh, untrusted setup safe by default: no real money
spent, no messages sent to anyone outside you, nothing touching a
production system, unless that's the *explicit, stated objective* of the
specific backlog item you wrote. Keep that default until you've watched
the system work correctly for a while — it's much easier to loosen a
guardrail deliberately than to recover from one that was too loose from
day one.

## What "done" looks like for your first month

Not a dramatic outcome — a boring, working loop. By the end of the first
month you should have: a handful of `reports/` files you can skim to see
what happened while you weren't watching, at least one or two items moved
to `done/` with their history preserved via `git mv`, and a `POLICY.md`
that's been edited at least once based on something a real run taught
you. If that's where you land, the system is working exactly as intended
— the value compounds from here, not from any single run.
