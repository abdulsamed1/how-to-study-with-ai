---
purpose: Contains one FDE journey support register or gate.
read_when: When checking FDE gates, sources, progress, or milestones.
depends_on:
  - journey-overview.md
  - ../../workspace/resources.md
---

# 6. Supporting branches — not required all at once


## 6. Supporting branches — not required all at once

- **Production performance and traffic spikes:** open `../performance/study-overview.md` when the P2.1 baseline or a Phase 9 diagnosis (P9.6) exposes a gap, or a real project needs it. Do not study all performance topics up front.

Division of labor (read-only cross-reference; neither file re-teaches the other):

| FDE-map unit | Performance-map levels | Who owns what |
|---|---|---|
| P9.6 (performance diagnosis) | L0–L4 | FDE map decides *that* diagnosis is needed; the performance map owns the diagnosis method (symptom→mechanism, request/resource signals, N+1, pools, contention). |
| P10.5 (read-path and overload mechanisms) | L3.6, L5.1–L5.4, L6.3–L6.6 | FDE map owns *choosing and justifying* caching, read replicas, load balancing, rate limiting, load shedding; the performance map supplies the criteria and failure modes (cache failure → origin overload, hot tenants, messaging). |
| P10.6 (distribution trade-offs) | L6.1–L6.2, L6.6 | FDE map owns consistency/partitioning/consensus *decisions*; the performance map supplies scale-up/scale-out, bottleneck migration, and "the database follows the application" reasoning. |
| P9.4, P9.7 (SLIs, fault matrix, runbook) | L8 scenarios A–G | The performance map's scenario set is rehearsal material: spike + CPU, slow-dependency 200s, burst, hot tenant (rate limiter), cache-vanish origin collapse (P10.5 failure case). |
| P11.4, P14.5, P16.1 | L9 | The LLM bridge: model call as downstream dependency, retries/side effects, context growth as unbounded state, observability for LLM calls. |
| P10.4a Stage 3 (capacity estimates) vs P9.6/P17.2 | L7 | P10.4a prepares *estimated* numbers; L7 owns *measured* curves (profiling, load testing, knee/capacity boundary). Estimates are validated by L7-style load tests, not by more estimation. |

- **AI Security specialization:** deepen OWASP/NIST, red teaming, secure SDLC, and security labs after Phase 15 or when the capstone risk requires it.
- **Distributed systems depth:** use *Designing Data-Intensive Applications*, 2nd ed.; *Understanding Distributed Systems*, 2nd ed.; *Building Microservices*, 2nd ed.; *Designing Distributed Systems*, 2nd ed.; *Software Architecture: The Hard Parts*; and *Foundations of Scalable Systems* as chapter-level sources only when the lesson needs them. Their bibliographic and read status is recorded in `../../workspace/resources.md`; chapters tagged `[TOC]` come from a table of contents only.
- **Framework specialization:** Avoid framework-first tutorials disconnected from the capstone.
