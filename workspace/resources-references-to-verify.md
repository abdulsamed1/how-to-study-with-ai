---
purpose: Contains one source catalogue section.
read_when: When the named source catalogue section is needed.
depends_on:
  - ../governance/source-policy.md
---

# References to verify


## References to verify

These are research leads, not evidence. Keep them here until the exact artifact
is opened and checked. Do not cite a person or organization by name alone.

- [AI Engineering from Scratch](https://github.com/rohitg00/ai-engineering-from-scratch): reference implementation repository. Evaluated 2026-10-22; filter strictly to avoid pre-training, deep learning foundations, and math from scratch (out of FDE scope). Serves as an example bank for pure Python LLM components, structured outputs, and basic agentic loops.
- A first-party customer deployment case study with measured adoption and business outcomes at honest provenance (leads: Coinbase support-chatbot write-up, Thomson Reuters CoCounsel/Cowork write-ups — vendor-reported numbers only until independently confirmed).
- The titles *A Common-Sense Guide to AI Engineering* and *An Illustrated
  Guide to AI Agents* must each be tied to a canonical publication page or
  publisher listing before use.

- **S38 — *Software Architecture: The Hard Parts: Modern Trade-Off Analyses for Distributed Architectures*, Neal Ford, Mark Richards, Pramod Sadalage, Zhamak Dehghani, First Edition** — O'Reilly Media, October 2021. ISBN-13: 978-1-492-08688-8. [Publisher page](https://www.oreilly.com/library/view/software-architecture-the/9781492086888/). Bibliographic details verified from canonical publisher listing (2026-10-17). Uploaded in both study tools (available as a study source per learner crosswalk of 2026-10-14), though not present as a local EPUB file in `/books/` on disk for this agent. Stays in References to verify because no chapter text has been read or examined by the mentor; all chapter citations in the journey remain `[TOC]` only.
- Performance case candidates named from memory, not opened: Facebook's September 2010 outage; Slack's 2021-01-04 outage; AWS us-east-1 on 2025-10-20. Confirm each exists, read the postmortem, and discard any that do not fit a level. Candidate levels for the first two are L4 and L8.
- A primary statistics-for-LLM-evaluation tutorial covering variance, sample size, and meaningful comparison (applied level per journey rule 9 — no ML-theory texts).
- Integration hardening still to open (leads, unopened on 2026-09-30; migrated from estaie-study-map 2026-10-09 — open and record exact section before teaching): Google SRE ch. 22 cascading failures (https://sre.google/sre-book/addressing-cascading-failures/); Kleppmann distributed locking (https://martin.kleppmann.com/2016/02/08/how-to-do-distributed-locking.html) + antirez Redlock reply (https://www.antirez.com/news/101); transactional outbox (https://microservices.io/patterns/data/transactional-outbox.html); Supabase range columns (https://supabase.com/blog/range-columns); Django ExclusionConstraint (https://docs.djangoproject.com/en/dev/ref/contrib/postgres/constraints); RateGain ARI push (https://developer.rategain.com/our-products/channel-manager/rg-bridge-supply-push/interface-specifications-availability-and-rates-notification-service); oneuptime Stripe-webhook atomic-enqueue 2026-09-13 (https://oneuptime.com/blog/post/2026-09-13-stripe-webhook-event-id-atomic-enqueue/view — Tier 2, confirm against provider docs). The Stripe idempotency, AWS retry, GitHub webhook, Stripe webhook, and Airbnb double-payments leads were opened and are registered as S64–S68.
- Further agent-incident primaries beyond EchoLeak (e.g., names in the OWASP Agentic 2026 announcement) — open the primary before any casebook use.
- OpenAI Datasets / evaluation-getting-started guide (successor to the deprecated S22 flow). S12 (Anthropic enterprise guide) and S14 (code execution with MCP) are verified; what remains a lead here is the procedural detail inside each (workflow sequences, the MCP code-API pattern).
- RFC 9457, *Problem Details for HTTP APIs* (https://www.rfc-editor.org/rfc/rfc9457; IETF Proposed Standard, July 2023; obsoletes RFC 7807). Found, not read. Candidate unit: P4.3.
- RFC 9700 / BCP 240, *Best Current Practice for OAuth 2.0 Security* (https://www.rfc-editor.org/rfc/rfc9700; January 2025). Found, not read. Candidate unit: P4.8b; also cross-check S6's OAuth statements.
- Postman, *API Security Best Practices* (https://blog.postman.com/api-security-best-practices/; dated 2026-02-19 in the learner's list). Not opened; at most a secondary checklist, never a substitute for S39, OWASP, or primary platform documentation.
- Cloudflare API Shield, BOLA vulnerability detection (https://developers.cloudflare.com/api-shield/security/bola-vulnerability-detection/; updated 2026-09-29 in the learner's list). Not opened; product-specific, so separate Cloudflare's detection description from general authorization-testing requirements.
- Stripe's AI-benchmark repository (https://github.com/stripe/ai/tree/main/benchmarks), described in S37. Not opened.
- OpenAPI Specification 3.1 (https://spec.openapis.org/oas/v3.1.0; JSON Schema 2020-12 dialect): lead for P4.3's contract-source-of-truth artifact (one machine-readable contract document) and the P4.8a contract-sheet claims; not opened.
- roadmap.sh pages for API security best practices, backend, software architect, and forward deployed engineer: all four were opened 2026-10-14. They render their skill nodes client-side and the fetched text contained none (only page descriptions and, on the Backend page, introductory prose), so no skill cluster could be extracted and none is registered as a source.
- Roadmap-linked primaries (S48's five layers) not opened in the 2026-10-21 alignment pass because no unit edit hung on them; open at teach time when a lesson needs one: MCP build-server tutorial (https://modelcontextprotocol.io/docs/develop/build-server; spec S6 already registered), Qdrant reranking/hybrid-search tutorial (https://qdrant.tech/documentation/tutorials-basics/reranking-hybrid-search/), OpenAI structured-outputs guide (https://developers.openai.com/api/docs/guides/structured-outputs), Anthropic define-success-criteria/develop-tests page (https://platform.claude.com/docs/en/test-and-evaluate/develop-tests — unreachable from this environment; recheck), Arize Phoenix docs (https://arize.com/docs/phoenix), LangGraph Academy intro course (https://academy.langchain.com/courses/intro-to-langgraph — framework track; likely excluded by the journey's framework-agnostic stance), Python official tutorial venv chapters and httpx async guide (https://docs.python.org/3/tutorial/, https://www.python-httpx.org/async/ — for the P11.2 lab environment, cited only if taught). OWASP LLM Top 10 canonical URL (S16's registration) should be rechecked: genai.owasp.org/llm-top-10/ did not respond 2026-10-21; promptfoo's docs link the project page at owasp.org/www-project-top-10-for-large-language-model-applications/ instead.
- Additional high-signal leads may be added only as links to specific articles,
  talks, papers, repos, or course pages; generic names and broad lists are not
  accepted entries.
