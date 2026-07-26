---
id: claude-code-productivity-tools
category: research
status: in-progress
impact: 4
confidence: 5
priority: 4
effort: 4
depends_on: []
created: 2026-07-21
updated: 2026-07-26
---

**Correction to this file's first-pass claim, checked against official
docs before committing**: the first pass reported that Claude Code's
`/cost` command was rebuilt (v2.1.92) to surface rate-limit utilization,
sourced from secondary blogs (Medium, finout.io, claudelab.net). Anthropic's
own docs (`code.claude.com/docs/en/costs`) don't corroborate this — they
describe `/usage` (not `/cost`) as the command showing plan/quota bars and
a skill/subagent/plugin usage breakdown, with no mention of `/cost`
gaining rate-limit data. Treat the "`/cost` rebuild" claim as an unverified
blog claim, same skepticism level as the `skillsllm.com` star counts
flagged in Learnings. This does **not** change this project's own
architecture conclusion: `/usage` is interactive/human-read-only (a CLI
command a person types and visually reads), not something an unattended
Cloud Routine session can call programmatically — so the "no reliable
programmatic remaining-quota API" conclusion in this project's `CLAUDE.md`
still holds. `ccusage`'s "official-limit trust layer" (Findings #1) reading
`rate_limits` via `--statusline` is a real, separate mechanism worth a
narrow follow-up look, but is a local-machine statusline integration, not
something available inside a Routine's stateless cloud sandbox either.

**Second correction, pass 2 (2026-07-26), checked by fetching both READMEs
directly**: the "official-limit trust layer" described above was
misattributed to **ccusage** in pass 1. That feature does not exist in
ccusage — its actual `statusline` command is a plain "compact usage
display for status bar hooks (Beta)" with no rate-limit provenance system.
The trust-layer feature (rate_limits capture with `official` /
`local_estimate` / `experimental` / `unknown` provenance labels) belongs to
**Claude-Code-Usage-Monitor** (Maciek-roboblog) instead — confirmed by
fetching `raw.githubusercontent.com/.../README.md` for both projects
directly rather than trusting search snippets. Findings #1 below is
corrected accordingly. Doesn't change this project's own conclusion either
way (a local statusline still isn't reachable by a stateless Cloud
Routine), but anyone acting on pass 1's ccusage recommendation for this
specific feature would have been pointed at the wrong tool.

## Objective

Produce an exhaustive catalogue of third-party tools (GitHub repos,
CLI wrappers, MCP servers, browser/menu-bar apps) that make Claude Code
usage more powerful/productive for an individual user — usage/cost
dashboards, session viewers, git/PR helpers, hooks/skills libraries,
status-line enhancements, prompt/context managers, and anything else in
this niche ecosystem. Not a top-5 list — a full map, so this becomes a
reference this user (and this project's own future backlog items) can
draw from when deciding what to adopt or build.

Requested explicitly by the user, verbatim intent preserved here: "search
github repos for tools to improve my claude code usage to become a very
powerful usage, like headroom, graphify, codeburn, or ponytail. These
kinds of niche tools on github or from other sources that would make me
as a user much more productive in claude code"

Note: "headroom," "graphify," "codeburn," and "ponytail" were given as
example-flavor names, not confirmed real projects — verify whether each
actually exists (and under what name/repo) rather than assuming, the same
way "Stanford CS153" was verified rather than assumed in the sibling
`free-ai-learning-resources` research item.

## Context

Same breadth-first mandate as the sibling research items in this
directory (`ai-monetization-overnight-automation`,
`free-ai-learning-resources`): fine to span multiple passes, checkpoint
coverage vs. gaps, don't stop at a comfortable top-N.

This is meaningfully close to this project's own domain (this repo *is*
a Claude Code automation project), so findings here may directly inform
this project's own tooling, not just the user's general workflow —
flag anything that could plug into Downtime Utilizer itself (e.g. usage
monitoring, since that was an open question in this project's own
original design research).

## Checkpoint

### Latest state
Second research pass complete (2026-07-26). Closed all four of pass 1's
concrete next steps by querying the GitHub API directly (via the `github`
MCP tool's `search_repositories`, `repo:owner/name` exact match) instead of
search snippets or aggregator sites:

1. **Headroom naming collision resolved — it's five repos, not four.**
   Pass 1 missed a fifth: **headroomlabs-ai/headroom** (62,471★, a
   token-compression library/proxy/MCP server — same category as
   `gglucass/headroom-desktop`, not a usage monitor). This is what
   `skillsllm.com`'s "headroom (60.4k★)" figure was actually referring to
   — the number is real, it just belonged to a repo pass 1 hadn't found
   yet, not to any of the four already-catalogued "headroom" projects
   (whose real star counts, GitHub-verified, are 11 / 9 / 68 / 484 — see
   Findings #0, updated).
2. **Star counts verified via GitHub API, not aggregator scraping.**
   `graphify`: 96,017★ (skillsllm's 76.3k was actually an *undercount*, not
   inflated). `ponytail`: 89,475★. `codeburn`: 8,934★. `ccburn`: 94★.
   `ccusage`: 17,465★. `awesome-claude-code`: 50,953★. See Findings — pass 2
   for the full table with repo-age context.
3. **Partial X/Twitter practitioner-sentiment pass.** `ponytail` confirmed
   as genuine organic virality (June 2026), not marketing-farm content —
   found independent, differently-worded threads in English, Portuguese,
   and Spanish all describing the same real experience (agent over-codes,
   this fixes it), a pattern consistent with real word-of-mouth rather than
   the OpenClaw-style near-identical-post content-farm signal flagged in
   the sibling monetization file. Reddit remains blocked (confirmed
   permanent per pass 1 — not re-attempted).
4. **ccusage statusline claim re-checked and corrected, not just
   confirmed.** Fetching both projects' READMEs directly turned up a real
   pass-1 error: the "official-limit trust layer" belongs to
   **Claude-Code-Usage-Monitor**, not ccusage (see corrected note above the
   frontmatter, and Findings #1).

Also surfaced a new cluster of usage-monitor tools not caught in pass 1
(AIQuotaBar and similar — see Findings #1 update) and a notable
cross-cutting caution: several of this ecosystem's most-cited repos show
star-accumulation rates far outside normal organic range for a niche dev
tool (see Learnings). Left `in-progress` — breadth-first mandate, and
next-steps 3 (IDE/orchestration/dotfiles categories are still thin on
verification) and the naming-collision gotcha both generalize beyond
"headroom" and haven't been swept for other collisions yet.

### Next steps
1. Sweep categories 2, 3, 4, 6, 8, 9, 10 (session viewers, git helpers,
   hooks libraries, MCP memory servers, orchestration, IDE integrations,
   dotfiles) the same way category 0/1/7 just got treated this pass:
   GitHub-API-verify star counts and check for un-caught naming collisions
   — this pass only fully re-verified the four user-named tools plus
   usage-tracking and token-compression.
2. The star-velocity anomaly (Learnings) deserves its own explicit
   treatment: pick the 3-4 fastest-growing repos in this file
   (`graphify`, `ponytail`, `headroomlabs-ai/headroom`) and look for
   independent signal beyond star count — actual npm/PyPI download
   numbers, HN/blog discussion volume relative to stars, GitHub's own
   fake-star detection tools (e.g. `star-history.com`'s anomaly view) —
   before recommending any of them to the user as "most popular" without
   that caveat attached.
3. New tools surfaced but not yet written into a Findings section:
   AIQuotaBar (yagcioglutoprak), ai-quota (niederme), aqua5230/usage,
   TokenBar (Nanako0129), claude-monitor (rjwalters) — all usage-monitor
   variants found via a plain WebSearch this pass, not yet given the same
   verify-and-catalogue treatment as the rest of category 1.
4. Direct Reddit/X mining for the *other* three user-named tools
   (headroom, graphify, codeburn) — this pass only did the X sentiment
   check for ponytail.

### Learnings
Same Reddit/`site:` indexing gap as the sibling files, still holds — not
re-attempted this pass since pass 1 already confirmed it's a hard tool-level
block. New pattern this pass: **star-count velocity as its own skepticism
signal**, same family as the OpenClaw content-farm signal in the sibling
monetization file but for a different mechanism (bought/bot stars vs. SEO
content farms). `graphify` (created 2026-04-03) hit 96k stars in ~16
weeks — roughly 6,000 stars/week sustained. `ponytail` (created
2026-06-12) hit 89k stars in ~6.5 weeks — roughly 13,700 stars/week.
`headroomlabs-ai/headroom` (created 2026-01-07) hit 62k in ~29 weeks —
roughly 2,150 stars/week. For comparison, `awesome-claude-code` — a much
more established, community-visible project — averaged roughly 780
stars/week over its full 65-week history to reach 51k, and `ccusage`
(60 weeks old) averaged roughly 290/week to reach 17.5k. Sustained rates
in the multiple-thousands-per-week range for brand-new single-purpose dev
tools are not impossible (genuine viral moments happen) but are far
outside what the more organically-adopted comparison repos show — treat
as a "verify independently before citing as evidence of real-world
adoption" flag on those three specific repos, the same way OpenClaw's
content-farm cluster got flagged, not as proof of fraud. Confirmed again
this pass: aggregator sites (`skillsllm.com`) can cite a real, verifiable
number for a repo that simply wasn't in the catalogue yet — the fix for a
"suspicious" aggregator figure is to search harder for the repo it's
describing, not just to discount the number.

## Findings

First research pass, 2026-07-21. ~15 web searches across GitHub search,
awesome-lists, and general web. Every entry has a source link.

### 0. The four user-mentioned names — all real, resolved

- **"headroom" is a naming collision across five repos, not four** —
  pass 1 found four; pass 2 found the fifth GitHub-API-verified this pass:
  **patwalls/headroom** (11★, macOS menu-bar Claude Code usage, session +
  weekly %), **allandecastro/headroom** (9★, Tauri menu-bar app tracking
  Claude Code + Copilot quotas), **henchmarketing-rgb/headroom** (68★,
  context-window usage bar for the statusline, reads actual session JSONL),
  **gglucass/headroom-desktop** (484★, a token-optimization proxy claiming
  ~2x more usage via compression — same category as #9 below), and
  **headroomlabs-ai/headroom** (62,471★ — GitHub-verified, matches the
  skillsllm.com figure almost exactly; a much larger token-compression
  library/proxy/MCP server, 20% fewer tokens for coding agents / 60-95%
  fewer for JSON, same category as gglucass's but a different, far more
  starred project — missed entirely in pass 1). The skillsllm.com "60.4k★"
  figure flagged with skepticism in pass 1 turned out to be a real number
  for a real repo pass 1 simply hadn't found — see Learnings.
  ([patwalls/headroom](https://github.com/patwalls/headroom), [allandecastro/headroom](https://github.com/allandecastro/headroom), [henchmarketing-rgb/headroom](https://github.com/henchmarketing-rgb/headroom), [gglucass/headroom-desktop](https://github.com/gglucass/headroom-desktop), [headroomlabs-ai/headroom](https://github.com/headroomlabs-ai/headroom))
- **"graphify"** — real: **Graphify-Labs/graphify**, a `/graphify` skill
  for Claude Code (and Cursor/Codex/Gemini CLI) that turns a codebase —
  code, docs, SQL schemas, configs, PDFs — into a queryable knowledge graph
  via local deterministic AST parsing, no vector store, fully offline for
  code-only corpora. A related community project, `claude-code-memory-setup`,
  pairs it with Obsidian for persistent memory, claiming up to 71.5x fewer
  tokens per session. **GitHub-verified star count (pass 2): 96,017★** —
  higher than the skillsllm.com "76.3k★" figure flagged in pass 1, not
  lower; the aggregator undercounted rather than inflated. The count
  itself is real, but see Learnings for why the *growth rate* to reach it
  (created 2026-04-03) is flagged as worth independent verification before
  treating as proof of organic adoption. ([Graphify-Labs/graphify](https://github.com/Graphify-Labs/graphify/tree/v8), [claude-code-memory-setup](https://github.com/lucasrosati/claude-code-memory-setup))
- **"codeburn"** — real: **getagentseal/codeburn**, a free local TUI
  dashboard tracking AI-coding token usage/cost across 31+ tools and agents
  (Claude Code, Cursor, Codex, Gemini) by model/project/task, `npx codeburn`
  to run. Actively discussed in `awesome-claude-code` repo issues as a
  community-recommended addition. A separate, similarly-named
  **JuanjoFuchs/ccburn** exists (burn-up-chart TUI specifically for Claude's
  own usage limits) — don't conflate the two. ([getagentseal/codeburn](https://github.com/getagentseal/codeburn), [ccburn](https://github.com/JuanjoFuchs/ccburn))
- **"ponytail"** — real: **DietrichGebert/ponytail**, an AI-agent
  skill/ruleset (Claude Code, Codex, Cursor, and others) that pushes the
  agent toward minimal, non-over-engineered solutions — check stdlib/
  platform/existing-dependency first before writing new code. Benchmarked
  (on real Claude Code sessions, 12 feature tasks against a real open-source
  repo) at ~54% less code on average (up to 94%), ~20% cheaper, ~27% faster.
  Went viral enough to get independent DEV/Medium writeups analyzing it.
  **GitHub-verified star count (pass 2): 89,475★**, created 2026-06-12 —
  see Learnings for the growth-rate flag. **Pass 2 X/Twitter sentiment
  check**: found independently-worded organic threads in English,
  Portuguese, and Spanish all describing the same real pain point (agent
  over-codes) and the same fix, a pattern consistent with genuine
  word-of-mouth rather than a coordinated content-farm push — the strongest
  organic-adoption signal of any tool in this file so far.
  ([DietrichGebert/ponytail](https://github.com/DietrichGebert/ponytail))

### 1. Usage/Cost Tracking & Dashboards

- **ccusage** (ccusage/ccusage, ccusage.com, **17,465★ GitHub-verified**):
  the incumbent, still very active. 2026 additions include custom pricing
  overrides, per-project instance filtering, timezone support, and a
  persistent local "usage warehouse" that survives Claude's 30-day log
  cleanup. Its `statusline` command (beta) is a compact usage display for
  status-bar hooks — **not** the rate-limit trust layer below; pass 1
  misattributed that feature to this project (see corrected note above the
  frontmatter). ([ccusage.com](https://ccusage.com/), [github](https://github.com/ccusage/ccusage))
- **Claude-Code-Usage-Monitor** (Maciek-roboblog): real-time monitor with
  burn-rate velocity and predictions for when you'll hit rate limits. Also
  the actual source of the **"official-limit trust layer"** — `--statusline`
  captures Claude Code's own official `rate_limits` data directly, with
  provenance labels (`official` vs `local_estimate` vs `experimental` vs
  `unknown`) distinguishing verified data from parsed guesses — corrected
  onto this entry in pass 2 after it was wrongly attributed to ccusage in
  pass 1 (confirmed by fetching both projects' READMEs directly).
  ([github](https://github.com/Maciek-roboblog/Claude-Code-Usage-Monitor))
- **AIQuotaBar** (yagcioglutoprak, 20★): macOS menu-bar app showing Claude.ai
  and ChatGPT usage live, auto-detects sessions from browser cookies (no
  copy-paste), includes a WidgetKit desktop widget. Surfaced this pass
  alongside a wider cluster of similar recent entrants not yet individually
  verified: **ai-quota** (niederme), **aqua5230/usage** (local-only, zero
  API calls, HTML reports), **TokenBar** (Nanako0129, native Swift,
  tracks 25+ agents), **claude-monitor** (rjwalters) — same category as the
  rest of this section, flagged for a future pass to catalogue properly
  rather than folded in here without individual verification.
  ([AIQuotaBar](https://github.com/yagcioglutoprak/AIQuotaBar))
- **claude-usage** (phuryn) and **claude-usage** (ocodista): two unrelated
  local dashboards, both reading Claude Code's local files for token/cost/
  session history; phuryn's adds a Pro/Max progress bar.
  ([phuryn](https://github.com/phuryn/claude-usage), [ocodista](https://github.com/ocodista/claude-usage))
- **codeburn** and **ccburn** — see #0 above.
- **usage-monitor-for-claude** (jens-duttke): portable single-EXE Windows
  tray app, zero config, auditable. ([github](https://github.com/jens-duttke/usage-monitor-for-claude))
- Menu-bar apps (macOS): **ClaudeBar** (tddworks) and **ClaudeBar**
  (kiminmonaco) — two unrelated repos, both tracking Claude/Codex/Copilot/
  Gemini quotas; **claude-usage-bar** (Blimp-Labs, Swift/SwiftUI, shows
  5-hour + 7-day dual bars); **cc-usage-bar** (lionhylra, minimal, opens an
  embedded terminal); **Claude-Usage-Tracker** (hamed-elfayome, native
  Swift/SwiftUI). ([tddworks/ClaudeBar](https://github.com/tddworks/ClaudeBar), [Blimp-Labs](https://github.com/Blimp-Labs/claude-usage-bar))
- **Official baseline, corrected after verification**: secondary blogs
  claimed Claude Code's `/cost` command was rebuilt in v2.1.92 to add
  rate-limit utilization. Checked directly against Anthropic's official
  docs (`code.claude.com/docs/en/costs`), which describe `/usage` — not
  `/cost` — as the command showing plan/quota bars, and don't corroborate
  any `/cost` rate-limit feature. Treat the blog claim as unverified.
  Separately, `/usage`'s quota bars are confirmed real but interactive-only
  (a human reads them in the CLI) — not a programmatic API a Cloud Routine
  could call. This project's own "no reliable programmatic remaining-quota
  API" conclusion stands. ([official docs](https://code.claude.com/docs/en/costs), vs. unverified: [finout.io](https://www.finout.io/blog/claude-code-pricing-2026))

### 2. Session/Transcript Viewers & Exporters

- **claude-code-log** (daaain): processes the entire `~/.claude/projects/`
  tree into linked, navigable HTML/Markdown, one file per session.
  ([github](https://github.com/daaain/claude-code-log))
- **claude-code-trace** (delexw): browse conversations/tool calls/tokens,
  live-tail active sessions, desktop + web + TUI. ([github](https://github.com/delexw/claude-code-trace))
- **claude-code-chat-history-viewer** (Kirushanthan03): styled HTML pages,
  live server mode, dark theme, syntax highlighting. ([github](https://github.com/Kirushanthan03/claude-code-chat-history-viewer))
- **claude-session-viewer** (jtklinger), **cclogviewer** (Brads3290),
  **clog** (HillviewCap, real-time web viewer), **claude-code-transcripts**
  (simonw, mobile-friendly paginated HTML), **cctrace** (jimmc414,
  exports to Markdown + XML), **claude-JSONL-browser** (withLinda,
  web-based multi-file explorer) — all solve the same problem with
  different UI choices; pick based on desired output format (HTML vs TUI
  vs Markdown) rather than feature gaps, since they overlap heavily.
  ([daaain's is the most "processes the whole tree" of the set](https://github.com/daaain/claude-code-log))

### 3. Git / PR / Worktree Helpers

- **Official**: Claude Code's own `--worktree` flag (isolated session per
  branch under `.claude/worktrees/`, can target a PR number/URL directly)
  and the official **Commit Commands plugin**
  (`/plugin install commit-commands@claude-plugins-official`) adding
  `/commit` and `/commit-push-pr`. ([docs](https://code.claude.com/docs/en/worktrees), [plugin](https://claude.com/plugins/commit-commands))
- **xlaude** (Xuanwo): CLI for managing multiple Claude instances against
  git worktrees with session awareness. ([github](https://github.com/Xuanwo/xlaude))
- **@akiojin/claude-worktree** (npm): intuitive worktree-management CLI
  with intelligent branch selection, built for Claude Code/Codex workflows.
- **claude-code-templates** (davila7): includes a `worktree-guide` skill
  with `/worktree-check`, `/worktree-deliver`, `/worktree-cleanup` commands.
  ([github](https://github.com/davila7/claude-code-templates))
- Commit-message generators (community, beyond the official plugin):
  **claude-auto-commit** (0xkaz), **claude-commit** (JohannLai, uses the
  Agent SDK), **claude-commit-vscode** (uaoa), **claude-lazygit**
  (godlyfast, zero-config, Conventional Commits). ([0xkaz](https://github.com/0xkaz/claude-auto-commit))

### 4. Hooks & Skills Libraries

- **awesome-claude-code** (hesreallyhim): the canonical curated list —
  described by its own maintainer approach as curating with judgment
  (broken tools get cut), covering skills, status lines, dev tooling, and
  plugins. Best single starting point in this whole category.
  ([github](https://github.com/hesreallyhim/awesome-claude-code))
- **awesome-claude-skills** — multiple independent curators maintain lists
  under this near-identical name: ComposioHQ (1000+ skills claimed),
  travisvn, BehiSecc — overlapping content, no single canonical winner.
- **claude-skills** (alirezarezvani): 345 skills/agents/plugins across
  30+ agent personas and 8+ coding-agent platforms, engineering through
  business-operations categories. ([github](https://github.com/alirezarezvani/claude-skills))
- Hooks documentation (not a tool, but load-bearing reference): Hidekazu
  Konishi's "Claude Code Hooks: Complete Guide" covers every hook event,
  return channels, and anti-patterns with ready `settings.json` examples.

### 5. Status Line Customizations

- **ccstatusline** (sirmalloc): highly customizable, powerline support,
  themes — one of the most-referenced options. ([github](https://github.com/sirmalloc/ccstatusline))
- **claude-powerline** (Owloops): vim-style powerline with real-time usage
  tracking and git integration built in. ([github](https://github.com/Owloops/claude-powerline))
- **claude-code-status-line** (benabraham): shows context window usage,
  5-hour/weekly quota remainder, model, git branch — directly overlaps
  with the usage-tracking category above. ([github](https://github.com/benabraham/claude-code-status-line))
- **oh-my-claude** (ssenart), **statusline** (b-open-io), **advanced
  statusline** (rz1989s, TOML theme config, "prayer times" as a novelty
  widget), **ClaudeCodeStatusLine** (daniel3303) — all overlapping
  powerline-style options; differentiate by widget set and theme engine,
  not core capability.

### 6. MCP Servers Extending Claude Code (memory/context/task-specific)

- **mcp-memory-keeper** (mkreyman): persistent-memory MCP server
  specifically pitched at the "context window fills up mid-session"
  problem. ([github](https://github.com/mkreyman/mcp-memory-keeper))
- **claude-memory-mcp** (Stig-Johnny): stores decisions, error solutions,
  project context, learnings, session state across conversations —
  conceptually close to this project's own checkpoint-file convention, but
  implemented as an MCP server + presumably a database rather than
  plain git-tracked files.
- **contextforge-mcp** (alfredoizdev): adds semantic search + Git sync +
  team collaboration on top of persistent memory, works across Claude
  Code/Cursor/Copilot. ([github](https://github.com/alfredoizdev/contextforge-mcp))
- **claude-memory** (daringanitch): PostgreSQL + pgvector + FastMCP vector
  memory with semantic search — the most infrastructure-heavy option
  found, appropriate only if a project has real semantic-search needs.
- **memory-mcp** (chenxiaofie), **memory-mcp** (yuvalsuede, adds automatic
  git snapshots), **agentic-semantic-memory-system-mcp** (tristan-mcinnis)
  — smaller/overlapping alternatives in the same space.
- Relevant contrast for this project: Downtime Utilizer intentionally uses
  plain git-tracked Markdown files (see `CLAUDE.md`) instead of an MCP
  memory server, specifically because Cloud Routines get a fresh clone
  with no persistent server state between runs — an MCP memory server
  would need its own always-on backend, which cuts against the "runs
  without your machine on" property Routines were chosen for.

### 7. Context/Memory Managers (token-compression proxies)

- **ClaudeSlim** (apolloraines): local proxy intercepting/compressing API
  calls, claims 60-85% token reduction / 6.5x more usage before rate
  limits, zero modification to Claude Code required, MIT licensed.
  ([github](https://github.com/apolloraines/claudeslim))
- **tamp** (sliday): "50% fewer tokens, zero behavior change" — more
  conservative, specific claim (52.6% input-token reduction measured) than
  some competitors. ([github](https://github.com/sliday/tamp))
- **token-reducer** (Madhan230205): hybrid BM25 + ONNX-vector RAG with AST
  chunking and reranking, claims 90%+ reduction, fully local/no API needed.
- **rtk** (rtk-ai): single Rust binary, zero dependencies, 60-90% claimed
  reduction "on common dev commands" specifically (narrower scope than the
  others). ([github](https://github.com/rtk-ai/rtk))
- **headroom-desktop** (gglucass) — see #0.
- **headroom** (headroomlabs-ai, 62,471★ GitHub-verified) — see #0; the
  fifth, previously-missed "headroom" repo, found pass 2. By far the most
  starred tool in this category — library/proxy/MCP server, 20% fewer
  tokens for coding agents, 60-95% fewer for JSON, same input/output
  answers claimed. See Checkpoint Learnings for the star-velocity caveat
  before treating that star count as adoption evidence on its own.
- Caveat: all percentage claims above are the projects' own, none
  independently benchmarked in this pass — treat as directional, not
  verified, the same way trading-bot income claims were flagged in the
  sibling monetization research file.
- **Directly relevant to this project**: any of these could mechanically
  extend how much a Cloud Routine run accomplishes before hitting a rate
  limit — worth a dedicated evaluation if quota efficiency becomes a
  priority, though they're built for interactive local sessions, not
  verified to work inside a Routine's cloud sandbox.

### 8. Multi-Agent / Orchestration Wrappers

- **Official**: Claude Code's built-in "Agent Teams" — experimental,
  disabled by default, one session as "team lead" coordinating others via
  a shared task list (this is the same primitive visible in this
  conversation's own `TaskCreate`/`TaskList` tools).
- **claude_code_agent_farm** (Dicklesworthstone): runs 20+ agents in
  parallel — automated bug-fixing, best-practices sweeps, lock-based
  coordination, real-time tmux monitoring. The most heavyweight option
  found. ([github](https://github.com/Dicklesworthstone/claude_code_agent_farm))
- **claude-parallel-agents** (sean-rowe): parallel independent-feature
  development via git worktrees, real-time monitoring, auto-restart.
  ([github](https://github.com/sean-rowe/claude-parallel-agents))
- **Claude Fleet** (sethdford): coordination layer aimed at building
  production-grade multi-agent systems.
- "Gas Town" and "Multiclaude" were referenced in secondary coverage as a
  solo-dev-vs-team-usage pair, but neither had a clearly identifiable
  primary GitHub repo surfaced this pass — flagged as unverified rather
  than included as confirmed tools.

### 9. IDE/Editor Integrations Beyond Official

- Official support is VS Code + JetBrains (dedicated plugin, diff viewing,
  selection-context sharing).
- **claudecode.nvim** (coder): the first Neovim integration, reverse-
  engineered from the official VS Code extension, implements the same
  WebSocket-based MCP protocol Claude Code uses to attach to editors.
  Explicitly community-maintained/unaffiliated with Coder the company.
  ([github](https://github.com/coder/claudecode.nvim))
- No other independently-maintained editor integrations (Zed, Sublime,
  etc.) were found with a working implementation — a Zed discussion
  thread exists requesting one, unresolved as of this pass.

### 10. Configuration / Dotfiles Repos

- **awesome-claude-code**'s own `docs/` structure and **my-claude-code-setup**
  (centminmod) are the most-referenced starting templates for a
  CLAUDE.md "memory bank" pattern. ([centminmod](https://github.com/centminmod/my-claude-code-setup))
- **claude-code-dotfiles** (elizabethfuentes12): auto-syncs `~/.claude`
  across machines via git — CLAUDE.md, commands, hooks, settings all kept
  in sync automatically (pull on open, push on close).
  ([github](https://github.com/elizabethfuentes12/claude-code-dotfiles))
- **dotclaude** — two unrelated repos share this name: chan9yu's (OMC
  multi-agent orchestration + plugins + hooks + output styles) and
  poshan0126's (a more minimal standard `.claude/` folder structure with a
  `CLAUDE.template.md`).
- Several individual dev dotfiles repos (vsbuffalo, ryoppippi) were
  referenced as real-world examples of a populated `.claude/` directory
  worth skimming for patterns, rather than tools to install directly.

### Cross-cutting notes

1. **Naming collisions are the single biggest gotcha in this ecosystem** —
   at least three of the four user-mentioned names ("headroom", "graphify",
   "codeburn"/"ccburn") have multiple unrelated same-named or
   confusingly-similar-named projects. Always confirm by description/repo
   owner before installing, not by name alone.
2. **Three genuinely distinct problems get solved by overlapping-looking
   tools**: (a) usage/cost visibility, (b) token/context compression to
   extend usage, (c) session/transcript readability. A user chasing "make
   my usage more powerful" likely wants one tool from (a) and, if quota is
   a real constraint, one from (b) — not one of everything.
3. **This project's own architecture note** (see top of file): a claimed
   `/cost` rate-limit feature did not hold up against official docs on
   verification — this project's `CLAUDE.md` assumption that no
   programmatic remaining-quota API exists stands unchanged. A useful
   general lesson from this research item: SEO/changelog-style blogs about
   Claude Code (finout.io, claudelab.net, and similar) should be
   cross-checked against `code.claude.com/docs` before a claim from them is
   treated as fact, same as the `skillsllm.com` star-count skepticism above.

## Findings — pass 2 (2026-07-26)

GitHub API queries (`repo:owner/name` exact match via `search_repositories`)
for every repo flagged in pass 1's Learnings/Next-steps, plus two direct
README fetches (`raw.githubusercontent.com`) and three targeted WebSearch
passes (ccusage statusline, ponytail X sentiment, headroom disambiguation).
Reddit not re-attempted (confirmed permanent block, pass 1).

### GitHub-verified star counts (vs. pass-1 aggregator/unverified figures)

| Repo | Stars (verified) | Created | Pass-1 figure |
|---|---|---|---|
| Graphify-Labs/graphify | 96,017 | 2026-04-03 | "76.3k★" (skillsllm, unverified) |
| DietrichGebert/ponytail | 89,475 | 2026-06-12 | none cited |
| headroomlabs-ai/headroom | 62,471 | 2026-01-07 | not found in pass 1 at all |
| hesreallyhim/awesome-claude-code | 50,953 | 2025-04-19 | none cited |
| getagentseal/codeburn | 8,934 | 2026-04-13 | none cited |
| ccusage/ccusage | 17,465 | 2025-05-29 | none cited |
| gglucass/headroom-desktop | 484 | 2026-03-30 | none cited |
| henchmarketing-rgb/headroom | 68 | 2026-04-23 | none cited |
| JuanjoFuchs/ccburn | 94 | 2026-01-09 | none cited |
| patwalls/headroom | 11 | 2026-06-09 | none cited |
| allandecastro/headroom | 9 | 2026-05-26 | none cited |

All figures above superseded pass 1's "skillsllm.com star counts looked
inflated, treat with skepticism" framing for `graphify` specifically — the
verified number was *higher* than the aggregator's, not lower. The
`headroom` "60.4k★" figure from pass 1's Learnings turned out to describe
a real fifth repo (`headroomlabs-ai/headroom`) pass 1 hadn't found, not an
inflated number for one of the four already-catalogued ones.

### New finding: star-accumulation velocity as a distinct skepticism signal

See Learnings above (Checkpoint section) for the full reasoning — summary:
`graphify`, `ponytail`, and `headroomlabs-ai/headroom` all show
thousands-of-stars-per-week sustained growth since creation, several times
faster than the two much more established comparison repos
(`awesome-claude-code`, `ccusage`) in this same file. Not proof of
star-buying/bot-farming, but a "verify independently before citing as
adoption evidence" flag in the same family as the OpenClaw content-farm
signal flagged in the sibling `ai-monetization-overnight-automation` file
— a different mechanism (paid/bot stars vs. SEO volume), same underlying
lesson: unusually fast, unusually uniform growth in this ecosystem is
itself a signal worth naming, not just a curiosity.

### New finding: ccusage / Claude-Code-Usage-Monitor feature misattribution

Documented in full in the corrected note above the frontmatter and in
Findings #1. Caught by fetching both projects' actual README files
directly rather than relying on search-result snippets, which is worth
naming as a general lesson for future passes in this file: for any claim
about *which specific tool* has *which specific feature*, fetch that
tool's own README/docs before citing it, even when a search snippet reads
confidently.

### New finding: organic-adoption signal for ponytail via X/Twitter

Documented in Findings #0 (ponytail entry). Independently-worded threads
in three languages describing the same pain point and the same fix is a
stronger organic-signal pattern than anything else surfaced in this file
so far — worth using as the comparison baseline if a future pass wants to
assess whether `graphify` or `headroomlabs-ai/headroom`'s adoption is
similarly organic or not (per the velocity flag above).
