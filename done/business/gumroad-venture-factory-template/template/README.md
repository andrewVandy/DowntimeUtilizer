# [Your Project Name]

Turns unused Claude Code quota into shipped work instead of letting it
expire. A structured backlog of projects lives in this repo; a nightly
Cloud Routine picks the highest-ROI unblocked item, makes progress, and
opens a PR — checkpointing everything back into the repo so the next run
(which starts from a fresh clone with no memory) can pick up where the
last one left off.

See `CLAUDE.md` for the backlog schema, ROI formula, and checkpoint
format. See `POLICY.md` for the guardrails the unattended routine runs
under. See `ROUTINE_PROMPT.md` for the exact prompt the routine runs.

Scope is deliberately narrow to start: one nightly schedule trigger, no
idle detection, no quota polling. Add those later once the basic loop has
proven itself on a few real runs — see "Make this yours" in `CLAUDE.md`.

## Setup (manual — one time, roughly 15 minutes)

These steps are external-facing (GitHub, your claude.ai account) and are
left for you to run rather than automated:

1. **Rename this project.** Replace `[Your Project Name]` above, and
   update any other placeholder text you find in `CLAUDE.md`,
   `POLICY.md`, and `ROUTINE_PROMPT.md` — search for `[Your` to find them
   all.

2. **Push this repo to GitHub.** A Cloud Routine clones from GitHub, so a
   local-only repo isn't reachable by it.
   ```
   gh repo create your-project-name --private --source=. --push
   ```
   (or create the remote manually and `git push -u origin main`).

3. **Connect GitHub to Claude Code**, if not already done: run
   `/web-setup` in a Claude Code session and grant access to this repo.

4. **Create the routine**: run `/schedule` in a Claude Code session
   (needs a claude.ai subscription login, not an API key) and describe
   it, e.g.:
   ```
   /schedule nightly at 1am, run the backlog routine in this repo
   ```
   When Claude asks for the prompt, paste the contents of
   `ROUTINE_PROMPT.md`. When it asks for the repository, select this one.
   Leave "Allow unrestricted branch pushes" **off** — the routine should
   only ever be able to open PRs, never push straight to `main`. This is
   the single most important setting in this whole setup: it's what
   keeps an unattended agent from being able to merge its own,
   unreviewed changes into your real branch.

5. **Verify**: `/schedule list` should show the routine, or check
   https://claude.ai/code/routines. Use "Run now" on the routine's detail
   page to test it once before waiting for the nightly schedule.

6. **Seed the backlog**: add a few real project files under `backlog/`
   (see `backlog/_template.md` and the worked example in
   `backlog/research/example-first-project.md`) before the first
   scheduled run — an empty backlog just produces a "nothing to do"
   report. Three to five items is enough to start; you can always add
   more later, including ones a routine run itself suggests in a report.

## What to expect from the first few runs

Don't expect the first run to ship something impressive — expect it to
correctly pick the highest-scoring item, make honest partial progress,
and leave a clean checkpoint. That's the whole system working as
designed. Read the first couple of `reports/` files closely: they're
where you'll notice if your `impact`/`confidence`/`priority`/`effort`
estimates on your seed items were off, or if a guardrail in `POLICY.md`
is stricter or looser than you actually want. Adjust the backlog and
`POLICY.md` based on what you see, not what you guessed going in.

## Why this shape, not something fancier

- **Files over a database**: a Cloud Routine gets a stateless fresh clone
  every run with no memory of previous runs. Plain git-tracked Markdown
  is the memory — no server to keep running, no state to lose between
  runs, and you can read (and edit) the entire "brain" of the system in
  a text editor.
- **A human merges**: the routine opens PRs, never pushes to `main`
  directly. This is a deliberate seam — it's the one place you see
  everything before it becomes permanent, and it costs you a few minutes
  of review per run in exchange for a hard backstop against a bad
  unattended decision compounding unreviewed.
- **One item at a time, worked to a checkpoint**: an agent given a whole
  backlog and no other constraint tends to spread thin — a little
  progress on everything, nothing finished. Picking the single
  highest-scoring item and the `in-progress` continuation bonus in
  `CLAUDE.md` both exist to counteract that specific failure mode.
