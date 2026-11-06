---
purpose: Contains one FDE journey support register or gate.
read_when: When checking FDE gates, sources, progress, or milestones.
depends_on:
  - journey-overview.md
  - ../../workspace/resources.md
---

# 7. Source register for this map


## 7. Source register for this map

The F-series foundational sources are maintained in the canonical
[`../../workspace/resources.md`](../../workspace/resources.md) registry. Lesson references such as `F1` and
`F12` must be resolved there. Re-open the exact page used before teaching and
record the subsection or version; a landing-page check is not proof that every
chapter or page has been read.

### S-series — existing project source registry

The following IDs are defined in `../../workspace/resources.md`; consult that file for publisher, verification state, edition, and access notes. Only entries marked **Verified** may support a factual claim. The most relevant starting points are:

- **S1:** FDE role standard — the Claude Frontier Academy announcement is primary; its program figures, dates, and badge timing are recorded in `../../workspace/resources.md` S1. **S2:** single Deloitte job listing — treat as stale/unverified until re-opened; superseded by S1.
- **S3, S7–S8, S12–S14:** agent/workflow patterns, tool design, multi-agent trade-offs, long-running execution, MCP-related engineering. Note S3's banner (tooling landscape changed since Dec 2024): patterns stand, tooling examples need re-checking.
- **S6:** MCP specification — pin the spec date in each lesson record; the current spec version and its date live in `../../workspace/resources.md` S6.
- **S4, S21–S23:** official model APIs, agent SDKs, and evaluation tools; re-check current versions. S22 (OpenAI evals guide) is deprecated — teach the Datasets/evaluation-getting-started flow instead; its shutdown dates are in `../../workspace/resources.md` S22.
- **S5:** context engineering.
- **S9:** quality-degradation postmortem — supports evaluation-gap detection and production evaluation (P14.5–P14.7, P9.5), and supplies a documented dependency-degradation failure case for P16.1's containment matrix. It documents no duplicate delivery or payment idempotency failure; never cite it for those.
- **S10:** Google Cloud Service Control incident — supports the documented crash-loop mechanism and the recovery herd caused by missing randomized exponential backoff (P8.3, P9.5), and supplies a dependency-failure case for P16.1's containment matrix. It is not a provider-specific 429/5xx case; the 503s were symptoms of an internal control-plane failure.
- **S35–S36:** Cloudflare's November 2025 outage account (configuration change, propagation, diagnosis, recovery) and its stated resilience plan. S36 is a plan with a Q1 2026 target, not verified implementation or measured results.
- **S37:** Stripe's vendor benchmark of agent-built integrations. Supports only the failure modes it documents — notably an agent treating a 400 on invalid test data as success, and browser-use dead ends. Not evidence about duplicate delivery, retry storms, or general production reliability.
- **S64–S68:** Stripe idempotency documentation, Airbnb double-payment prevention (2019), AWS timeouts/retries/backoff with jitter (2019), GitHub webhook best practices and signature validation, and Stripe's webhook guide. Provider engineering guidance plus one first-party incident write-up: they support mechanism claims, not measurements of this capstone.
- **S15:** evaluation methodology and agent-eval practice (2026-01-09 refresh).
- **S16–S17:** OWASP LLM Top 10 2026 and Agentic Top 10 2026 — always cite the edition. **S24:** NIST AI RMF 1.0 plus GenAI Profile NIST AI 600-1 — cite the profile.
- **S18–S19, S25–S29:** distributed systems, data systems, architecture, scalability, and SRE foundations.
- **S33–S42:** S33 AWS Well-Architected REL03-BP01 (workload segmentation; vendor guidance), S34 Node.js test-CI security incident, S35 and S36 Cloudflare's 2025 outage account and resilience plan, S37 Stripe's AI-agent integration benchmark, S38 *Software Architecture: The Hard Parts* (chapters `[TOC]` only), S39 NIST SP 800-228-upd1 (the original SP 800-228 was withdrawn and superseded in its entirety — cite only the current edition), S40 GitHub's guide to human oversight in AI-assisted code review, S41 Faler's essay on AI-assisted engineering antipatterns, S42 C4 model for architecture diagramming (site structure verified). Read the caveats in `../../workspace/resources.md` first: S33, S36, S37, S40, and S41 are vendor or practitioner material, not independent measurement.

### Known source gaps — keep visible

Full entries live in the ../../workspace/resources.md coverage gaps list, kept current there; this map records only what each gap costs in a lesson:

- RAG chunking/embedding/reranking tuning depth: P12.5 stays at failure-taxonomy depth (Barnett et al. FP1–FP7); tuning claims are labeled as research gaps, not facts.
- Statistical-uncertainty tutorial for LLM evaluation: P14.3 teaches from the labeled interim protocol only; it does not cite an unverified source as established.
- Agent tool-misuse incidents: Phase 13/15 use verified EchoLeak (CVE-2025-32711); every other named incident stays a casebook lead until its primary is opened.
- Webhook signature verification and raw-body handling (P8.4): the unit's rules stand on F4/S39 general guidance and are labeled provider-unverified until a primary source is opened.
- Human-in-the-loop practice: S40/S41/S37 are qualitative; teach review requirements as engineering judgment, not as measured effect sizes.

For any topic whose supporting source is not verified, the lesson labels it as a research gap and never states it as established fact.
