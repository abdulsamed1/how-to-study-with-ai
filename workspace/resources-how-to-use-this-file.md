---
purpose: Contains one source catalogue section.
read_when: When the named source catalogue section is needed.
depends_on:
  - ../governance/source-policy.md
---

# How to use this file


## How to use this file

This is the canonical source catalog for the FDE study path. Every reference
belongs in one of three sections:

1. **Verified references** — opened and checked; may support a lesson or factual
   claim.
2. **References to verify** — provided as a research lead; useful for finding
   material, but not evidence until its specific artifact is opened and checked.
3. **Coverage gaps** — a needed topic for which no adequate reference has been
   verified yet.

The AI must check all three sections before teaching: confirm the section and
status for each source ID (`S#` or `F#`) the current unit names, and read the
reading-status rows for those IDs. Use the ID column as the lookup key; do not
load the full verified table for one lesson. It must not silently ignore a
reference in the second section or treat it as verified.

This file is not a dump of names, newsletters, communities, or broad roadmap
ideas. Only concrete artifacts may enter a source section: a book, paper,
course page, blog post, job listing, official documentation, or another
specific publication with a canonical URL. User-supplied roadmaps and lists of
people or organizations are discovery leads only until they are tied to a
specific artifact and date-verified.

Books may be listed as citations even when access is paywalled; do not
reproduce copyrighted text. API, product, model, and security claims require
current official documentation or a dated primary source. Cite the exact
chapter, section, page, or heading used when available. A chapter tagged
`[TOC]` in a journey file was identified from a book's table of contents only
and has not been read by the mentor; keep the tag until the passage is checked.

Availability, bibliography, and reading are three separate states: an uploaded
book is available; its title page, author, and edition may still be unverified;
and `[TOC]` chapters have not been read. An uploaded book whose title page or
edition has not been checked is listed under **References to verify**, not
under Verified references.

Books marked **Uploaded in both study tools** are fully supplied by the user in
both NotebookLM and the ChatGPT Project. They may be used as study references
in either tool. Cite the book title, edition, author, and chapter or page; do
not reproduce the book or treat a generated summary as the source. The six
books carrying that marker are also on disk in `books/`, so a chapter read in
the workspace is recorded with that path as the tool.

A durable entry must identify a specific artifact with a canonical
URL, explain its relevance, and record its verification status. Roadmaps and
career feeds such as [roadmap.sh/ai-engineer](https://roadmap.sh/ai-engineer)
and [The Batch — AI Careers](https://www.deeplearning.ai/the-batch/tag/ai-careers)
are valid discovery inputs only when they are opened and tied to a specific
artifact used by the lesson.
