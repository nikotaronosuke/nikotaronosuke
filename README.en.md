# nikotaronosuke

English | [日本語](README.md)

## Building products with AI — without outsourcing the decisions

I design and build independent Web / Mobile products.

I use ChatGPT, Claude, Claude Code, and other generative-AI tools as implementation, research, and review partners.

What I try to keep human-owned is:

- what to build
- product scope
- UX
- acceptance criteria
- trade-offs
- real-device / real-use verification
- the decision to change the specification when the original idea does not hold up

---

## Active products

### Caplog

A mobile-first product for **discovering places, creating outing plans, recording the experience, and reusing those records in future plans**.

- [Public showcase](https://github.com/nikotaronosuke/caplog-showcase)
- [Web](https://caplog.jp)

`Expo` `React Native` `TypeScript` `Supabase` `Cloudflare Workers` `Next.js` `Google Maps / Places`

Current focus is the Mobile app while the Web version remains in production.

The public showcase documents decisions around:

- interactive route maps
- public URL architecture
- Mobile App API boundaries
- provider credential / cost controls
- privacy-aware logging
- real-device verification

**Status:** Mobile in active development / Web in production

---

### ぽいもの本舗 / Poimono

My personal site for products, development logs, technical articles, and Web experiments.

- [poimono.jp](https://poimono.jp)

`Astro` `TypeScript` `Cloudflare Workers Static Assets`

It is the main public home for my projects, experiments, and engineering notes.

**Status:** in production / continuously updated

---

### NINJA MAP

A bilingual travel database for finding **ninja experiences and attractions that can be visited today in Japan**.

- [Japanese](https://ninjamap.jp)
- [English](https://ninjamap.jp/en/)

`Astro` `TypeScript` `MapLibre GL JS` `Cloudflare Workers`

The project separates:

- source verification for whether a place should be listed
- coordinate verification for public map display
- Japanese / English publishing
- map / SEO output

The initial dataset contains 50 ninja-experience spots.

**Status:** in production / data continuously maintained

---

## Public tools and engineering projects

### [Tiny Code Pet](https://github.com/nikotaronosuke/tiny-code-pet)

A tiny native Windows desktop pet for Claude Code and Codex.

It shows working state, estimated whole-request progress, and completion while deliberately avoiding prompt / response / source-code inspection.

`C#` `Win32` `Claude Code Hooks` `Codex Hooks`

Highlights:

- pure Win32, no Electron / WebView
- event-driven, no polling
- progress separated from completion
- root Stop + 20-second quiet-window completion
- Claude / Codex lifecycle differences kept separate
- ninja animation and subagent “shadow clones”

---

### [AI Problem-Solving Memory](https://github.com/nikotaronosuke/ai-problem-solving-memory)

A Problem Control / Consistency Layer for multiple AI coding agents.

Instead of sharing entire chat transcripts, agents continue the same **Problem identity** with typed evidence, dead ends, discoveries, fixes, and Verification.

`TypeScript` `PostgreSQL` `MCP`

Highlights:

- server-authoritative Problem state
- FIX separated from Verification
- optimistic locking and idempotent writes
- explicit recall of past experience
- provider-free lexical retrieval core
- Claude Code / Codex / remote-host support through one Problem truth

---

### [Excel Batch Tool](https://github.com/nikotaronosuke/excel-batch-tool)

A Windows desktop application for safely batch-processing Excel workbooks **fully offline and without Microsoft Excel itself**.

`C#` `WPF` `.NET 8` `Open XML SDK`

Highlights:

- read-only workbook safety analysis
- source files are never edited in place
- unsupported workbook semantics block instead of silently disappearing
- exact-key transfer / matching
- CSV transformation
- PDF → Excel / CSV
- optional Offline OCR Pack
- human review when OCR cannot be trusted safely

---

### [CrowdWorks AI Work Survey Analyzer](https://github.com/nikotaronosuke/crowdworks-ai-survey-analyzer)

A fully local browser app for survey CSV / TSV analysis.

It was originally built for a Japanese crowdsourcing survey about paid work performed with generative AI.

`TypeScript` `Vite` `Chart.js` `Vitest`

Highlights:

- no upload / no analytics / no persistent browser storage
- CrowdWorks-specific CSV normalization isolated in one adapter
- explicit per-question denominators
- multiple-response aggregation
- cross-tabs
- conservative free-text parsing
- identity fields structurally excluded from AI-facing summaries

---

### [Jev Voice Decision](https://github.com/nikotaronosuke/jev-voice-decision)

A Windows demo that turns Japanese speech into **typed decisions rather than generated answers**.

`Python` `Jev` `Parakeet JA`

The model handles the ambiguous decision layer; ordinary Python keeps the deterministic action rules.

Highlights:

- local STT
- only final transcript sent to Jev
- Choice / Noul / Score primitives
- abstention when confidence is low
- push-to-talk instead of always-on listening
- no persisted audio / transcript / session history

---

### [Japanese STT & LLM Router Evaluation](https://github.com/nikotaronosuke/ja-stt-router-eval)

An evaluation harness for Japanese speech recognition and closed-set LLM routing.

`Python` `Windows` `WSL` `STT` `LLM routing`

Highlights:

- explicit evaluation methodology before product integration
- missing values are never converted to zero
- abstention is a valid outcome
- wrong display measured separately from safe miss
- sealed routing fixture before provider comparison
- privacy / budget gates before hosted-provider runs
- historical measurements clearly separated from reproducible assets

---

<details>
<summary><strong>Past prototypes / paused projects</strong></summary>

### Dog App

A mobile prototype about spending time with “your dog” inside the phone.

`Flutter` `Dart` `Flame` `Supabase`

I prototyped autonomous dogs in a 2D plaza, authentication, profiles, and media flows.
The project was paused after repeated real-device quality evaluation and scope review.

### Uradori

A restaurant-search prototype for answering:

> “The place I planned to go to does not work — where should I go instead?”

`React Native` `Expo` `TypeScript` `Cloudflare Workers` `Google Places / Routes`

The project explored alternative-place search using current location, travel conditions, and category filters.
It was paused after evaluating external API cost and product viability.

</details>

---

## How I work

- **Product / UX:** I own product direction, specifications, UX, and final acceptance decisions
- **AI:** I use ChatGPT / Claude / Claude Code for research, implementation, and review
- **Verification:** I verify with real screens, real devices, and real workflows where relevant
- **Revision:** I do not force the product to fit the original technical plan; if evidence says the specification is wrong, I change the specification

---

## Current interests

- AI-assisted product development
- UX prototyping
- mobile / real-device verification
- privacy-aware local tooling
- safe human–AI collaboration
- systems where multiple AI agents can share evidence without silently sharing authority
