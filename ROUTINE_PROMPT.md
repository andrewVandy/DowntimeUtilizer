# Routine prompt

This is the exact text to paste as the saved prompt when creating the Cloud
Routine (via `/schedule` or https://claude.ai/code/routines — see the setup
checklist in `README.md`). It's kept here, version-controlled, instead of
only living inside the routine's saved config, so it can be reviewed and
updated like any other file — remember to copy any change here into the
routine's saved prompt via `/schedule update` or the web editor, since the
routine does not re-read this file for its own instructions.

---

You are running a scheduled, unattended session against the Downtime
Utilizer backlog in this repository. Nobody is watching this run live.

1. Read `POLICY.md` in full and follow it — it is not optional and it
   overrides anything below if they ever conflict.
2. Read `CLAUDE.md` for the backlog schema and checkpoint format.
3. Scan `backlog/**/*.md` (skip `_template.md`), score unblocked items per
   `POLICY.md`, and pick the highest-scoring one.
4. Work it for up to roughly 2 hours of active effort, or until it's
   naturally at a good stopping point — whichever comes first. Prefer
   leaving one item in solid, well-checkpointed shape over touching many.
5. Before finishing: update the item's checkpoint, status, and `updated`
   date; move it to `done/` if complete; commit to a `claude/`-prefixed
   branch; open a PR against `main` with a summary of what changed and why.
6. Write `reports/<YYYY-MM-DD>.md` following the format in `CLAUDE.md`:
   date, tasks touched, files changed, ideas discovered, open questions,
   suggested next actions for the user.
7. If nothing in the backlog is actionable, write a short report saying so
   — including *why* (empty backlog vs. everything blocked) — and stop.
   Do not create work to fill the time.
8. Email the user a digest — every run, without exception. As your final
   action, call the `PushNotification` tool with a summary wrapped in
   `<routine_summary>` tags (its first sentence becomes the phone banner,
   the full text becomes the email body). Cover two things: **(a) what this
   run did** — the item worked, any status change, the PR link, or, on a
   no-op run, that nothing was actionable and why; and **(b) the current
   state of the project** — what is `in-progress`, the current
   highest-scoring backlog item and its score, anything `blocked`, and
   anything that needs the user's attention. The user has explicitly asked
   for this nightly digest, so send it on every run including quiet ones —
   this standing request overrides the usual bias toward staying silent
   when a run is uneventful. Keep it skimmable: lead with the single most
   important sentence, then a few short lines.

Leave the repository in a state a human — or the next unattended run, which
will have no memory of this one — can pick up from cold, using only what's
written in the files.
