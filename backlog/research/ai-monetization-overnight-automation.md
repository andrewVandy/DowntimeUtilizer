---
id: ai-monetization-overnight-automation
category: research
status: in-progress
impact: 5
confidence: 4
priority: 5
effort: 5
depends_on: []
created: 2026-07-21
updated: 2026-07-22
---

## Objective

Produce an exhaustive survey of how people and small operators are actually
using AI systems — especially autonomous/overnight automation of the kind
this project runs — to generate real cash flow today. Not a curated top-10
list: a broad, source-backed catalogue of every distinct pattern found,
so this file becomes the seed list future `backlog/business/` items get
scored and picked from.

Requested explicitly by the user, verbatim intent preserved here: "Research
all the ways people are utilizing ai systems to earn money. Look at all
niche boards like reddit, twitter, or any other possible resources out
there. this is an exhaustive effort to list EVERYTHING that people are
doing nowadays, so use every token you need to and provide ALL material
you can."

## Context

This overrides `POLICY.md`'s default "prefer one item in solid shape over
spreading thin" guidance in one specific way: breadth is the point of this
item, not depth on a single idea. It is fine — expected — for this to span
multiple sessions/runs. Each pass should widen source coverage (new
subreddits, new platforms, new search angles) rather than re-covering the
same ground, and should checkpoint exactly which sources have been mined
so the next pass starts from the frontier, not from zero.

Sources explicitly in scope: Reddit (niche subs, not just the obvious
r/artificial — see Findings for the actual list mined), Twitter/X, Indie
Hackers, Product Hunt, Hacker News, YC/startup forums, niche newsletters,
blogs, and anywhere else a real pattern turns up.

Output of this item is the `## Findings` section below — a working
reference document, not a report to be read once and archived. When later
`backlog/business/` items get created from ideas found here, link back to
this file's id.

## Checkpoint

### Latest state
Second research pass complete (2026-07-22). Closed both gaps flagged by
pass 1: solo-operator lead-gen income data (category #8) and a dedicated
X/Twitter pass — see Findings pass 2 below. Also confirmed Reddit direct
mining is not just a search-indexing gap but a hard tool-level block in
this environment (see Learnings) — downgrading that from "next step" to
"known permanent limitation, work around it." Mined the file for concrete
ideas per next-step 3: created two new `backlog/business/` items
(`github-to-claude-code-launcher-extension`,
`ai-coding-freelance-portfolio-kit`) rather than forcing 3-5 — judged two
well-differentiated, source-backed ideas better than padding to a target
count with weaker ones. Also flagged a distribution-plan gap in the
existing `gumroad-venture-factory-template` item (see its own Next steps)
since category #15's core lesson is "build a distribution plan alongside
the build plan, not after." Left `in-progress`, not `done` — breadth-first
mandate means this can always widen further, and category #10
(trading/financial) and #16 (Discord) remain thin.

### Next steps
1. Reddit is now confirmed inaccessible to this tool environment (WebFetch
   refuses reddit.com/old.reddit.com; Pushshift API returns 403) — stop
   attempting direct fetches. Future passes needing Reddit-flavored signal
   should rely on secondary aggregator/roundup coverage (as this file
   already does) or note the gap explicitly rather than re-attempting the
   same blocked approach.
2. A new SEO-content-farm cluster sprang up this pass around "OpenClaw"
   (a self-hosted open-source AI agent with a skill marketplace, ClawHub)
   — dozens of near-identical "how to make money with OpenClaw" blog posts
   from unrelated-looking domains (superframeworks, medium/@0xmega,
   a1republic, topsaasworld, openclawway, openclawlaunch, growwstacks) all
   citing the same handful of figures. Treat this whole cluster with the
   same skepticism as the KDP/trading-bot marketing content already
   flagged — a future pass should verify the OpenClaw GitHub repo/ClawHub
   listing counts directly before citing any number from this cluster as
   fact, not just cross-reference within the cluster itself.
3. Categories #10 (trading) and #16 (Discord) are still thin (agency/
   vendor marketing only, no solo-operator numbers) — lowest priority gap
   given both are already flagged low-confidence in Cross-cutting takeaway
   #2, but a future pass could still try.
4. If either new `backlog/business/` item spawned this pass gets picked up
   and completed, come back and note the outcome here — this file is the
   feedback loop for whether the ROI-scoring judgment calls made this pass
   were right.

### Learnings
Confirmed this pass: Reddit isn't just poorly indexed by `site:` search —
the WebFetch tool itself refuses `reddit.com` and `old.reddit.com`
outright ("Claude Code is unable to fetch from..."), and the Pushshift
mirror API (`api.pushshift.io`) returns HTTP 403. This is a firm
environment-level wall, not something a smarter query will route around;
stop budgeting future-pass effort on "try Reddit again." X/Twitter,
by contrast, worked well this pass via plain `WebSearch` (no `site:`
needed) — got real thread content and specific case studies (see
Findings), though several were self-reported/DM-verified rather than
independently confirmed, so flagged accordingly rather than taken at face
value. General pattern reinforced again: any new tool/platform that
suddenly has a wave of near-identical "how to make money with X" blog
posts across unrelated-looking domains (this pass: OpenClaw) is a signal
to lower confidence on cited figures, not raise it — the volume of
content is itself weak evidence of a gold-rush/content-farm dynamic, not
of the underlying opportunity's size.

## Findings

First research pass, 2026-07-21. ~30 web searches across Reddit, Hacker
News, Indie Hackers, Product Hunt, Medium/Substack, and general web.
**Coverage caveat**: direct `site:reddit.com` queries mostly returned
nothing (Reddit is poorly indexed by this search tool) — Reddit-sourced
data points below came in secondhand, via HN/Medium/blog posts that quote
or link Reddit threads, not from reading the subreddits directly. A future
pass should hit Reddit's own search/API or fetch subreddit URLs directly
rather than searching for them. Every entry below has at least one
concrete source link.

### 1. Micro-SaaS / AI Wrapper Products

Thin, focused products built on top of a foundation model API, sold as
subscriptions. The most consistently real money in this list — many
public revenue numbers.

- **Chatbase** (AI customer support wrapper): $335k+ MRR, grown mostly via founder posting build updates on X. ([Signal](https://signalhub.substack.com/p/a-chatgtp-wrapper-making-5m-a-month))
- **PDF.ai** (chat-with-your-PDF): $60k+ MRR, later acquired. ([DEV](https://dev.to/kacper7/how-to-build-an-ai-wrapper-in-1-day-ai-startup-ideas-examples-5484))
- **Photo AI** (Pieter Levels): $0 to $132–138k MRR in 18 months, ~$2M total revenue. Widely cited as the canonical solo AI-wrapper case study. ([Indie Hackers](https://www.indiehackers.com/post/photo-ai-by-pieter-levels-complete-deep-dive-case-study-0-to-132k-mrr-in-18-months-3a9a2b1579))
- **StealthGPT** (undetectable AI text): $200k+/month. ([microsaasidea](https://microsaasidea.substack.com/p/micro-saas-agencies-ai-process-ai-content-2))
- **Devv** (AI search for developers): $30k/month. Various other $8.6k–$62k MRR AI tools documented on Indie Hackers, several crediting SEO as the primary growth channel. ([Indie Hackers search](https://www.indiehackers.com/post/from-150-month-to-8-6k-mrr-how-one-pivot-and-a-lot-of-seo-saved-my-ai-startup-2af6a82ee6))
- Why it works: API costs are near-zero marginal, distribution is the real bottleneck (word of mouth, SEO, X build-in-public), and being narrow beats being general.
- Risk/moat: thin wrappers are easy to clone; defensibility comes from distribution/brand and accumulated user data, not the underlying model call.

### 2. AI Agencies & Productized Consulting

Selling AI implementation as a service to businesses that have budget but
no in-house AI capability.

- Consultants with case studies charge $200–$600/hour; generalists without proof compete with $99 online courses instead. ([emergent.sh](https://emergent.sh/learn/how-to-make-money-with-ai))
- **AI chatbot for local businesses**: $2,000–$5,000 setup + $500–$2,500/mo retainer; realistic to reach $10–15k/mo in 6 months, $30–50k/mo in 12–18 months with a small team. ([AI Business](https://aibusiness.vc/solo/ai-chatbot-local-business))
- **AI automation consulting** (no-code GPT bots for executives): one documented case went from zero coding background to $1,000/month building simple custom-GPT bots for busy professionals. ([aicofounderstack](https://www.aicofounderstack.com/2026/05/10/10-ai-side-hustles-that-actually-pay-in-2026/))
- Why it works: businesses want AI outcomes, not AI expertise — a solo operator with one or two "AI setup" packages can sell to dozens of small clients.
- Risk/moat: crowded and rate-competitive at the generic end; niche depth + a visible portfolio is what separates $99/mo commodity work from $500/hr consulting.

### 3. Freelance AI Development / "Build me an MVP" services

- Average AI-coding freelancer on Upwork reportedly earns $12,400/month, ~3.2x traditional developer rates. Junior $50–100/hr, mid $100–200/hr, senior $200–400+/hr. ([betonai.net](https://betonai.net/ai-coding-is-the-highest-paying-freelance-skill-in-2026-heres-exactly-what-to-charge-real-rate-data/))
- A solo developer using Claude Code / similar tools can plausibly deliver $20–75k-agency-quality MVPs for $5–25k, still earning more per hour than an agency's senior engineer. ([emergent.sh](https://emergent.sh/learn/how-to-make-money-with-ai))
- Retainer model: $3,000–8,000/month per client for ongoing AI maintenance/feature work; three clients ⇒ $9–24k/month predictable income. (same source)
- Why it works: this project's own toolchain (Claude Code) is directly the production asset here — no gap between "what we have" and "what the market pays for."
- Risk: "vibe coding" saturation — see #14 below on the flip side of this trend.

### 4. Content Automation (faceless video, niche sites, newsletters)

- **Faceless YouTube automation**: successful channels reported at $5,000–$50,000/month; top 1,000 faceless channels combined reportedly gross $50M+/year. Best niches: personal finance, tech reviews, AI tools, business case studies, history — $15–40 RPM vs $2–8 for general entertainment. Realistic timeline: 6–12 months to profitability, $500–2,000/month outsourced production cost. ([sidequesthustle](https://sidequesthustle.com/guides/youtube-automation-guide-2026), [jogg.ai](https://www.jogg.ai/blog/faceless-youtube-automation/))
- **AI-assisted niche/blog sites**: one documented case reached $76,000 in year one from display ads using heavily-edited AI content; another sold a 14-month-old AI-powered site for $108k. Ongoing sites without a sale: $500–3,000/month once established. ([goodreads](https://www.goodreads.com/author_blog_posts/24530083-blogger-uses-ai-to-earn-76-000-in-year-1), [Let's Play with AI](https://letsplaywithai.substack.com/p/how-we-built-and-sold-a-108k-ai-powered))
- **AI-curated niche newsletters**: one example grew to 12,000 subscribers, monetized via $500/issue sponsorships + affiliate links, ≈$1,800/month. ([aicofounderstack](https://www.aicofounderstack.com/2026/05/10/10-ai-side-hustles-that-actually-pay-in-2026/))
- Why it works: AI collapses the production-time cost of content; the bottleneck shifts entirely to niche selection, distribution, and audience retention — the "boring" parts AI doesn't solve for you.
- Risk: platform/algorithm dependency (YouTube, Google ranking changes); pure AI-generated content increasingly penalized (see KDP note below) — editing/curation layer matters.

### 5. Digital Products & Marketplaces (prompts, GPTs, templates, extensions)

- **Prompt marketplaces** (PromptBase etc.): sellers keep ~80% revenue; focused prompt packs reportedly earn $2,000–10,000/month for some creators, though prompt-selling alone is usually described as a supplement to consulting/product income, not a standalone living ($200–3,000/mo typical). ([dodopayments](https://dodopayments.com/blogs/sell-ai-prompts-online), [promptstodollars](https://promptstodollars.com/turn-ai-prompts-into-income/))
- **GPT Store**: publish custom GPTs, earn from usage (mechanism exists; no strong independent revenue data surfaced this pass).
- **Chrome extensions as AI wrappers**: real, verifiable revenue — Superpower ChatGPT ($20–30k MRR), Mate Translate ($18k/mo, 800k users), Closet Tools (~$42k/mo). Freemium-to-$10–20/mo-subscription is the dominant model. 442 AI extensions now have 1,000+ users combined 115M+ installs. ([stormy.ai](https://stormy.ai/blog/build-profitable-ai-chrome-extension-blueprint), [extensionpay](https://extensionpay.com/articles/browser-extensions-make-money))
- **Notion templates, workflow packs, small GPT-powered tools** on Gumroad/Etsy — repeatedly mentioned as a pattern across sources but with less hard revenue data than the extension/wrapper category.
- Why it works: near-zero distribution cost via existing marketplaces (Chrome Web Store, Gumroad, GPT Store); AI lowers the cost of building the product itself.
- Risk: marketplace platform risk (store policy/ranking changes) and easy copyability.

### 6. E-commerce Automation

- **AI-run dropshipping**: one documented 30-day case study generated $54,475 letting AI run product research/testing/ops; another more modest case made ~$800 profit with near-zero manual labor. Typical range cited: $1,000–10,000/month first year, five/six-figure monthly for established stores. AI reportedly cuts research time ~85% and failed-product-test rate ~45%, testing ~10 products in the time a human tests one — but a human "Architect" overseeing strategy is still described as necessary. ([productlair](https://productlair.com/blog/ai-dropshipping-2026), YouTube case study referenced in search)
- **AI print-on-demand**: AI design generation cuts a 3–5 hour design task to 15–30 minutes; sellers reportedly earn $500–5,000/month. ([printjourney.ai](https://www.printjourney.ai/), [tinymarketinglab](https://tinymarketinglab.com/how-to-fully-automate-your-print-on-demand-business/))
- Why it works: AI automates the two most time-consuming parts (product/design research, listing generation) in an already-proven business model.
- Risk: real-money risk (inventory/ad spend even in dropship/POD models), platform dependency (Shopify, marketplaces), and genuinely mixed results in the sourced case studies — this is not passive.

### 7. Data Work (labeling, synthetic data, RLHF)

- Legitimate, low-barrier-to-entry: $20–45/hour depending on task complexity and domain expertise; domain experts (doctors, lawyers, engineers) correcting AI model outputs can earn "hundreds of dollars an hour." Market grew to $5.46B in 2025, +21%/year. ([builtin](https://builtin.com/articles/train-ai-side-hustle), TIME)
- Caveat directly from sourcing: industry is "poorly regulated," some workers report account deactivation with earnings unpaid — this is gig-labor risk, not automation risk.
- Fit for this project: this is a human-labor category, not something an unattended overnight agent can do itself — relevant only as background/business-idea context, not as an automatable backlog item.

### 8. Lead Generation / Cold Outreach Agencies

- AI-powered prospecting/outreach agencies (e.g. ColdIQ, LeadGenius as examples of the category) build "automated revenue engines" combining AI agents with human relationship management; sourced material describes tool capability and pricing philosophy but no hard agency income figures surfaced this pass. ([coldiq.com](https://coldiq.com/blog/best-lead-generation-agencies-for-ai-companies))
- Why it works: AI automates prospecting/enrichment/personalization at a volume no human SDR team matches; still needs a human layer for actual relationship close.
- Gap: this category needs a follow-up pass specifically for solo-operator (not agency-scale) income data.

### 9. AI Customer Support / Chatbot-as-a-Service

Overlaps #1 and #2 — covered there (the $2–5k setup + $500–2,500/mo retainer model, and the $0.10–0.50/conversation vs $12–25/ticket-human-cost economics that make the pitch to SMBs work). ([botpress](https://botpress.com/blog/ai-agent-customer-support))

### 10. Trading & Financial Automation

- **Crypto/stock trading bots**: widely marketed as passive income; sourced material is explicit that "there's no guarantee of profits" and performance depends entirely on strategy quality — no verified independent income figures found, mostly vendor marketing content. Treat as high-risk/unverified. ([mexc.com search results])
- **AI investment newsletters**: Prospero.Ai cited as achieving a 57% win rate vs S&P 500 in 2026 with tens of thousands of subscribers — one of the more concrete claims found, though it's the vendor's own claim, not third-party verified. ([prosperoai.substack.com](https://prosperoai.substack.com/))
- Why flagged high-risk: this is the one category where sourced "income" data is mostly marketing copy for the tools themselves rather than independently reported user results — treat any specific number here with more skepticism than the SaaS/content categories above.

### 11. Creative Licensing (stock photos, music, ebooks)

- **AI stock photos/music**: platforms like Wirestock (photos) and AudioJungle/Pond5/DistroKid (music) accept AI-generated content if disclosed; side-hustlers report $500–5,000/month after building a catalogue; composers with 200+ tracks across platforms cited at ~$1,000/month passive. ([shotkit](https://shotkit.com/ai-stock-images-passive-income/), [soundverse](https://www.soundverse.ai/blog/article/monetizing-ai-generated-music-licensing-sync-and-new-revenue-streams-for-modern-creators))
- **Amazon KDP ebooks**: single title $50–500/month, 5–10 titles $1,000–5,000/month, combined with email/direct-sales funnels up to $5,000–20,000+/month. **Important 2026-specific constraint**: Amazon now requires AI-generated (not just AI-assisted) content to be disclosed, and explicitly penalizes "churn and burn" bulk unedited AI text under the A10 algorithm — a pure-automation approach is now a liability, not just low-quality. ([sellermetrics.app](https://sellermetrics.app/how-much-money-can-you-make-with-amazon-kdp/), [Medium/Neil Caley on A10](https://medium.com/@neilcaley/amazon-kdp-is-changing-fast-the-2026-survival-guide-to-ranking-royalties-and-the-a10-algorithm-bac40eda3dd7))
- Why it works: licensing platforms provide distribution; AI collapses production cost of the underlying asset.
- Risk: increasing platform-side AI-disclosure enforcement (KDP explicitly, likely others following) — factor this into any backlog item in this space from day one, not as an afterthought.

### 12. Back-Office / Virtual Assistant Automation

- AI bookkeeping/VA services (Wing, MyOutDesk, Global Teams AI, Truewind as named examples): pitched as 60–70% cheaper than in-house hires; framed as a service-resale/arbitrage model (AI tool + human oversight sold as a package) rather than something a fully autonomous agent replaces end to end. ([wingassistant.com](https://wingassistant.com/bookkeeping-virtual-assistant/))
- Fit for this project: closer to a business/reseller opportunity than an automatable backlog item as-is.

### 13. Vertical Professional Services (legal, translation/localization)

- **Legal doc automation** (Spellbook, Harvey, Ivo, LegalSifter as named platforms): framed entirely as tools sold *to* law firms/in-house teams, not as a solo-operator income stream — lawyers reportedly spend 40–60% of time on drafting/review, which is the market these tools sell into. Not a good direct backlog fit (regulated, liability-heavy) but relevant as competitive/market intelligence. ([ironcladapp](https://ironcladapp.com/journal/legal-ai/what-is-contract-review-ai))
- **Translation/localization**: AI is described as augmenting rather than replacing freelance translators; platforms (Smartcat, Gengo, Phrase) connect freelancers to work, with AI handling first-pass drafts and QA. No strong solo-automation income figures surfaced.

### 14. Vibe Coding / Rapid App Building & Flipping

- "Vibe coding" (natural-language-to-app development) described as the default indie-hacker workflow in 2026; YC's latest batch reportedly shipping 95% AI-generated code. Non-technical founders building $10k+ MRR products "in days" is the claimed norm in some sources. One headline example: Polsia, a one-person company, reportedly hit $1M ARR in 30 days, $3M by two months. ([superframeworks](https://superframeworks.com/articles/vibe-coding-tipping-point-what-founders-need-to-know))
- **Important counter-signal**: the same research also surfaced that 45% of AI-generated code reportedly contains vulnerabilities, and a "90% problem" where builders get close to done but can't finish integration/debugging without real engineering skill. This is a real ceiling on how far pure-automation app-flipping can go without human review.
- Fit for this project: directly relevant — this is quite literally the same tool category (Claude Code) this project already runs. A backlog item scoping "build and ship one small paid tool end-to-end" would test this pattern directly rather than just researching it.

### 15. Autonomous "give an AI agent $X and a deadline" experiments — direct evidence

The single most relevant category to this project's actual thesis, because it's the closest existing analogue to what Downtime Utilizer itself is trying to do. Evidence is genuinely mixed — include failures, not just wins:

- **"$100, 48 hours, ship or die"**: agent spent first 4 hours scraping Reddit/X/Indie Hackers for pain points, found a spike of small-business complaints about "2026 AI Compliance Laws," reportedly built a response product — described by the author as "terrifyingly profitable" (specific $ outcome not independently verified). ([Medium/aimonks](https://medium.com/aimonks/i-gave-an-ai-agent-100-and-48-hours-to-make-money-the-results-were-terrifyingly-profitable-767dfe9a93d3))
- **Claude autonomous business attempt**: built 7 digital products, wrote 150+ posts, distributed across 6 platforms — **$0 revenue, zero conversions**, despite real output volume. Directly cautionary: production ≠ monetization. ([HN discussion](https://news.ycombinator.com/item?id=47417016))
- **"ChadGPT" Facebook Marketplace resale experiment**: AI sourced free/cheap items, coordinated pickup, resold — 3 items sold in one day for $145 total. Small but real, verified transaction-level outcome. (referenced via marketbeat.com / Codie Sanchez experiment)
- **Skyfire agent-to-agent commerce demo**: agents ("Aida", "SlangAgent") autonomously paying each other for services and accepting payment — demonstrates the mechanism of agent-to-agent commerce exists, but this is closer to infrastructure/demo than a replicable income source today.
- **30-day "AI agent passive income" test**: author explicitly said they were "genuinely glad" they hadn't let the agent execute trades autonomously after encountering enough edge cases/misreads — a direct data point on why unattended financial-decision automation (see #10) is the highest-risk category on this whole list.
- Why this category matters most: it's evidence, not theory, about the actual failure mode this project needs to guard against — an agent can produce a lot of *output* (products, posts, listings) with zero revenue if it skips validation/distribution. Any `backlog/business/` item generated from this research should be scored down on `confidence` unless it has a concrete distribution/traffic answer, not just a build plan.

### 16. Community/Platform Monetization (Discord bots)

- Subscription-gated bot features: example math shows a 5,000-member Discord community converting 20% to $10/mo premium ⇒ ~$8.5–9k/month net after Discord's cut. 2–3 tiers at $5–50/month is the typical structure. ([earnlab](https://earnlab.com/blog/how-to-make-money-on-discord-2026), [meegle](https://www.meegle.com/en_us/topics/monetization-models/monetization-for-discord-communities))
- Fit for this project: needs an existing community to bolt onto — not a cold-start pattern by itself.

### Cross-cutting takeaways for scoring future `backlog/business/` items

1. **The realest money is in categories with public, third-party-verifiable revenue numbers**: micro-SaaS/wrappers (#1), Chrome extensions (#5), freelance AI dev (#3), faceless content (#4). Score these higher on `confidence`.
2. **The riskiest / most marketing-driven claims**: trading bots and most "passive income" framing generally (#10). Score low on `confidence` regardless of headline numbers until independently verified.
3. **The most directly relevant precedent** is category #15 — actual attempts at unattended agent-driven income, including real failures. Any concrete `backlog/business/` idea spawned from this file should explicitly address the "produced output but zero revenue" failure mode (build a distribution/traffic plan alongside the build plan, not after).
4. **Regulatory/platform risk is increasing, not decreasing**: KDP's AI-disclosure crackdown (#11) is a specific, dated example — check current platform policy before scoring any content-at-scale idea, don't assume 2025-era rules still hold.

## Findings — pass 2 (2026-07-22)

~10 web searches, targeted at pass 1's two explicit gaps (category #8
solo-operator data, dedicated X/Twitter pass). Reddit direct-fetch attempts
(3 different approaches) all failed — see Learnings, not included as
findings since no content was actually retrieved.

### 8 (update). Lead Generation / Cold Outreach — solo-operator numbers found

Pass 1 only found agency-scale positioning; this pass found solo-operator
figures directly:

- Solo cold-email/lead-gen operators typically earn **$5,000–$15,000/month
  with 3–5 clients on retainer**; a 5-client agency at $2,500–$3,500/month
  per client is described as a realistic 6-month target
  (~$12,500–$17,500/month revenue). ([smartlead.ai](https://www.smartlead.ai/blog/lead-generation-business))
- Pricing structures: retainer $2,000–$6,000/month per client; per-meeting
  $200–$500/qualified meeting ($275 average in B2B SaaS per a cited 2026
  Leadium survey); per-verified-lead $50–$150. ([litemail.ai](https://litemail.ai/blog/cold-email-agency-pricing-guide-2026), [coldiq.com](https://coldiq.com/blog/best-cold-email-agencies))
- A cited 2025 Clutch survey claims average agency profitability within 3
  months when cold email is the primary channel — low overhead, so this
  scores reasonably on effort-to-first-dollar, but note all these figures
  are vendor/tool-blog sourced (litemail, smartlead, coldiq are themselves
  cold-email tool vendors), same "marketing content" caveat as category
  #10 — no independent third-party verification found.
- Net: closes the gap, but confidence should stay moderate, not high — this
  is vendor-adjacent content, not Indie-Hackers-style self-reported
  builder data.

### 17. AI Agent Skill/Plugin Marketplaces (OpenClaw / ClawHub) — new category

Surfaced this pass, not covered in pass 1. **OpenClaw** is a real,
self-hosted open-source AI agent framework (model-agnostic — works with
Claude, GPT, Gemini, local models) with a public skill marketplace,
**ClawHub**, described variously as having 700-17,000+ skills depending on
source (figures disagree — treat as unverified, see Learnings).

- Individual skill sellers reportedly earn **$100–$1,000/month per skill**,
  with a realistic starter portfolio (3 skills, ~$20 average) generating
  ~$600/month; top single-skill sellers cited over $1,000/month.
  ([Medium/@0xmega](https://medium.com/@0xmega/the-clawhub-skill-economy-how-builders-are-making-600-20-000-month-selling-ai-agents-0b56d4aede5e))
- Most-cited success story: "Felix"/Claw Mart, reportedly $71,300 in
  cumulative earnings — an outlier, not a typical result, per the same
  source that reports it.
- One thread claim (Ihtesham Ali, X, self-reported/DM-verified rather than
  independently confirmed): a Berlin-based seller made $127,000 from
  custom OpenClaw skills; a Texas solo developer cleared $43,000/month
  from web-scraping automations; a Toronto-based operator built an
  email-copywriting agent generating $8,200/month. Treat these as
  directional anecdotes, not verified figures — same skepticism tier as
  category #10's trading claims.
- **Why flagged as lower-confidence category overall**: a wave of
  near-identical "how to make money with OpenClaw" SEO posts appeared
  across many differently-branded domains this pass, all citing
  overlapping figures — a classic content-farm/gold-rush signal (see
  Learnings). Also: this is a different agent runtime/ecosystem than
  Claude Code, so it doesn't directly reuse this project's own tokens or
  tooling the way categories #1/#3/#14 do — relevant as market
  intelligence, lower priority as a direct backlog fit for this project.

### 15 (update). Autonomous agent income experiments — additional X/Twitter evidence

Dedicated X-native search (plain `WebSearch`, no `site:` operator) worked
well and surfaced primary-ish threads pass 1's general web search missed:

- "10 People Made $847,000 Last Month Using AI Agents" (Ihtesham Ali,
  X) — claims 3 weeks of sourcing via Discord/Reddit/private communities,
  "verified through Discord DMs, payment screenshots, and analytics
  dashboards." That verification standard is self-reported, not
  independent — same tier as the marketing-adjacent claims elsewhere in
  this file, include as anecdote not fact. Contains the individual case
  studies cited under category #17 above.
- Freelance-platform-specific figures found: entry-level AI-agent-building
  setups $1,500–$3,000 + $500–$2,500/month retainers; high-ticket
  full-service packages $8,000–$20,000 upfront; a freelancer with 5
  retainer clients earning $500–$2,500/month passively on top of new
  project fees. Consistent with, and slightly more conservative than, the
  Upwork figures already in category #3. ([emergent.sh](https://emergent.sh/learn/how-to-make-money-with-ai))
- Reinforces, doesn't change, category #15's core takeaway: real money
  exists, but every credible figure sits next to at least one explicitly
  unverified or self-reported one in the same source — the pattern (mix
  wins with failures, distrust round numbers) holds.
