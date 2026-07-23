---
id: chrome-extension-ai-wrapper
category: business
status: backlog
impact: 4
confidence: 4
priority: 4
effort: 3
depends_on: []
created: 2026-07-23
updated: 2026-07-23
---

## Objective

Build and publish one narrow, single-purpose AI-powered Chrome extension
to the Chrome Web Store — a real second (or third, alongside
`gumroad-venture-factory-template`) revenue attempt, chosen because the
Chrome Web Store gives free organic distribution (search + store browsing)
that a standalone SaaS or agency doesn't get, which sidesteps this
project's hardest unsolved problem: an unattended routine has no safe way
to do outbound marketing/sales itself.

Definition of done for a sellable v1: a working extension solving one
narrow, well-defined problem (not a general "AI everything" wrapper),
freemium-gated (free tier + $5-15/mo paid tier via a payment provider that
doesn't require the extension itself to touch money — e.g. ExtensionPay or
Stripe Checkout links), store listing copy and screenshots drafted and
ready. Actually submitting to the Chrome Web Store (requires a one-time
$5 developer registration fee and a real developer identity) is a manual
handoff step for the user, same pattern as the Gumroad seller-account step
in `gumroad-venture-factory-template` — the routine's job is to get
everything else fully built and ready.

## Context

Sourced from `ai-monetization-overnight-automation` category #5: verified,
real revenue in this exact niche — Superpower ChatGPT ($20-30k MRR), Mate
Translate ($18k/mo, 800k users), Closet Tools (~$42k/mo) — all on a
freemium-to-subscription model, and 442 AI extensions now individually
have 1,000+ users. Category #14 (vibe coding) directly applies: this is
squarely the kind of small, scoped tool Claude Code can build end-to-end
in one sitting, unlike a full SaaS product.

**Pick the specific extension idea before starting the build** — do not
default to another "chat with ChatGPT" wrapper (saturated). Spend the
first session on: (a) browsing the Chrome Web Store's AI category for
a genuine gap (a specific narrow workflow annoyance, not a general
assistant), (b) sanity-checking there isn't already a dominant free
incumbent, (c) writing that decision down here before any code.

**Explicit anti-"zero-revenue" step** (per `ai-monetization-overnight-
automation` category #15's central lesson: agents that build lots of
output with no distribution plan earn nothing): before declaring this
"ready," this file's Checkpoint must include a specific plan for how the
*user* will get the first 100 installs (a subreddit/community it solves a
real problem for, a Product Hunt launch draft, etc.) — not just "publish
and see." Drafting that content (a Product Hunt listing, a launch post) is
safe for the routine to do; actually posting it publicly is a user
decision, same boundary as the Gumroad publish step.

## Checkpoint

### Latest state
Not started. Idea not yet picked — see Next steps #1.

### Next steps
1. Browse the Chrome Web Store's current AI-extension category and pick
   one specific, narrow problem to solve (write the chosen idea and the
   reasoning for picking it into this file before writing any code).
2. Scaffold the extension (manifest v3, minimal permissions — narrow scope
   keeps the Chrome Web Store review fast and reduces the trust bar for
   installs).
3. Wire up the freemium gate via a provider that doesn't require handling
   payments directly in the routine's own execution (ExtensionPay or a
   Stripe Checkout link are both used by comparable real products cited
   in Context).
4. Draft store listing copy, screenshots/promo images, and a launch-post
   draft (Product Hunt and/or a relevant subreddit) covering the "first
   100 installs" plan required above.
5. Hand off to the user for the manual step: pay the one-time $5 Chrome
   Web Store developer registration fee, submit for review, publish.

### Learnings
(none yet)
