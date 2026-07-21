---
id: gumroad-venture-factory-template
category: business
status: backlog
impact: 5
confidence: 4
priority: 5
effort: 4
depends_on: []
created: 2026-07-21
updated: 2026-07-21
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
Not started. Idea locked and differentiation-checked; no build work done
yet.

### Next steps
1. Draft the generic/sanitized template repo structure (strip
   project-specific content from `backlog/`, `POLICY.md`,
   `ROUTINE_PROMPT.md`, `CLAUDE.md`; add clear placeholders and a
   setup-wizard-style top-level README).
2. Write the buyer-facing guide explaining the pattern (why Cloud
   Routines, why git-tracked checkpoints, why ROI scoring with the
   finish-bonus) and how to adapt it to their own use case.
3. Draft Gumroad listing copy (title, description, price point — check
   comparable prices on the products found in the differentiation check
   above) and a cover-image brief.
4. Once packaged and ready: stop and hand off to the user for the
   manual step (create Gumroad seller account, upload, set price,
   publish) — do not attempt this step autonomously.

### Learnings
(none yet)
