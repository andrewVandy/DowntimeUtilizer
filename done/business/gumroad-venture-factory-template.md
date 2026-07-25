---
id: gumroad-venture-factory-template
category: business
status: done
impact: 5
confidence: 4
priority: 5
effort: 4
depends_on: []
created: 2026-07-21
updated: 2026-07-25
---

## Objective

Ship a real, purchasable Gumroad product — this project's first revenue
attempt, not another research pass. Productize a cleaned-up, generic
template version of this repo's own working system: a git-tracked
backlog, ROI scoring (with the finish-over-novelty bonus in `POLICY.md`),
checkpoint convention, and a nightly Cloud Routine — sold as a guide +
starter-repo template that teaches a Claude Code user how to set up their
own autonomous "unused quota → shipped work" pipeline.

Definition of done for a first sellable v1: a generic, sanitized template
repo (no Downtime-Utilizer-specific or personal content) plus a short
buyer-facing guide, packaged and ready to upload — checked into
`backlog/business/gumroad-venture-factory-template/` as it's built.
Actually creating the Gumroad seller account and hitting publish is a
manual step for the user (see Context) — the routine's job is to get
everything else fully ready.

## Context

Chosen over two alternatives (Chrome extension, niche newsletter) because
it has the fastest realistic path to an actual transaction — Gumroad has
no app-review process and handles payment/payout directly — and it
directly reuses tokens already spent building this project instead of
starting cold.

**Differentiation check, done before committing to this exact angle**:
searched Gumroad directly for existing Claude-Code-related products before
locking this in. The generic "Claude Code prompt pack / CLAUDE.md starter
kit" niche is **already saturated** — found multiple existing paid
products covering that ground: *The Complete Claude Code Playbook*
(getflowmate.gumroad.com, 91-page manual), *Claude Code Project Starter
Pack* (buildtolaunch.gumroad.com), *Claude Code Prompt Pack* (50+ prompts,
maxtendies.gumroad.com), *Claude Skills Pack* (thinkaiprompt.gumroad.com),
and a CLAUDE.md starter kit (joeyhipolito.gumroad.com). None of them cover
the specific mechanism this project demonstrates: an actual working
Cloud-Routine-driven backlog system with ROI scoring and cross-run
checkpointing. That's the real differentiation — sell the *system*, not
another prompt list. Re-check this before final listing in case the space
has moved since this pass.

**What the buyer actually gets** (not a vague "prompt pack"): a sanitized,
generalized version of this repo's own scaffold — `backlog/` schema,
`POLICY.md` guardrails, `ROUTINE_PROMPT.md`, the checkpoint convention —
plus a written guide covering the one-time setup this repo's own
`README.md` already documents (GitHub push, `/web-setup`, `/schedule`),
generalized for someone else's use case rather than this specific project.

**Constraint carried over from `POLICY.md`**: creating a Gumroad seller
account requires real identity/payout information — something this
project's unattended routine correctly should not and cannot do on the
user's behalf. That remains a manual step, tracked in this file's
Checkpoint, same pattern as the GitHub/routine setup already in
`README.md`.

## Checkpoint

### Latest state
Everything the routine can do without spending real money or creating
real accounts is now built and checked in under
`gumroad-venture-factory-template/` (sibling directory to this file, also
moved to `done/business/` in this commit):

- `template/` — the full sanitized, generic starter repo a buyer would
  clone: `README.md` (setup steps), `CLAUDE.md` (backlog schema + ROI
  formula), `POLICY.md` (guardrails, now also includes a "check for
  duplicate/overlapping unmerged PRs before starting work" rule — a
  lesson pulled directly from a real conflict this project hit on
  2026-07-25, see that day's report), `ROUTINE_PROMPT.md`, `backlog/`
  scaffold with `_template.md` and one worked example project, and empty
  `done/`/`reports/` directories (via `.gitkeep`). Grepped for this
  project's own name/owner/email — clean, no leakage.
- `GUIDE.md` — buyer-facing guide: the four core ideas (files-as-memory,
  the scoring formula and why the finish-bonus matters, checkpoints vs.
  logs, human-merges-only), a short setup walkthrough, and what a
  reasonable first month looks like.
- `LISTING.md` — draft Gumroad title/tagline/description/price
  ($24, anchored against the one directly-comparable priced product found
  in the original differentiation check) and a cover-image brief. Flags
  two things the *user* must fill in before publishing: a real run-count
  number for the description's credibility line, and a quick re-check
  that the "no direct competitor for this specific mechanism" finding
  still holds (search takes a few minutes, not a new research pass).
- `DISTRIBUTION.md` — closes the gap flagged below: a real plan (not just
  "upload and see"), leading with a build-in-public post about the
  underlying project itself rather than a direct sales pitch, with
  specific channels (Show HN, Indie Hackers, a relevant subreddit,
  `awesome-claude-code` submission) reasoned from what the source
  monetization research actually found converts in this space.

Marked `status: done` and moved to `done/business/` — everything above is
complete and doesn't need another routine pass. What's left (Gumroad
seller account creation, actually uploading/pricing/publishing, and later
posting the distribution content) is explicitly the user's manual step
per this file's own original Objective — not something a future run
should attempt autonomously.

### Next steps
For the user, not a future routine run:
1. Read `GUIDE.md` and `LISTING.md` under the `gumroad-venture-factory-template/`
   directory; fill in the `[N]` real-run-count placeholder in the listing
   description once you have a genuine number, and do the quick
   re-check noted in `LISTING.md` for any new direct competitor.
2. Create a Gumroad seller account (real identity/payout info — this is
   why it's a manual step, per `POLICY.md`) and upload the `template/`
   directory as the downloadable product, using `LISTING.md`'s copy.
3. Once live, work through `DISTRIBUTION.md`'s channel list — start with
   the build-in-public post (Channel 1), since that's the hook the whole
   plan leans on.
4. If you want a future routine run to *draft* the actual post content
   once there's a real number to cite (per `DISTRIBUTION.md`'s "what NOT
   to do" section — don't post without one), that's safe to delegate;
   posting it publicly and any account creation to do so stays manual.

### Learnings
Building the sanitized template surfaced one real, generalizable lesson
that got folded directly into the template's own `POLICY.md` rather than
just noted here: this same run independently discovered two other open,
unmerged PRs on this repo (from 2026-07-23 and 2026-07-24) that had
already completed passes on both top-scored backlog items before this
run started — meaning this run's first attempt (a second pass on
`claude-code-productivity-tools`) duplicated already-better work and had
to be discarded after the fact. Added an explicit "check for
duplicate/overlapping unmerged PRs before starting" rule to the shipped
`POLICY.md` so a buyer's own setup doesn't repeat the same wasted-effort
pattern. See `reports/2026-07-25.md` for the full story.
