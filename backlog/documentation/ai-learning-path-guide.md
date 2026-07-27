---
id: ai-learning-path-guide
category: documentation
status: backlog
impact: 4
confidence: 4
priority: 3
effort: 3
depends_on: [free-ai-learning-resources]
created: 2026-07-27
updated: 2026-07-27
---

## Objective

Turn `done/research/free-ai-learning-resources.md` (13 categories, 100+
free AI/ML learning resources, deliberately flat and unordered) into a
structured, ordered learning path: beginner → intermediate → advanced,
with explicit prerequisite chains, so someone starting from zero has a
concrete "do this, then this" sequence instead of a reference catalogue
to sort through themselves.

## Context

`free-ai-learning-resources.md` (`done/research/` once merged) explicitly
flagged this as its own natural follow-on in its Next steps: "consider
spinning a `backlog/documentation` item that turns this into an ordered
learning path... this file is deliberately unordered/exhaustive, not a
curriculum." That file itself notes math prerequisites (section 13:
linear algebra, calculus, probability/stats, optimization) are assumed
rather than taught by most of the ML/DL courses it catalogues — a prime
example of the sequencing problem this item should solve (math needs to
come *before* the courses that assume it, not be a footnote).

This is a pure synthesis/writing task over material that's already been
researched and verified — no new web research should be needed unless a
gap in sequencing surfaces something missing, in which case a quick
targeted search (not a fresh exhaustive pass) is enough.

Suggested structure to start from (adjust as the actual content dictates):
1. **Absolute beginner** (no code, no math) — Experience AI, Elements of
   AI, Google's ML Crash Course intro modules.
2. **Math foundations** — section 13 of the source file, sequenced
   (linear algebra → calculus → probability/stats → optimization),
   flagged as skippable for learners who already have this background.
3. **Programming + ML fundamentals** — Kaggle Learn micro-courses,
   Stanford CS229, fast.ai.
4. **Deep learning core** — MIT 6.S191, Stanford CS230/CS231n/CS224N,
   Karpathy's Zero to Hero, d2l.ai.
5. **Modern LLMs / agents** — Anthropic Academy, HuggingFace courses,
   agent-framework courses (section 8 of the source), Stanford CS25/CS153.
6. **Specialization branches** (pick based on interest) — RL (CS234/
   CS285), safety/alignment (section 9), production/MLOps (Full Stack
   Deep Learning, section 11's awesome-lists), research-paper fluency
   (section 12's paper-reading communities, arXiv, Papers with Code).

Depends on `free-ai-learning-resources` being `status: done` (it is, as
of this pass — verify it landed in `done/research/` before starting, in
case the PR carrying it hasn't merged yet).

## Checkpoint

### Latest state
Not started — freshly created this pass.

### Next steps
1. Read the full source file in `done/research/free-ai-learning-resources.md`.
2. Draft the ordered path as a new file (this item's own deliverable —
   suggest `done/documentation/ai-learning-path-guide/GUIDE.md` or similar
   once complete, following whatever structure/output convention the
   `gumroad-venture-factory-template` or other `done/` items established
   for multi-file deliverables).
3. Explicitly mark which resources are "core path" vs "optional/
   specialization branch" — don't just re-list everything in a different
   order, actually cut down to a recommended critical path with
   optional detours called out separately.
4. Sanity-check estimated total time commitment per stage (the source
   file has per-resource duration/hour estimates for some entries but not
   all — fill gaps where easy, don't block on it where not).

### Learnings
(None yet — first run.)
