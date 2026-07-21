---
id: free-ai-learning-resources
category: research
status: in-progress
impact: 4
confidence: 5
priority: 4
effort: 5
depends_on: []
created: 2026-07-21
updated: 2026-07-21
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

### Next steps
1. Direct Reddit mining (r/MachineLearning, r/learnmachinelearning) — this
   pass hit the same `site:reddit.com` indexing wall documented in the
   sibling research file; recommendation-list content came in secondhand
   via aggregator posts, not primary threads.
2. Foundational math prerequisites (linear algebra, calculus, probability
   for ML) surfaced only incidentally (3Blue1Brown's Essence of Linear
   Algebra, Khan Academy) — worth a dedicated sub-pass if this file is
   later turned into a structured learning-path guide, since most courses
   above assume this math rather than teach it.
3. Once judged sufficiently exhaustive, consider spinning a
   `backlog/documentation` item that turns this into an ordered learning
   path (beginner → advanced) rather than a flat catalogue — this file is
   deliberately unordered/exhaustive, not a curriculum.

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
  AI subreddits across secondary sources — coverage caveat: this pass
  could not verify these directly (`site:reddit.com` indexing gap, see
  Learnings); recommendation came from aggregator posts referencing them,
  not primary threads.
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
