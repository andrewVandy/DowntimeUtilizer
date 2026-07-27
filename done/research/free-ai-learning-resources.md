---
id: free-ai-learning-resources
category: research
status: done
impact: 4
confidence: 5
priority: 4
effort: 5
depends_on: []
created: 2026-07-21
updated: 2026-07-27
---

## Objective

Produce an exhaustive, categorized catalogue of free resources for
learning AI/ML systems — not a top-10 list, a full map of what's out
there, so this file becomes a reference asset in its own right (a
"digital product"/documentation deliverable) and a seed list for future
`backlog/documentation` or `backlog/writing` items (e.g. a curated
learning-path guide built from this).

Requested explicitly by the user, verbatim intent preserved here: "research
as many free resources for learning AI systems as possible. Do the same
kind of research, exhaustive and covering absolutely EVERYTHING. feel free
to work for as long as necessary to compile every resource. I want
courses, like the stanford cs 153 that have brilliant speakers,
educational sites or interactive learning spaces, releases from claude
themselves, etc."

Note: "Stanford CS 153" checked out — it's a real, current course
("Frontier Systems," see `## Findings` #1) with guest lecturers including
Ben Mann (Anthropic cofounder), Jensen Huang, and others. CS25
("Transformers United") is a separate, also-real course with its own
strong guest-speaker lineup from Anthropic/OpenAI/DeepMind — both are
catalogued below.

## Context

Same breadth-first mandate as `ai-monetization-overnight-automation`
(see that file's Context for the general pattern this project uses for
exhaustive research items): this is fine to span multiple passes, should
checkpoint which categories/sources are covered vs. still open, and
should not stop at a comfortable top-N — keep expanding until sources
genuinely dry up.

Categories explicitly requested or clearly implied: university courses
with public lecture videos (especially ones with notable guest speakers),
interactive/hands-on learning platforms, official model-lab educational
releases and documentation (Anthropic, OpenAI, Google DeepMind, Meta),
plus anything else that constitutes a genuine free way to learn AI
systems (books, YouTube channels, MOOCs, official cookbooks/guides,
communities, newsletters, podcasts).

## Checkpoint

### Latest state
First research pass complete: 7 categories, 40+ distinct resources
catalogued in `## Findings`, each with a source link and a free/paid-tier
distinction. The "CS 153" question is resolved (see Objective note) —
it's real, not a mix-up. Judged reasonably exhaustive on the categories
explicitly requested; left `in-progress` rather than `done` because two
gaps remain (see Next steps) that a future pass could close.

Second pass (2026-07-27): closed both gaps left open by the first pass and
added 6 new sections (8-13, ~35 resources) covering previously-
uncatalogued modalities — agent-framework-specific courses (LangChain
Academy, CrewAI, AutoGen), AI safety/alignment courses beyond Anthropic's
own (BlueDot Impact, ARENA, Center for AI Safety, Tübingen/Harvard
university courses), cloud-provider free AI learning paths (Google
Skills, AWS Skill Builder, NVIDIA DLI), curated "awesome-list" GitHub
repos, other free modalities (paper-reading communities, competitive-
learning platforms beyond Kaggle), and a dedicated math-prerequisites
section (linear algebra, calculus, probability/stats, optimization — 12
resources). Reddit access confirmed as a permanent tool-level block (not
an indexing gap), matching the sibling monetization file's finding
exactly. File now has 13 categories and 100+ distinct resources, each
with a source link and free/paid-tier distinction; every category
originally requested by the user is covered, plus substantial bonus
breadth. Judged sufficiently exhaustive — moved to `done`. Several
official course-provider sites (bluedot.org, skills.google,
skillbuilder.aws, nvidia.com, aisafetybook.com, mml-book.github.io,
ocw.mit.edu) returned HTTP 403 to direct WebFetch in this environment;
those entries are flagged inline as corroborated via search snippets
only, not primary-source-verified — a worthwhile spot-check for whoever
next relies on them, but not a reason to hold this file open further.

### Next steps
This file is `done`. Follow-on work now lives in
`backlog/documentation/ai-learning-path-guide.md` (created this pass, per
Next step #3 below) — an ordered beginner→advanced curriculum built from
this catalogue's raw material, rather than further expansion of this flat
list. If a future pass wants to re-open this file instead (e.g. new
categories emerge, or a 403'd source needs re-verification), that's fine
too — nothing here is a hard stop, just a natural completion point.

1. ~~Direct Reddit mining~~ — resolved 2026-07-27: confirmed hard tool-
   level block, not an indexing gap. No further attempts needed.
2. ~~Foundational math prerequisites~~ — resolved 2026-07-27: dedicated
   section 13 added (12 resources: linear algebra, calculus,
   probability/stats, optimization, interactive tools, books).
3. ~~Spin a `backlog/documentation` item for an ordered learning path~~ —
   done this pass, see above.

### Learnings
Same `site:reddit.com` indexing gap as the sibling monetization research
file — broader natural-language queries surfaced aggregator/roundup posts
that *reference* Reddit and YouTube-channel recommendation threads, not
primary discussion. Highest-signal sources this pass: official course
websites/GitHub repos (authoritative on cost/access details), Class
Central (reliably distinguishes free-audit vs. paid-certificate), and
direct searches for specific claims (e.g. searching the exact course
number "CS153" directly, rather than assuming, is what caught that it's
a real current course and not a misremembering).

2026-07-27 pass: Directly re-tested the Reddit question the sibling
monetization file first hit. **Confirmed hard block, reproduced exactly**:
`WebFetch` on `www.reddit.com` returns "Claude Code is unable to fetch
from www.reddit.com" (outright refusal, not a timeout/404), and
`WebSearch` with `allowed_domains:["reddit.com"]` returns an explicit API
400 — "domains are not accessible to our user agent" — pointing at
Anthropic's own crawler-blocking policy page. This is tool/environment-
level, not a fluke of this query, and matches the sibling file's finding
exactly: stop attempting direct Reddit access in future passes. Plain
natural-language `WebSearch` queries mentioning "reddit" (no `site:`/
domain restriction) do work, but return aggregator/blog summaries of what
Reddit supposedly recommends, not primary thread content — useful as a
weak signal, not a substitute for direct access. X/Twitter fared better:
plain-language queries surfaced actual thread content (e.g. a specific
X post cataloguing MIT's free AI book collection), consistent with the
sibling file's finding that X/Twitter is searchable this way while Reddit
is not.

2026-07-27 pass, math prerequisites: this was an easy search space —
official primary sources (MIT OCW course pages, Stanford's own
book-hosting page, official Coursera/DeepLearning.AI pages) surfaced
directly in results, unlike the Reddit gap. Two sources (mml-book.github.io,
ocw.mit.edu) 403'd to direct WebFetch and had to be corroborated via
multiple independent search snippets instead — a reminder that even
well-indexed official sites can be unreachable to WebFetch specifically,
separate from the Reddit-style hard block.

## Findings

First research pass, 2026-07-21. ~25 web searches across official course
sites, Class Central, GitHub, and general web. Every entry has at least
one source link; cost/access basis (fully free vs. free-audit vs.
free-tier) is noted explicitly per entry since "free" is used loosely by
many secondary sources.

### 1. University Courses (public lecture videos)

- **Stanford CS153 — Frontier Systems**: exactly what the user asked
  about. Current, real course on scaling/securing frontier AI
  infrastructure, with guest lectures from **Ben Mann (Anthropic
  cofounder)**, Jensen Huang (NVIDIA), Matthew Prince (Cloudflare), and
  Steve Huffman (Reddit), among others. Final project: build and deploy
  an AI agent from scratch. Some lecture videos public on YouTube.
  ([course site](https://cs153.stanford.edu/), [YouTube example](https://www.youtube.com/watch?v=F_7M4Hc-usM))
- **Stanford CS25 — Transformers United**: now on its 6th iteration (V6);
  guest lectures from OpenAI, Anthropic, Google DeepMind, Meta, NVIDIA,
  and researchers like Andrej Karpathy and Geoffrey Hinton have been
  featured across versions. Fully recorded, livestreamed, over 1M
  cumulative YouTube views; recordings posted within 1-2 weeks of each
  lecture. ([course site](https://web.stanford.edu/class/cs25/), [recordings](https://web.stanford.edu/class/cs25/recordings/))
- **Stanford CS229 — Machine Learning**: Andrew Ng's original course,
  multiple free full YouTube playlists (Autumn 2018 is the most complete,
  27+ hours). Core ML fundamentals: supervised/unsupervised learning,
  learning theory, RL. ([YouTube playlist](https://www.youtube.com/playlist?list=PLoROMvodv4rMiGQp3WXShtMGgzqpfVfbU), [site](https://cs229.stanford.edu/))
- **Stanford CS230 — Deep Learning**: Andrew Ng, free YouTube playlist
  (Autumn 2018) covering CNNs, RNNs/LSTM, Adam, dropout, batchnorm,
  project strategy. Current-year recordings are enrolled-student-only via
  Canvas, but the public playlist stands on its own.
  ([YouTube playlist](https://www.youtube.com/playlist?list=PLoROMvodv4rOABXSygHTsbvUz4G_YQhOb))
- **Stanford CS231n — CNNs for Visual Recognition**: famous computer
  vision course; free YouTube playlists exist for older years (2025
  version also on YouTube), slides/notes permanently free at
  cs231n.github.io regardless of video-year restrictions.
  ([notes](https://cs231n.github.io/), [2025 playlist](https://www.youtube.com/playlist?list=PLoROMvodv4rOmsNzYBMe0gJY2XS8AQg16))
- **Stanford CS224N — NLP with Deep Learning**: free full YouTube
  playlists (2023/2024 versions), covers DL fundamentals through modern
  LLMs; slides and assignments public every year regardless of video
  availability. ([2023 playlist](https://www.youtube.com/playlist?list=PLoROMvodv4rMFqRtEuo6SGjY4XbRIVRd4), [site](https://web.stanford.edu/class/cs224n/))
- **Stanford CS234 — Reinforcement Learning**: free YouTube playlists for
  both Winter 2019 and Spring 2024 (Emma Brunskill); core RL from
  fundamentals to offline RL and multi-agent play.
  ([2019 playlist](https://www.youtube.com/playlist?list=PLoROMvodv4rOSOPzutgyCTapiGlY2Nd8u))
- **MIT 6.S191 — Introduction to Deep Learning**: MIT's flagship intro
  deep learning course; lectures, slides, and labs fully open-sourced
  every year at introtodeeplearning.com (MIT-licensed), YouTube playlist
  updated annually. Covers RNNs, transformers/attention, CNNs, generative
  modeling, RL, LLMs. ([site](https://introtodeeplearning.com/), [YouTube](https://www.youtube.com/playlist?list=PLtBw6njQRU-rwp5__7C0oIVt26ZgjG9NI))
- **MIT OpenCourseWare 6.034 — Artificial Intelligence**: classic Patrick
  Winston-taught intro to AI (knowledge representation, search, learning);
  free lecture videos, notes, exams, no registration.
  ([OCW](https://ocw.mit.edu/courses/6-034-artificial-intelligence-fall-2010/))
- **Berkeley CS182 — Deep Learning / Deep Neural Networks**: free YouTube
  playlist for Spring 2021; more recent offerings restrict video access to
  @berkeley.edu accounts, but the open playlist covers optimization,
  backprop, CNNs, RNNs, transformers, RL, GANs, meta-learning in full.
  ([playlist](https://www.youtube.com/playlist?list=PL_iWQOsE6TfVmKkQHucjPAoRtIJYt8a5A))
- **Berkeley CS285 — Deep Reinforcement Learning (Sergey Levine)**: free
  YouTube playlists for multiple years (Fall 2020/2021); the canonical
  advanced deep RL course, requires prior ML/MDP background.
  ([course site](http://rail.eecs.berkeley.edu/deeprlcourse/), [playlist](https://www.youtube.com/playlist?list=PL_iWQOsE6TfXxKgI1GgyV1B_Xa0DxE5eH))
- **CMU 11-785 — Deep Learning**: free lecture videos on YouTube; broad
  deep-neural-network fundamentals and applications course.
  ([CMU channel](https://www.youtube.com/channel/UC8hYZGEkI2dDO8scT8C5UQA))
- Why these matter as a category: multi-year public YouTube archives mean
  even when the *current* offering is gated to enrolled students, prior
  years remain fully free and usually still current enough to be useful —
  check both the live course site and YouTube/Class Central for archived
  versions before assuming a course is inaccessible.
- **MIT 18.06(SC) — Linear Algebra (Gilbert Strang)**: found this pass via
  natural-language search surfacing it as a recurring Reddit/community
  recommendation. Fills the math-prerequisite gap flagged in the previous
  pass's Next steps — full free lecture videos, summary notes per lecture,
  and recitation problem-solving videos, OCW Scholar format built for
  independent learners, 10M+ visits since 2002. Directly relevant since
  most DL/ML courses above assume this math rather than teach it.
  ([OCW](https://ocw.mit.edu/courses/18-06sc-linear-algebra-fall-2011/))
- **NYU DS-GA 1008 — Deep Learning (Yann LeCun & Alfredo Canziani)**: found
  this pass. Free, fully online, closed-captioned lecture videos + written
  overviews + executable PyTorch Jupyter notebooks; covers supervised/
  self-supervised learning, embeddings, metric learning, CNNs/RNNs, with
  CV/NLP/speech applications. Notable as a free course co-taught by a
  Turing Award winner. ([course site](https://atcold.github.io/pytorch-Deep-Learning/), [YouTube](https://www.youtube.com/playlist?list=PLLHTzKZzVU9e6xUfG10TkTWApKSZCzuBI))

### 2. Official AI-Lab Educational Releases & Research

- **Anthropic Academy** (learn.anthropic.com or via docs): ~20 free
  courses as of mid-2026, all free registration, certificates on
  completion — Claude 101, Claude Code 101, Claude Platform 101, Building
  with the Claude API, AI agent frameworks, and more, organized as
  learning paths from zero technical background upward.
  ([overview](https://beginnersinai.org/anthropic-academy-courses/), [ranked list](https://spectrumailab.com/blog/anthropic-academy-13-free-courses-ranked-2026))
- **Anthropic's Prompt Engineering Interactive Tutorial** (GitHub):
  official, free, 9 chapters + appendix, hands-on exercises with a live
  "Example Playground" per lesson, uses Claude 3 Haiku. Available as
  Jupyter notebooks, a Google Sheets version, and a couple of independent
  interactive-web ports. ([repo](https://github.com/anthropics/prompt-eng-interactive-tutorial))
- **Claude Cookbooks** (GitHub, `anthropics/claude-cookbooks`): official
  code recipes — classification, RAG, summarization, tool use, PDF
  handling, image generation — free, actively maintained, Python-based but
  concepts are language-agnostic. ([repo](https://github.com/anthropics/claude-cookbooks))
- **Anthropic's own model/alignment research, published openly** — the
  closest thing to "releases from Claude themselves" the user asked about:
  - **Claude's Constitution**: Anthropic's published document of the
    principles used to train Claude's behavior, publicly posted and
    updated (latest major update January 2026). ([news post](https://www.anthropic.com/news/claude-new-constitution))
  - **Transformer Circuits Thread** (transformer-circuits.pub): the
    Anthropic interpretability team's ongoing, free, interactive
    publication on mechanistic interpretability — reverse-engineering what
    happens inside transformers. Includes "A Mathematical Framework for
    Transformer Circuits" and monthly "Circuits Updates."
    ([site](https://transformer-circuits.pub/))
  - **Alignment Science Blog** (alignment.anthropic.com): Anthropic's
    alignment research team's public writing on steering/evaluating
    powerful models. ([blog](https://alignment.anthropic.com/))
- **OpenAI Academy**: free, self-paced, ChatGPT-account-gated (for
  progress tracking/certificates), covers AI fundamentals through applied
  agents/workflows. ([help center](https://help.openai.com/en/articles/20001270-openai-academy-courses))
- **OpenAI Cookbook** (GitHub, 73k+ stars): the reference for building
  with the OpenAI API — embeddings, semantic search, fine-tuning,
  function calling, agents. Free, requires an OpenAI account for running
  examples live. ([repo](https://github.com/openai/openai-cookbook))
- **Google's Machine Learning Crash Course**: free, no sign-up, no
  paywall, ~15 hours, recently expanded to cover LLMs, AutoML, responsible
  AI, with interactive in-browser visualizations. ([course](https://developers.google.com/machine-learning/crash-course))
- **Google DeepMind — AI Research Foundations** (via Google Skills): free
  curriculum on building/fine-tuning language models from the ground up.
  ([Google Skills](https://www.skills.google/collections/deepmind))
- **Google DeepMind — Educational** (GitHub Colab notebooks): free,
  beginner-friendly interactive tutorials from foundational Python through
  supervised/unsupervised/RL concepts.
- **Experience AI** (DeepMind + Raspberry Pi Foundation): free AI
  curriculum for ages 11-14, lesson plans/slides/videos, used in 180
  countries, 19 languages — notable as the most accessible entry point of
  anything in this list. ([site](https://experience-ai.org/en/))
- **Meta AI Blog** (ai.meta.com/blog): official research/infra
  announcements and papers, free; Llama models themselves are free to
  download for research/most commercial use, with third-party (DataCamp,
  Hugging Face) tutorials for fine-tuning/RAG/deployment rather than an
  official Meta "course." ([blog](https://ai.meta.com/blog/))

### 3. Interactive / Hands-On Learning Platforms

- **Kaggle Learn**: free micro-courses (a few hours each), no cost, with
  completion certificates — Python, Intro/Intermediate ML, Pandas, Data
  Viz, Time Series, Data Cleaning, AI Ethics, Geospatial Analysis, ML
  Explainability, Game AI & RL. ([kaggle.com/learn](https://www.kaggle.com/learn))
- **Hugging Face courses** (all free, self-paced, on huggingface.co/learn):
  LLM/NLP Course (Transformers, Datasets, Tokenizers, Accelerate), Deep
  RL Course (Stable Baselines3, CleanRL, trains agents in real game
  environments), Diffusion Models Course, AI Agents Course (smol-agents,
  LlamaIndex, LangGraph). ([agents course](https://huggingface.co/learn/agents-course/en/unit0/introduction), [deep RL course](https://huggingface.co/learn/deep-rl-course/en/unit0/introduction))
- **fast.ai — Practical Deep Learning for Coders**: free, 9 lessons
  (~90 min each), code-first (not math-first), uses free compute (Kaggle
  Notebooks/Paperspace Gradient), companion free book, active community
  forum. ([course.fast.ai](https://course.fast.ai/))
- **DeepLearning.AI short courses**: 70+ free video modules (1-2 hrs
  each) — prompt engineering, RAG, LangChain, LlamaIndex, fine-tuning,
  safety, multi-agent systems, Andrew Ng's Agentic AI course. **Caveat**:
  videos are free, but labs/quizzes/certificates now require a paid Pro
  membership ($25/mo) as of this pass — verify current terms before
  assuming full-course access is free. ([deeplearning.ai](https://www.deeplearning.ai/))
- **Full Stack Deep Learning**: free forever, all lectures/labs — bridges
  academic ML knowledge to production systems (deployment, infra,
  troubleshooting, team org). Assumes prior DL-fundamentals knowledge.
  ([site](https://fullstackdeeplearning.com/))

### 4. Free Books

- **Dive into Deep Learning** (d2l.ai): fully free, interactive (math +
  code + prose together, runnable notebooks), adopted at 500+
  universities including Stanford/MIT/Harvard/Cambridge.
  ([d2l.ai](https://d2l.ai/))
- **Neural Networks and Deep Learning** (Michael Nielsen):
  free, beginner-friendly, builds intuition via the handwritten-digit
  recognition problem; covers backprop, why deep nets are hard to train.
  ([neuralnetworksanddeeplearning.com](http://neuralnetworksanddeeplearning.com/))
- **Deep Learning** (Goodfellow, Bengio, Courville — "the MIT Press
  book"): complete free HTML version, the standard theoretical reference
  text. ([deeplearningbook.org](https://www.deeplearningbook.org/))
- fast.ai's companion book ("the fastai book") is free online alongside
  the course (see #3).
- **MIT Open Learning's free AI book collection**: found this pass via an
  X/Twitter thread and corroborated directly on MIT's own site — a curated
  set of ~12-13 free full-text books/courses spanning Foundations of
  Machine Learning, Understanding Deep Learning, Machine Learning Systems,
  Algorithms for ML, Deep Learning, Reinforcement Learning (incl.
  Sutton & Barto), Distributional RL, Multi-Agent Systems, Fairness in ML,
  and Probabilistic ML (two parts). Genuinely new find — a single curated
  jumping-off point rather than one book. ([MIT Open Learning](https://openlearning.mit.edu/news/13-foundational-ai-courses-resources-mit), [X thread](https://x.com/cyrilXBT/status/2072537498924802279))

### 5. YouTube Channels/Creators

- **Andrej Karpathy — "Neural Networks: Zero to Hero"**: free course-as-
  playlist, builds neural nets from scratch in code up through GPT,
  including a from-scratch tokenizer. Widely regarded as one of the best
  hands-on deep-learning tutorials available anywhere, free or paid.
  ([playlist](https://www.youtube.com/playlist?list=PLXYLzZ3XzIbi4lL43O6fIU_ojuZwBO6vi), [repo](https://github.com/karpathy/nn-zero-to-hero))
- **3Blue1Brown — Neural Networks / Deep Learning series** (Grant
  Sanderson): the definitive visual-intuition series for the math behind
  neural nets and transformers; also has a separate "Essence of Linear
  Algebra" series covering the math prerequisite.
  ([playlist](https://www.youtube.com/playlist?list=PLZZWrBYkx7Otcjr3eCLZDCgfpqnxMY29s))
- **Two Minute Papers**: short, accessible summaries of new ML/AI
  research papers — good for staying current without reading full papers.
- **Yannic Kilcher**: long-form deep-dive paper walkthroughs (LLMs, RL,
  NLP architectures) for a more advanced/research-literate audience.
- **StatQuest (Josh Starmer)**: the math/statistics *underneath* ML
  algorithms, explained simply — good complement to the more
  code-first/paper-first channels above.
- **sentdex (Harrison Kinsley)**: applied, code-heavy Python ML/DL
  tutorials, long-running channel with a large back catalogue.
- **Sebastian Raschka**: LLM training/fine-tuning-focused content,
  surfaced repeatedly as a recommended channel alongside the above.
- **Serrano.Academy (Luis Serrano)**: found this pass. 180k+ subscribers,
  ex-Google/Apple/Udacity/Cohere educator, author of "Grokking Machine
  Learning" — teaches via illustrations/analogies rather than formulas;
  covers ML fundamentals, probability/stats, and recommendation-system
  math. Good complement to StatQuest for a more visual/intuition-first
  angle on the same underlying math.
  ([channel](https://www.youtube.com/@SerranoAcademy))

### 6. MOOCs / Free-Audit Courses

- **Coursera — Machine Learning Specialization** (Andrew Ng /
  DeepLearning.AI + Stanford Online): free to audit (no certificate);
  4.8M+ learners since 2012 lineage. ([specialization](https://www.coursera.org/specializations/machine-learning-introduction))
- **Coursera — Deep Learning Specialization** (Andrew Ng /
  DeepLearning.AI): free to audit per-course (not as one bundled
  specialization); financial aid available for full paid access.
  ([specialization](https://www.coursera.org/specializations/deep-learning))
- **edX** — AI/ML courses from Harvard, MIT, IBM, Microsoft; free to
  audit, browse at edx.org/learn/artificial-intelligence and
  edx.org/learn/machine-learning.
- **Elements of AI** (University of Helsinki + MinnaLearn): free, ~30
  hours across 6 modules, no math/programming required, 1M+ learners in
  170 countries, 26 languages, optional LinkedIn certificate.
  ([elementsofai.com](https://www.elementsofai.com/))
- **Microsoft Learn — AI learning paths**: 100% free, no certificate
  paywall found — Azure AI Fundamentals (AI-900), Intro to AI on Azure,
  Generative AI (Azure AI Foundry), interactive labs built in.
  ([AI-900 path](https://learn.microsoft.com/en-us/training/courses/embark-ai-journey-free-ai-tools-microsoft-education-3hr))

### 7. Communities, Newsletters, Podcasts (for staying current)

- **r/MachineLearning, r/learnmachinelearning**: the two most-recommended
  AI subreddits across secondary sources. **Coverage caveat, now
  confirmed (2026-07-27 pass)**: direct access is a hard tool-level block
  in this environment, not a search-indexing gap — `WebFetch` on
  reddit.com is refused outright and `WebSearch` with
  `allowed_domains:["reddit.com"]` errors with an explicit 400 (Reddit
  blocks Anthropic's crawler user-agent). Matches the sibling
  monetization file's finding exactly; see Learnings. Recommendations for
  these subs continue to come in secondhand via aggregator posts, not
  primary threads, and that will remain true for any future pass in this
  environment.
- **Papers with Code**: pairs arXiv papers with their code implementations
  and benchmark leaderboards — standard reference for "what's SOTA and is
  there code."
- **arXiv** (arxiv.org, cs.CL/cs.LG/cs.AI categories): the primary source
  new research lands in before/alongside conference publication; free,
  no login.
- **Import AI** (Jack Clark, Anthropic cofounder): long-running newsletter
  mixing technical AI developments with policy commentary — notable as an
  Anthropic-adjacent voice specifically.
- **Podcasts**: *This Week in Machine Learning/AI* (Sam Charrington, long-
  running practitioner interviews), *Machine Learning Street Talk* (Tim
  Scarfe, safety/philosophy-leaning researcher interviews) — both surfaced
  repeatedly as top recommendations.

### 8. Agent-Building & Framework-Specific Courses

- **LangChain Academy** (academy.langchain.com, repo:
  `langchain-ai/langchain-academy`): official, fully free, MIT-licensed.
  Modules 0-6 progress from setup through LangGraph fundamentals
  (state, memory, human-in-the-loop) to agent deployment; Jupyter
  notebooks + LangGraph Studio visualization. Newer standalone courses
  ("Intro to LangGraph," "LangGraph Essentials," "Deep Research with
  LangGraph") also listed on the Academy site. Verified via GitHub repo
  README (Academy site itself 403'd to WebFetch).
  ([repo](https://github.com/langchain-ai/langchain-academy), [academy site](https://academy.langchain.com/))
- **CrewAI**: no single official free "course" as polished as LangChain's,
  but `learn.crewai.com` hosts free documentation-as-course material, and
  DeepLearning.AI's "Multi AI Agent Systems with CrewAI" (see #3 for the
  free-video/paid-lab caveat) is CrewAI-official-adjacent (built with
  CrewAI's founder). CrewAI itself is open-source/free to use.
  ([learn.crewai.com](https://learn.crewai.com/), [DLAI course](https://www.deeplearning.ai/courses/multi-ai-agent-systems-with-crewai))
- **Microsoft AutoGen**: official docs/tutorials free at
  microsoft.github.io/autogen — **caveat**: AutoGen is now in maintenance
  mode; Microsoft is steering new projects toward "Microsoft Agent
  Framework" instead, with an official migration guide.
  ([docs](https://microsoft.github.io/autogen/0.2/docs/Getting-Started/), [repo](https://github.com/microsoft/autogen), [migration guide](https://learn.microsoft.com/en-us/agent-framework/migration-guide/from-autogen/))
- Hugging Face's **AI Agents Course** (already in #3) also covers
  LangGraph and smol-agents hands-on, functioning as a second free
  framework-agnostic agent-building path.

### 9. AI Safety & Alignment (beyond Anthropic's own)

- **BlueDot Impact — AI Safety Fundamentals** (bluedot.org/courses):
  cohort-based, largely free courses developed with Oxford, OpenAI, and
  the Centre for the Governance of AI — Technical AI Safety, AGI
  Strategy (pay-what-you-want), Technical AI Safety Project Sprint.
  Small cohorts (~20), expert-led, 7,000+ trained since 2022. Site
  returned 403 to direct WebFetch; corroborated via search snippets
  from bluedot.org's own course pages plus third-party coverage.
  ([courses](https://bluedot.org/courses), [community](https://bluedot.org/our-community))
- **ARENA (Alignment Research Engineer Accelerator)**: curriculum fully
  free/open online for self-study (in-person London bootcamp is
  selective/funded separately). Four chapters — DL fundamentals,
  transformer mechanistic interpretability (TransformerLens, GPT-2
  circuits), RL (DQN, PPO, RLHF), and training-at-scale (distributed
  training, quantization). Verified via GitHub repo.
  ([learn site](https://learn.arena.education/), [repo](https://github.com/callummcdougall/ARENA_2.0))
- **Center for AI Safety — "AI Safety, Ethics, and Society" textbook +
  virtual course** (aisafetybook.com): free curriculum covering
  catastrophic AI risk, malicious use, AI race dynamics, organizational
  risk, plus ML/scaling-laws fundamentals — could not verify site
  directly (403 to WebFetch), only via search snippet, so treat as
  unconfirmed pending a future pass.
- **University AI safety courses with public materials**: Tübingen's
  "AI Safety, Security and Alignment" (lecture recordings + materials
  on GitHub, `aisa-group/tue-ai-safety-course`) and Harvard's CS 2881
  "AI Safety" (Fall 2026, per boazbk.github.io/mltheoryseminar) —
  both surfaced with public syllabi; access to recordings varies by
  course, unlike ARENA/BlueDot these are standard university courses
  first and free-to-the-public second.
  ([Tübingen repo](https://github.com/aisa-group/tue-ai-safety-course), [Harvard CS2881](https://boazbk.github.io/mltheoryseminar/))

### 10. Cloud Provider Free AI/ML Learning Paths (beyond Microsoft Learn)

- **Google Skills (formerly Cloud Skills Boost)**: "Introduction to
  Generative AI" learning path — 5 short courses (Generative AI,
  Responsible AI, LLMs, Image Generation, Transformer Models, each
  under 45 min) entirely on the free tier, no credits needed. The
  companion "Generative AI for Developers" advanced path requires
  completing the free prerequisites but its hands-on labs (Vertex AI,
  Generative AI Studio) need paid Google Cloud credits — same
  free-intro/paid-hands-on-labs split seen elsewhere in this file. Site
  403'd to direct WebFetch; based on search snippets from skills.google
  and secondary coverage.
  ([intro path](https://www.skills.google/paths/118), [advanced path](https://www.skills.google/paths/183))
- **AWS Skill Builder**: 600+ free digital courses overall, 100+
  specifically AI/ML/generative-AI, ranging from self-paced fundamentals
  to structured "Learning Plans" (e.g. the Machine Learning Learning
  Plan) and AWS Certification prep. Free tier covers course content;
  certification exams themselves are paid. Site 403'd to WebFetch;
  based on search snippets and the AWS Training blog.
  ([skillbuilder.aws](https://skillbuilder.aws/), [ML skills blog post](https://aws.amazon.com/blogs/training-and-certification/building-ml-skills-from-zero/))
- **NVIDIA Deep Learning Institute (DLI)**: 21+ courses free as of this
  pass (filter "Free Courses" at learn.nvidia.com after free account
  signup) — includes "Building RAG Agents with LLMs" and "Generative AI
  Explained." Paid courses add GPU-lab time/certificates beyond what
  free tier includes. Site 403'd to direct WebFetch; based on search
  snippets. ([learn.nvidia.com](https://learn.nvidia.com/), [overview](https://www.nvidia.com/en-us/training/online/))

### 11. Curated "Awesome List" Repos (free resource maps)

- **awesome-machine-learning** (`josephmisiti/awesome-machine-learning`,
  the original/most-forked version): curated ML frameworks/libraries by
  ~30 programming languages, plus linked sub-lists for free ML books,
  courses, blogs/newsletters, conferences, and meetups. Verified via
  direct WebFetch of the repo. ([repo](https://github.com/josephmisiti/awesome-machine-learning))
- **awesome-production-machine-learning** (`EthicalML/awesome-production-machine-learning`,
  20.8k stars): curated MLOps tooling — deployment, monitoring,
  versioning, scaling, plus explainability/privacy/responsible-AI tool
  categories. Complements the theory-focused list above with a
  production/engineering-focused map. Verified via direct WebFetch.
  ([repo](https://github.com/EthicalML/awesome-production-machine-learning))
- **ZhiningLiu1998/awesome-machine-learning-resources**: a meta-list of
  other awesome-lists across ML subtopics (paradigms, tasks,
  applications, ethics, datasets, frameworks) — useful as a map of maps
  if the two above don't cover a specific niche.
  ([repo](https://github.com/ZhiningLiu1998/awesome-machine-learning-resources))

### 12. Other Free Learning Modalities

- **Latent Space (swyx et al.)**: not a formal "university" but the
  community behind the AI Engineer World's Fair conference; free Discord
  community running a weekly **LLM Paper Club** (unrecorded Zoom,
  practitioner-run paper discussions) plus a widely-followed newsletter/
  podcast (already loosely adjacent to #7). No confirmed formal "Latent
  Space University" curriculum found this pass — treat that name as
  aspirational/informal rather than a concrete free course.
  ([community](https://www.latent.space/p/community))
- **ML Collective — "Deep Learning: Classics and Trends" (DLCT)**: free,
  running since 2018, weekly Zoom paper-reading sessions, usually
  presented by the paper's own authors — subscribe by email for links.
  ([mlcollective.org/dlct](https://mlcollective.org/dlct/))
- **Competitive-learning platforms beyond Kaggle**: **Zindi** (Africa-
  focused, already implied but confirming distinct from Kaggle),
  **DrivenData** (social-good-focused competitions), **CodaLab**
  (open-source, academic/conference-hosted competitions), **Numerai**
  (ongoing weekly tournament on obfuscated financial data, free to
  enter), **AIcrowd** and **Analytics Vidhya Hackathons** — all free to
  participate, useful as applied-practice alternatives/supplements to
  Kaggle for learners who've outgrown Kaggle Learn's micro-courses.

### 13. Math Prerequisites

Flagged as a gap in the first pass (3Blue1Brown's Essence of Linear
Algebra, Khan Academy surfaced only incidentally). MIT 18.06 (Strang)
is covered in section 1 above; this section covers the rest — calculus,
probability/statistics, optimization, and interactive/book resources —
closing Next steps #2 in full.

- **MIT OCW 18.01/18.02 — Single & Multivariable Calculus**: free video
  lectures, notes, problem sets, exams with solutions; standard
  prerequisite pair for gradient-based ML math.
  ([OCW hub](https://ocw.mit.edu/courses/mathematics/))
- **MIT OCW 6.041/18.05 — Probability and Statistics**: two related free
  tracks — 6.041 (Tsitsiklis, EECS-flavored, videos + recitations + TA
  help videos) and 18.05 (more applied: Bayesian inference, hypothesis
  testing, confidence intervals, linear regression; single-variable
  calculus is its only prerequisite). Both fully free, no login.
  ([6.041](https://ocw.mit.edu/courses/6-041sc-probabilistic-systems-analysis-and-applied-probability-fall-2013/), [18.05](https://ocw.mit.edu/courses/18-05-introduction-to-probability-and-statistics-spring-2022/))
- **Stanford EE364A — Convex Optimization (Boyd & Vandenberghe)**: the
  standard optimization course/reference for ML. Full textbook free
  online (Cambridge UP authorized web posting); course videos/slides via
  Stanford Engineering Everywhere. Book is free forever, no registration;
  SEE video access may require free registration.
  ([book](https://stanford.edu/~boyd/cvxbook/), [SEE course](https://see.stanford.edu/Course/EE364A))
- **3Blue1Brown — "Essence of Calculus"**: companion series to the
  already-listed Essence of Linear Algebra; same visual-intuition
  approach applied to derivatives, chain/product rules, integrals, and
  Taylor series. Free forever, no account needed.
  ([playlist](https://www.youtube.com/playlist?list=PLZHQObOWTQDMsr9K-rj53DwVRMYO3t5Yr))
- **Immersive Math — "Immersive Linear Algebra"**: free interactive
  online textbook (Ström, Åström, Akenine-Möller), billed as the first
  linear-algebra book with fully manipulable interactive figures. Fully
  free, no login. ([immersivemath.com/ila](https://immersivemath.com/ila/))
- **Seeing Theory (Brown University)**: free, D3.js-based interactive
  visual introduction to probability and statistics — distributions,
  sampling, the CLT, confidence intervals, hypothesis testing, Bayesian
  inference. No longer actively maintained but still hosted and fully
  usable. ([seeing-theory.brown.edu](https://seeing-theory.brown.edu/))
- **"Mathematics for Machine Learning"** (Deisenroth, Faisal, Ong;
  Cambridge UP, 2020): free full-text PDF authorized by the publisher
  for personal use, covers linear algebra, analytic geometry, matrix
  decompositions, vector calculus, probability/distributions, and
  optimization specifically framed around ML use.
  ([book site](https://mml-book.github.io/), [PDF](https://mml-book.github.io/book/mml-book.pdf))
- **Coursera — "Mathematics for Machine Learning" Specialization**
  (Imperial College London): 3 courses — Linear Algebra, Multivariate
  Calculus, Dimensionality Reduction/PCA — free to audit, paid
  certificate.
  ([specialization](https://www.coursera.org/specializations/mathematics-machine-learning))
- **Coursera — "Mathematics for Machine Learning and Data Science"**
  (DeepLearning.AI, Luis Serrano): calculus, linear algebra, statistics,
  and probability together with Python labs. Free to audit; first module
  fully previewable without enrolling; certificate is paid.
  ([specialization](https://www.deeplearning.ai/courses/mathematics-for-machine-learning-and-data-science-specialization/))
- **Khan Academy — Linear Algebra, Calculus 1/2, Multivariable Calculus,
  Statistics & Probability**: each a fully-built free curriculum (videos
  + articles + practice problems with instant feedback), no subscription,
  no ads, no login required. Confirms/expands the incidental mention from
  the first pass. ([khanacademy.org](https://www.khanacademy.org/))
- **Paul's Online Math Notes (Lamar University)**: free, downloadable-PDF
  lecture notes for Calculus I/II/III and Differential Equations, written
  for self-study rather than just enrolled students.
  ([tutorial.math.lamar.edu](https://tutorial.math.lamar.edu/))
- Cross-reference: **StatQuest** and **Serrano.Academy** (both already
  listed under YouTube Channels, section 5) are also strong free
  stats-for-ML video resources — worth revisiting from this
  math-prerequisites angle specifically.

**Coverage note**: `mml-book.github.io` and `ocw.mit.edu` returned HTTP
403 to direct WebFetch in this environment; those two entries are
corroborated via multiple independent WebSearch snippets rather than a
direct primary-source fetch, slightly lower-confidence than entries
elsewhere in this file that were WebFetch-verified directly.

### Cross-cutting notes

1. **"Free" has at least three tiers** in this space: fully free forever
   (MIT OCW, Anthropic Academy, Hugging Face courses, d2l.ai, Elements of
   AI), free-to-audit-but-paid-certificate (Coursera specializations), and
   free-videos-but-paid-labs (DeepLearning.AI short courses as of this
   pass). Don't assume a "free course" headline means fully free — check
   per-entry above.
2. **Multi-year public archives are the norm** for the big university
   courses: even when the current year's lectures are gated to enrolled
   students, prior years usually remain permanently free on YouTube, and
   slides/assignments are often public every year regardless.
3. **Directly answering "releases from Claude themselves"**: the most
   literal fit is Anthropic's own published research writing — Claude's
   Constitution, the Transformer Circuits interpretability thread, and the
   Alignment Science blog — which function as free, primary-source
   educational material about how Claude itself is actually built and
   steered, distinct from third-party tutorials about using the API.
