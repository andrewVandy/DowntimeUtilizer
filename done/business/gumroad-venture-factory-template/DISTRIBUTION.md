# Distribution plan

Flagged as a gap by `ai-monetization-overnight-automation` (category #15):
that research documents an agent that built 7 digital products and wrote
150+ posts and made **$0** — output without a distribution plan is the
single most common way this kind of project fails. "Upload to Gumroad and
wait" is not a plan. This file is.

## Why build-in-public is the right channel here, specifically

The product *is* a description of a system that produced itself — this
document, the template repo, and the guide were all built by an actual
instance of the system being sold, working an actual backlog item
end-to-end. That's a genuinely unusual, verifiable hook ("I built this by
having my own overnight AI routine build it, here's the repo") that a
generic prompt-pack seller can't claim. The distribution plan should lead
with that story, not with feature bullets.

## Channel 1 — a build-in-public post about the source project itself

Before (or instead of) promoting the Gumroad listing directly, write a
post about the *underlying project this template is extracted from* —
what it does, why it's built the way it is, a real example of an
overnight run's report and PR. Mention the template as a "here's how to
set this up yourself" link near the end, not as the headline. This
mirrors the pattern the source research found actually works (Pieter
Levels-style build-in-public, Indie Hackers case studies) rather than a
cold product announcement, which converts worse in this exact community.

**Draft angle**: "I set up an AI agent that works my backlog every night
while I sleep, and it's shipped N PRs so far. Here's exactly how it's
built (and a template if you want to set up your own)."

**Where to post it**:
- **Hacker News, "Show HN"** — this audience is specifically primed for
  "I built X, here's how" posts with a working repo attached; the
  research's own category #15 findings (real overnight-agent experiments)
  came substantially from HN discussion threads, meaning this exact
  community already has appetite for this exact topic.
- **Indie Hackers** — post as a milestone/build-log entry, not a launch
  announcement; that platform's culture rewards "here's the journey and
  the numbers" over "buy my thing."
- **A relevant subreddit** (e.g. r/ClaudeAI or r/artificial, whichever is
  more active at publish time — check both) — same build-in-public
  framing, not a direct sales pitch; most subreddit rules in this space
  penalize direct self-promotion but tolerate a genuine build writeup with
  a link at the end.

## Channel 2 — the existing Claude Code tooling ecosystem

`claude-code-productivity-tools` (sibling research item in this backlog)
already catalogued the exact communities and aggregators that pay
attention to new Claude Code tooling:

- **`awesome-claude-code`** (hesreallyhim) — the canonical curated list
  for this ecosystem. Submitting a PR/issue proposing this template for
  inclusion is free, high-relevance distribution if it's accepted
  (maintainer curates with judgment, so the submission needs to clearly
  explain what's different from a prompt pack, not just link it).
- Aggregator sites that surface new Claude Code tools organically
  (skillsllm.com and similar) tend to pick up new repos via their own
  crawling — no outreach needed, but worth confirming the template repo
  itself (not just the Gumroad listing) is public and has a clear README,
  since that's what these aggregators actually index.

## Channel 3 — X/Twitter, once there's a real number to cite

The monetization research (category #1, #15) is consistent on this: the
posts that convert are the ones with a specific, verifiable number
("$X in Y days"), not generic feature announcements. Don't post to X
until there's a real first-week or first-month number to cite (installs,
revenue, or even just "N real overnight runs completed on my own
backlog") — a numberless launch tweet is exactly the "output, no
distribution traction" pattern this whole plan exists to avoid.

## What NOT to do

- Don't buy ads or run paid promotion — no data in the source research
  supports paid acquisition working for a $24 one-time-purchase template
  at this scale; organic/community channels are where every comparable
  product's traction actually came from.
- Don't post the same build-in-public writeup verbatim across all three
  channels the same day — space it out and adapt tone per community (HN
  wants technical depth, Indie Hackers wants the number/journey, Reddit
  wants a slightly more casual framing).

## Handoff

Drafting the actual post content (HN/Indie Hackers/Reddit copy) is safe
for a routine to do once there's a real number to cite. Posting it
publicly, and any account creation needed to post it, is a manual step
for you — same boundary as the Gumroad publish step itself.
