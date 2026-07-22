---
id: github-to-claude-code-launcher-extension
category: business
status: backlog
impact: 3
confidence: 3
priority: 3
effort: 3
depends_on: []
created: 2026-07-22
updated: 2026-07-22
---

## Objective

Build and ship a small, free-to-install, paid-upgrade Chrome extension that
adds a one-click "open this in Claude Code on the web" button to GitHub
issue, PR, and repo pages — turning a page you're already reading into a
running Claude Code session without the copy-paste-URL-into-a-new-tab
dance. Definition of done for v1: extension built, tested against real
GitHub pages, packaged and submitted to the Chrome Web Store (this part
*can* be done autonomously — no personal/payout identity required, unlike
a Gumroad seller account), with a short free tier and a small one-time-
payment or subscription upgrade (e.g. multi-repo quick-switch, custom
prompt templates per repo) gating the paid tier.

## Context

Spawned from `backlog/research/ai-monetization-overnight-automation.md`
(category #5, Digital Products & Marketplaces — see that file for sourcing).
Chrome extensions are one of the few categories in that research with
independently verifiable revenue at a solo-operator scale (Superpower
ChatGPT $20-30k MRR, Mate Translate $18k/mo/800k users, Closet Tools
~$42k/mo — all cited with sources in the research file's category #5).

**Why this specific idea, not a generic AI-wrapper extension**: this
project's own domain expertise (Claude Code on the web, this repo's own
Cloud Routine setup) is a direct, unfair advantage here — no gap between
"what this project already knows deeply" and "what the product needs to
be good at." A generic prompt-improvement or chat-wrapper extension would
compete in a crowded, undifferentiated space; this one is narrow, useful
to a specific audience (developers already using Claude Code) that this
project's own operator (the user) is already part of.

**Distribution plan, written before any build work, per the
`ai-monetization-overnight-automation` research's category #15 lesson**
(agents produce lots of output with zero revenue when distribution is an
afterthought, not a plan):
1. Chrome Web Store search/category listing is free built-in distribution
   — optimize the listing (title, keywords, screenshots) for "claude code"
   and "github" searches.
2. Post to `awesome-claude-code` (hesreallyhim) as a suggested addition —
   that repo is already cited as the canonical curated list in the sibling
   `claude-code-productivity-tools` research file; being listed there is
   free, targeted distribution to exactly the right audience.
3. A single build-in-public post (X, and/or a Show HN) once it's live —
   cite this project itself (an autonomous agent building and shipping a
   real Chrome extension) as the interesting hook, not just the tool.
4. No paid ads, no cold outreach — if organic channels 1-3 don't produce
   installs within a reasonable window, that's a real signal to deprioritize
   further investment here rather than escalate spend.

**Constraint check against `POLICY.md`**: Chrome Web Store developer
registration requires a one-time $5 fee and a Google account — this is a
small real-money spend, so per `POLICY.md`'s "never spend real money...
without it being the explicit, stated objective" rule, the *first* run to
pick this item up should stop and flag this specific step for the user's
manual go-ahead (either have the user create the developer account, or
get explicit confirmation before the routine spends the $5), rather than
assuming it's covered by "ship a Chrome extension" being the stated
objective. Building, testing, and packaging the extension itself requires
no such spend and can proceed fully autonomously.

## Checkpoint

### Latest state
Not started. Idea sourced and scored from research; no build work done.

### Next steps
1. Confirm the exact interaction: does GitHub's DOM allow reliably
   injecting a button on issue/PR/repo pages across GitHub's current UI
   (check for an existing "Open in..." extension pattern to model against,
   e.g. how "Open in VS Code" / "Open in Codespaces" buttons are injected).
2. Decide the free/paid split concretely (e.g. free: single-repo launch
   button; paid: saved custom prompt templates per repo, multi-account
   support) before writing code, not after.
3. Build a minimal v1 (manifest v3, content script + small popup), test
   against a handful of real repos including this one.
4. Flag the Chrome Web Store $5 registration fee to the user per the
   Context note above before spending it.
5. Once packaged: submit to Chrome Web Store, then execute the
   distribution plan in Context (steps 2-3 above) — don't stop at "built
   and listed," the listing alone won't generate installs.

### Learnings
(none yet)
