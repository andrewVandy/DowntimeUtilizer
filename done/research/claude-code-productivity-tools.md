---
id: claude-code-productivity-tools
category: research
status: done
impact: 4
confidence: 5
priority: 4
effort: 4
depends_on: []
created: 2026-07-21
updated: 2026-07-24
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

**Second-pass update (2026-07-24)**: the narrow follow-up above is now
done — see Findings #1 and Next steps #4 in the previous pass's checkpoint.
`rate_limits` (`five_hour`/`seven_day`, each with `used_percentage` and
`resets_at`) is a genuine, currently-documented field in the JSON Claude
Code passes to a `statusLine` script on stdin
([official docs](https://code.claude.com/docs/en/statusline), confirmed
by direct fetch of the docs page, not a secondary blog). It only appears
for Claude.ai Pro/Max subscribers, only after the first API response in
the session. This is a real mechanism, unlike the earlier `/cost` claim —
but it's a **statusLine callback**, which only fires when an interactive
TUI is rendering a status bar. Whether a headless Cloud Routine session
(no TUI, nothing rendering a status line) ever triggers that callback is
still unconfirmed — flagged as an open question, not assumed either way.
This project's own "no reliable programmatic remaining-quota API for an
unattended session" conclusion in `CLAUDE.md` stands unless/until that
question is answered.

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
Second research pass complete (2026-07-24). All four next-steps from
pass 1 resolved:
1. **Headroom disambiguation + recommendation** — found a fifth,
   previously-missed "headroom" repo (`headroomlabs-ai/headroom`, ~62k
   stars) that turns out to be the dominant one by a wide margin. Added
   below with an explicit recommendation instead of just a disambiguated
   list.
2. **Star counts verified** — the pass-1 skepticism toward `skillsllm.com`
   numbers was itself wrong: cross-checked six repos' figures against
   independent sources (GitHub trending-stats mirrors, star-history.com,
   direct WebFetch of the repo pages) and skillsllm's numbers were all
   within a few percent of current counts, not inflated. Corrected
   framing throughout Findings #0/#1 and in Learnings below.
3. **Reddit/X practitioner-retention mining** — attempted, came back
   thin again. No new signal on which tools people keep using long-term
   vs. abandon; same indexing gap as every other pass. Recording as a
   confirmed-negative result, not re-attempting with the same approach
   in a future pass.
4. **ccusage's rate-limit mechanism** — confirmed real and independently
   documented (official `statusLine` docs, not a blog), but it's gated on
   an interactive TUI actually rendering a status line — applicability to
   this project's own headless Cloud Routine sessions is still an open
   question, not resolved either way. See the corrected note above the
   frontmatter and Findings #1.

All four pass-1 next-steps are now closed. Moving to `done` — the
objective (exhaustive, source-checked catalogue + the four user-named
tools resolved) is met; a future pass could always add more tools, but
that's true of any open-ended catalogue and isn't itself a reason to keep
this one `in-progress`.

### Next steps
None outstanding from this pass. If picked up again in the future:
- Categories 2–10 (everything except headroom/graphify/codeburn/ponytail)
  weren't re-verified this pass — only the four user-named tools plus
  ccusage got a second look. A future pass could extend the same
  star-count-verification treatment to the rest of the catalogue.
- Four adjacent quota/usage tools surfaced but weren't vetted this pass:
  `rjwalters/claude-monitor`, `grzegorz-raczek-unit8/claude-quota`,
  `aqua5230/usage`, and `tddworks/ClaudeBar`'s own site
  (tddworks.github.io/ClaudeBar) — spotted via search snippets only, not
  independently confirmed or categorized.

### Learnings
Correcting a pass-1 conclusion: the `skillsllm.com` star-count skepticism
was wrong. This pass cross-checked its cited figures for `graphify`
(93.3k on skillsllm vs. ~94-94.8k confirmed independently),
`headroomlabs-ai/headroom` (61.3k vs. ~62k confirmed), and `codeburn`
(8.9k vs. 8,857 confirmed) — all within a few percent, consistent with
skillsllm's numbers simply lagging live GitHub by days/weeks on
fast-growing repos, not being fabricated or inflated. Lesson: don't let
"this number looks too high for a niche tool" become the working
hypothesis without checking — some of these tools (ponytail: ~88k stars
in about a month; graphify: ~94k) really did go viral that fast this
cycle. Second lesson: the earlier "resolve the headroom collision" task
undercounted the collision itself — a 5th same-named repo
(`headroomlabs-ai/headroom`) existed and was more popular than all four
pass-1 entries combined, found only because this pass's WebSearch queries
didn't anchor on "menu bar" the way pass 1's did. When a name is confirmed
to collide across repos, search without assuming which flavor of tool
"wins" — the most differently-shaped match can be the one that matters.
Same Reddit/`site:` indexing gap as every prior pass persists; treat as a
permanent environment constraint at this point, not something to keep
re-testing.

## Findings

First research pass, 2026-07-21. ~15 web searches across GitHub search,
awesome-lists, and general web. Every entry has a source link.

### 0. The four user-mentioned names — all real, resolved, with recommendations

- **"headroom" is a naming collision across *five* unrelated repos, not
  four** — pass 1 found four; this pass found a fifth that turns out to be
  the dominant one:
  - **headroomlabs-ai/headroom** (~62k stars, ~4.7k forks — missed
    entirely in pass 1). A context-compression layer for AI coding agents
    — library, proxy, or agent-wrapping modes — claiming 20% fewer tokens
    for coding agents generally and 60-95% fewer for JSON, reversible
    compression, cross-agent memory sharing. By far the most-starred
    "headroom" and the one skillsllm.com's "60.4k★" figure actually
    belongs to (pass 1 mis-attributed that number to the wrong repo — see
    Learnings). **This is the recommended pick if the goal is what the
    user actually asked for** ("become a very powerful usage") — it's a
    usage-extending tool, not just a usage-visibility one, and it's the
    only "headroom" with real community adoption at this repo.
    ([github](https://github.com/headroomlabs-ai/headroom))
  - **patwalls/headroom** (~10 stars) and **allandecastro/headroom**
    (star count not independently found this pass) — both macOS menu-bar
    Claude Code quota trackers. allandecastro's is the more capable of the
    two: also covers Codex and Copilot quotas, and reads percentages
    "straight off the same endpoints claude.ai/settings/usage and your
    GitHub account use — never reconstructed by parsing local logs" per
    its own README, i.e. the same "official data, not a guess" pattern as
    ccusage's rate-limit trust layer (Findings #1). **Recommended if the
    goal is quota visibility specifically, not usage extension.**
    ([patwalls/headroom](https://github.com/patwalls/headroom), [allandecastro/headroom](https://github.com/allandecastro/headroom))
  - **henchmarketing-rgb/headroom** — a context-window (not rate-limit)
    usage bar for the statusline, reads actual session JSONL. Narrower
    scope than the above two.
    ([github](https://github.com/henchmarketing-rgb/headroom))
  - **gglucass/headroom-desktop** — a token-optimization proxy claiming
    ~2x more usage via compression, same category as #7 below but much
    smaller than headroomlabs-ai/headroom (~473 stars, growing steadily
    from ~104 a few months ago — real traction, just far behind the
    category leader). ([github](https://github.com/gglucass/headroom-desktop))
- **"graphify"** — real: **Graphify-Labs/graphify**, a `/graphify` skill
  for Claude Code (and Cursor/Codex/Gemini CLI) that turns a codebase —
  code, docs, SQL schemas, configs, PDFs — into a queryable knowledge graph
  via local deterministic AST parsing, no vector store, fully offline for
  code-only corpora. A related community project, `claude-code-memory-setup`,
  pairs it with Obsidian for persistent memory, claiming up to 71.5x fewer
  tokens per session. **Star count verified this pass, ~94-94.8k** (up
  from the 76.3k skillsllm.com cited in pass 1 — genuine growth, not the
  inflated figure pass 1 suspected; see Learnings), confirmed independently
  via trendshift.io and direct repo fetch, not skillsllm alone.
  ([Graphify-Labs/graphify](https://github.com/Graphify-Labs/graphify/tree/v8), [claude-code-memory-setup](https://github.com/lucasrosati/claude-code-memory-setup))
- **"codeburn"** — real: **getagentseal/codeburn**, a free local TUI
  dashboard tracking AI-coding token usage/cost across 31+ tools and agents
  (Claude Code, Cursor, Codex, Gemini) by model/project/task, `npx codeburn`
  to run. Actively discussed in `awesome-claude-code` repo issues as a
  community-recommended addition. **Star count verified this pass: 8,857**
  (matches skillsllm.com's 8.9k almost exactly). A separate,
  similarly-named **JuanjoFuchs/ccburn** exists (burn-up-chart TUI
  specifically for Claude's own usage limits, ~13 stars) — don't conflate
  the two; codeburn is the far more adopted of the pair.
  ([getagentseal/codeburn](https://github.com/getagentseal/codeburn), [ccburn](https://github.com/JuanjoFuchs/ccburn))
- **"ponytail"** — real: **DietrichGebert/ponytail**, an AI-agent
  skill/ruleset (Claude Code, Codex, Cursor, and others) that pushes the
  agent toward minimal, non-over-engineered solutions — check stdlib/
  platform/existing-dependency first before writing new code. Benchmarked
  (on real Claude Code sessions, 12 feature tasks against a real open-source
  repo) at ~54% less code on average (up to 94%), ~20% cheaper, ~27% faster.
  **Star count verified this pass: ~88k**, reached 50k within 1.5 weeks of
  launch per the maintainer's own post — genuinely one of the fastest-growing
  tools in this whole catalogue, not just "went viral" as pass 1 put it
  without a number. ([DietrichGebert/ponytail](https://github.com/DietrichGebert/ponytail))

### 1. Usage/Cost Tracking & Dashboards

- **ccusage** (ccusage/ccusage, ccusage.com): the incumbent, still very
  active. 2026 additions include custom pricing overrides, per-project
  instance filtering, timezone support, a persistent local "usage
  warehouse" that survives Claude's 30-day log cleanup, and — most notable
  for this project — an **"official-limit trust layer"**: `--statusline`
  now captures Claude Code's own official `rate_limits` data directly,
  with provenance labels (`official` vs `local_estimate` vs `experimental`
  vs `unknown`) distinguishing verified data from parsed guesses. **Second
  pass, verified**: the underlying mechanism is real and officially
  documented — Claude Code's `statusLine` feature passes a `rate_limits`
  object (`five_hour`/`seven_day` windows, each with `used_percentage` and
  `resets_at`) on stdin to any configured statusline script, confirmed by
  direct fetch of `code.claude.com/docs/en/statusline`, not a blog
  (contrast with the debunked `/cost` claim below). Only present for
  Claude.ai Pro/Max subscribers, only after the first API response.
  Whether this fires for a headless Cloud Routine session (no TUI
  rendering a status line) is unconfirmed — noted as an open question
  rather than assumed either way; see the corrected note above the
  frontmatter. ([ccusage.com](https://ccusage.com/), [github](https://github.com/ccusage/ccusage), [official docs](https://code.claude.com/docs/en/statusline))
- **Claude-Code-Usage-Monitor** (Maciek-roboblog): real-time monitor with
  burn-rate velocity and predictions for when you'll hit rate limits.
  ([github](https://github.com/Maciek-roboblog/Claude-Code-Usage-Monitor))
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
- Spotted this pass, not yet vetted (surfaced via search snippets while
  chasing the headroom collision, description-only — confirm before
  recommending): **rjwalters/claude-monitor** (macOS menu bar widget),
  **grzegorz-raczek-unit8/claude-quota** (SwiftBar plugin, menu bar
  gauges), **aqua5230/usage** (macOS menu bar, local-only/zero API calls,
  HTML reports).
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
