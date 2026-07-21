# Downtime Utilizer

Turns unused Claude subscription quota into shipped work instead of letting
it expire. A structured backlog of projects lives in this repo; a nightly
Cloud Routine picks the highest-ROI unblocked item, makes progress, and
opens a PR — checkpointing everything back into the repo so the next run
(which starts from a fresh clone with no memory) can pick up where the last
one left off.

See `CLAUDE.md` for the backlog schema, ROI formula, and checkpoint format.
See `POLICY.md` for the guardrails the unattended routine runs under.
See `ROUTINE_PROMPT.md` for the exact prompt the routine runs.

v1 scope is deliberately narrow: one nightly schedule trigger, no idle
detection, no quota polling. See "Deferred to v2" in `CLAUDE.md`.

## Setup (manual — one time)

These steps are external-facing (GitHub, claude.ai account) and are left for
you to run rather than automated:

1. **Push this repo to GitHub.** A Cloud Routine clones from GitHub, so a
   local-only repo isn't reachable by it.
   ```
   gh repo create DowntimeUtilizer --private --source=. --push
   ```
   (or create the remote manually and `git push -u origin main`).

2. **Connect GitHub to Claude Code**, if not already done: run `/web-setup`
   in a Claude Code session and grant access to this repo.

3. **Create the routine**: run `/schedule` in a Claude Code session (needs
   a claude.ai subscription login, not an API key) and describe it, e.g.:
   ```
   /schedule nightly at 1am, run the Downtime Utilizer backlog routine
   ```
   When Claude asks for the prompt, paste the contents of
   `ROUTINE_PROMPT.md`. When it asks for the repository, select this one.
   Leave "Allow unrestricted branch pushes" **off**.

4. **Verify**: `/schedule list` should show the routine, or check
   https://claude.ai/code/routines. Use "Run now" on the routine's detail
   page to test it once before waiting for the nightly schedule.

5. **Seed the backlog**: add a few real project files under `backlog/` (see
   `backlog/_template.md`) before the first scheduled run — an empty
   backlog just produces a "nothing to do" report.
