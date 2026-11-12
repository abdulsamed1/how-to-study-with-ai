---
purpose: Contains one source catalogue section.
read_when: When the named source catalogue section is needed.
depends_on:
  - ../governance/source-policy.md
---

# Reading status


## Reading status

The single record of what was read, keyed by source ID. The rows above carry
identity and verification status only. A chapter tagged `[TOC]` in a journey
file was identified from a book's table of contents only and has not been read;
keep the tag until the exact passage is read and recorded here. Clearing a tag
follows journey rule 7. Tool is where the passage was read: `web` for a
page, `books/ epub` for a local book file. For each book, the chapters listed
below are the ones read; every other cited chapter of that book is still
`[TOC]`.

| Source | Chapter or section | Status | Date | Tool |
|---|---|---|---|---|
| S1 | eligibility and program-structure sections | read (sections) | 2026-10-14 | web |
| S18 | public linearizability FAQ | read (sections) | 2026-10-19 | web |
| S39 | sections 1–4.5 of the PDF | read (sections) | 2026-10-15 | web |
| S39 | Appendix F change log, §5, Appendices A–E | not read | — | — |
| S19 | ch. 1–2 | read | 2026-10-16 | books/ epub (OpenCode) |
| S19 | ch. 6 (replication lag and stale reads) | read (sections) | 2026-10-19 | books/ epub (OpenCode) |
| S19 | ch. 7 (sharding; when to avoid it) | read (sections) | 2026-10-19 | books/ epub (OpenCode) |
| S19 | ch. 8 (distributed transactions: commit on some nodes, fail on others) | read (sections) | 2026-10-19 | books/ epub (OpenCode) |
| S19 | ch. 10 (consistency and consensus) | read (sections) | 2026-10-19 | books/ epub (OpenCode) |
| S19 | ch. 12 (consumer offsets, per-partition order, replay) | read (sections) | 2026-10-19 | books/ epub (OpenCode) |
| S20 | ch. 4–6, 11, 19, 21–23 | read | 2026-10-16 | books/ epub (OpenCode) |
| S20 | ch. 4 (concurrency models; the Node.js event loop and blocking CPU work) | read (sections) | 2026-10-19 | books/ epub (OpenCode) |
| S20 | ch. 8 (component-based thinking; logical vs physical architecture) | read (sections) | 2026-10-19 | books/ epub (OpenCode) |
| S26 | ch. 2–3, 16 | read | 2026-10-16 | books/ epub (OpenCode) |
| S26 | ch. 4 (communication styles; inter-process failure modes) | read (sections) | 2026-10-19 | books/ epub (OpenCode) |
| S27 | ch. 28 (upstream resiliency: load shedding, load leveling, rate limiting) | read | 2026-10-19 | books/ epub (OpenCode) |
| S28 | ch. 1 (introduction to scalable systems), ch. 6 (distributed caching) | read | 2026-10-19 | books/ epub (OpenCode) |
| S28 | ch. 4 (an overview of concurrent systems) | read (sections) | 2026-10-19 | books/ epub (OpenCode) |
| S29 | ch. 2 (important distributed system concepts), ch. 16 (common failure patterns) | read | 2026-10-19 | books/ epub (OpenCode) |
| S29 | ch. 14 (monitoring and observability patterns) | read (sections) | 2026-10-19 | books/ epub (OpenCode) |
| S38 | all cited chapters | [TOC] | — | — |
| S9 | full article | read | 2026-10-22 | web |
| S10 | full article | read | 2026-10-22 | web |
| S14 | full article | read | 2026-10-21 | web |
| S33 | full article | read | 2026-10-14 | web |
| S34 | full article | read | 2026-10-14 | web |
| S35 | full article | read | 2026-10-14 | web |
| S36 | full article | read | 2026-10-14 | web |
| S37 | full article | read | 2026-10-14 | web |
| S40 | full article | read | 2026-10-15 | web |
| S41 | full article | read | 2026-10-15 | web |
| S43 | full article | read | 2026-10-19 | web |
| S44 | page | read | 2026-10-19 | web |
| S45 | page | read | 2026-10-21 | web |
| S46 | page | read | 2026-10-21 | web |
| S47 | page | read | 2026-10-21 | web |
| S48 | full repo at pinned commit 061a9087dc710f9d4b7644c88d329a2a341ffcad | read | 2026-10-21 | web |
| S49 | majority of page; opening sections + output/tool-use/thinking/agentic sections | read | 2026-10-21 | web |
| S50 | mechanics, pricing, structure, invalidation, tracking sections | read | 2026-10-21 | web |
| S51 | full article | read | 2026-10-21 | web |
| S52 | short overview | read | 2026-10-21 | web |
| S53 | Welcome page incl. "GraphRAG vs Baseline RAG" and process sections | read | 2026-10-21 | web |
| S54 | metric index page | read | 2026-10-21 | web |
| S55 | homepage: what-is, key features, MCP relationship, governance | read | 2026-10-21 | web |
| S56 | page | read | 2026-10-21 | web |
| S57 | full article | read | 2026-10-21 | web |
| S58 | README | read | 2026-10-21 | web |
| S59 | majority; key-considerations, use-cases, prompting-techniques sections | read | 2026-10-21 | web |
| S60 | page | read | 2026-10-21 | web |
| S61 | full article | read | 2026-10-21 | web |
| S64 | full page | read | 2026-10-24 | web |
| S65 | full article | read | 2026-10-24 | web |
| S66 | full article | read | 2026-10-24 | web |
| S67 | both pages | read | 2026-10-24 | web |
| S68 | full page | read | 2026-10-24 | web |
| S69 | cover, contents, and sampled chapter-opening passages; crosswalk sections mapped from contents, not read in full | partial; all mapped chapter sections remain `[TOC]` until opened at teach time | 2026-10-24 | local PDF |
| S70 | full page: definition, process, GLASGOW steps, and limitations | read | 2026-11-06 | web |
| S71 | abstract only | partial; full article not read | 2026-11-06 | web |

| S72 | Design: Message Delivery Semantics and Using Transactions; KafkaConsumer: position, committed position, consumer groups, and offset commits | read (sections) | 2026-11-12 | web |
| S73 | Consumer Acknowledgements and Publisher Confirms: manual/automatic ack, requeue, publisher confirms, prefetch; Quorum Queues: poison-message handling, delivery limit, delayed retry, dead lettering and at-least-once constraints | read (sections) | 2026-11-12 | web |
