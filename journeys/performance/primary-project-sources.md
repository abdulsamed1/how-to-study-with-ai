---
purpose: Contains one part of the performance and traffic-spike study map.
read_when: When diagnosing or practising the named performance concern.
depends_on:
  - ../../workspace/mission.md
  - ../../workspace/resources.md
---

# Primary Project Sources



## 1. Foundations of Scalable Systems — Ian Gorton (S28)

Use for the fundamental performance/scalability distinction and for the connection between optimization, replication, application capacity, database bottlenecks, caching, asynchronous queueing, and resource pools.

Relevant chapters (read status recorded in `../../workspace/resources.md` S28):

- Ch. 1 (read) — scalability; replication and optimization; performance; bottlenecks.
- Ch. 2 [TOC] — service tiers; scale-out; database bottlenecks; caching; asynchronous queueing; hardware scalability.
- Ch. 5 [TOC] — application service execution; thread pools; request queues; database connection pools; utilization and monitoring.

## 2. Understanding Distributed Systems, 2nd ed. — Roberto Vitillo (S27)

Use for the operational reasoning around performance, load, capacity, overload, downstream failure, caching, monitoring, and observability.

Relevant chapters (read status recorded in `../../workspace/resources.md` S27):

- Ch. 1.3 [TOC] — Scalability.
- Ch. 18 [TOC] — Network Load Balancing.
- Ch. 19 [TOC] — Data Storage.
- Ch. 20 [TOC] — Caching.
- Ch. 23 [TOC] — Messaging.
- Ch. 24 [TOC] — Common Failure Causes.
- Ch. 26 [TOC] — Fault Isolation.
- Ch. 27 [TOC] — Downstream Resiliency.
- Ch. 28 (read) — Upstream Resiliency.
- Ch. 29 [TOC] — Testing.
- Ch. 31 [TOC] — Monitoring.
- Ch. 32 [TOC] — Observability.

## 3. Designing Distributed Systems, 2nd ed. — Brendan Burns (S29)

Use selectively for implementation-oriented patterns and labs, not as a reason to study distributed systems broadly.

Relevant chapters (read status recorded in `../../workspace/resources.md` S29):

- Ch. 6 [TOC] — Replicated Load-Balanced Services.
- Ch. 9 [TOC] — Functions and Event-Driven Processing.
- Ch. 11 [TOC] — Work Queue Systems.
- Ch. 12 [TOC] — Event-Driven Batch Processing.
- Ch. 14 (read: monitoring and observability patterns) — Monitoring and Observability Patterns.
- Ch. 16 (read) — Common Failure Patterns, especially the thundering-herd and obsolete-work patterns.

## 4. User-supplied production/performance articles

Use these as the anti-pattern and scenario source for:

- measure before changing architecture;
- performance engineering before blind hardware scaling;
- N+1 query amplification;
- database bottlenecks;
- memory/CPU as symptoms that require investigation;
- timeout/retry/circuit-breaker reasoning;
- asynchronous work;
- rate limiting;
- graceful degradation;
- scaling only after establishing that the current capacity is genuinely insufficient.

These materials are treated as **scenario input**, not as a substitute for source-backed implementation details from the project books.

## 5. Casebook seeds

Case candidates and their verification state live in `../../workspace/resources.md` and `casebook/INDEX.md`. The procedure is `../../teaching/research-protocol.md`, and the case-count threshold and gap recording follow the [research protocol](../../teaching/research-protocol.md).

The cases below are the ones this branch teaches from, with the level each one serves. Their source status is in `../../workspace/resources.md`.

- Google Cloud incident report, 2025-06-12 (Service Control): recovery without randomized exponential backoff. Source S10. Candidate levels: L4 (retry backlog after recovery), L5 (overload control), L8 (full scenario).
- Anthropic Engineering, "A postmortem of three recent issues" (Sept 2025): evaluation of production quality. Source S9. Candidate levels: L1, L4 (detection difficulty), L9 (evaluation sensitivity).
- Cloudflare's 2025-11-18 outage (S35) and its resilience plan (S36). Candidate levels: L4 (retry backlog after recovery), L5 and L8 (failure propagation, configuration pushed everywhere at once). S35 is a first-party account; S36 is a stated plan, not a measured outcome.

---
