---
purpose: Defines a temporary, source-grounded learning scope for caching using a synthetic ESTAIE integration scenario.
read_when: When the learner declares TMP:caching-estaie:v1.
depends_on:
  - ../../workspace/mission.md
  - ../../workspace/resources.md
---

# TMP:caching-estaie:v1 — Caching from first principles

**Status:** Temporary learning scope; not part of the permanent FDE curriculum.
**Owner:** Mentor until a permanent journey owner is approved.
**Objective:** Given a read-heavy integration workflow, explain, design, implement, and test a cache that reduces repeated origin work while preserving an explicit freshness contract and remaining safe when the cache is unavailable.
**Scenario boundary:** ESTAIE is the business context only. All endpoints, data, traffic, architecture, and constraints used in lessons are synthetic training assumptions unless the learner supplies verified ESTAIE artifacts. Do not claim these describe ESTAIE production.

## Assumed starting point

No caching prerequisite is required. Teach the request, application, origin/database, and response path as needed. Treat HTTP, API, and database concepts as bridges, not gates. No specific ESTAIE programming language or infrastructure is assumed.

## Temporary branch map

| Unit | Focus | Prerequisite | Proof |
|---|---|---|---|
| C1 — Why caching exists | Repeated reads, origin work, cache hit/miss, latency and load | None | Trace one request and explain what work is avoided on a hit and repeated on a miss |
| C2 — Cache-aside and keys | Read-through flow controlled by the application; key identity and cache boundaries | C1 | Design stable keys for synthetic partner/property reads and trace hit/miss behavior |
| C3 — Freshness and invalidation | TTL (time-to-live), expiration, invalidation, stale data, and write paths | C2 | State a freshness contract and show how updates affect cached values |
| C4 — Local vs distributed; Caffeine vs Redis | Per-process memory versus shared cache service; latency, sharing, failure, and operations | C1–C3 | Select or reject each option against explicit workload and deployment constraints |
| C5 — Eviction and admission | Capacity limits, LRU/LFU, Caffeine W-TinyLFU, Redis eviction policies | C4 | Explain the policy difference without claiming a universal hit-rate winner |
| C6 — Failure and verification | Cache outage, miss storms, stampede, hot keys, origin protection, metrics and tests | C1–C5 | Test hit/miss/stale/unavailable paths and show bounded origin load during cache failure |

Teach one unit at a time. Each lesson follows the repository's four-part lesson protocol and introduces at most two new primary concepts. Do not teach the whole map in one response.

## Concept links

- C1 → request-path cost and database/query diagnosis (FDE P9.6; performance L3).
- C2–C3 → data ownership, writes, correctness, and consistency (FDE Phase 5 and Phase 8).
- C4–C5 → runtime memory, service boundaries, capacity, and workload-dependent trade-offs (FDE P9.6 and P9.8).
- C6 → overload control, graceful degradation, observability, and resilience (FDE P9.3, P9.7, P9.9).
- Later design connection: FDE P10.5 owns the include/defer/reject decision for caching in a system design.

These are connections, not claims that the learner has completed those units.

## Sources

- **S28 — Foundations of Scalable Systems**, Ian Gorton, 1st ed., ch. 2 section “Scaling the Database with Caching” and ch. 6 “Distributed Caching.” Uploaded EPUB inspected. Supports the origin bottleneck, distributed cache role, application caching, and web caching.
- **S27 — Understanding Distributed Systems**, Roberto Vitillo, 2nd ed., ch. 20 “Caching.” Uploaded EPUB inspected. Supports cache purpose, hit ratio, side/inline cache, TTL, invalidation difficulty, local/external cache trade-offs, and thundering herd.
- **S77 — Caffeine official project documentation**, “Eviction” and “Efficiency.” Official project wiki opened 2026-11-20. Supports size/time eviction and W-TinyLFU design; its hit-rate comparisons are workload/simulation claims, not a universal guarantee.
- **S78 — Redis Open Source documentation**, “Key eviction.” Official documentation search result reviewed 2026-11-20; direct page rendering returned no readable lines. Use the official page for current Redis policy names and behavior, and reopen during any implementation lesson.
- **ESTAIE system facts:** none supplied or verified for this scope. Keep all example details labelled synthetic.

## Proof boundary and exit

A guided explanation is not proof. The scope is complete only when the learner independently:
1. chooses a cache boundary and stable key for a changed read workload;
2. defines freshness and invalidation behavior;
3. justifies local versus distributed placement and an eviction policy from workload evidence;
4. demonstrates hit, miss, stale, eviction, and cache-unavailable behavior in a runnable test harness;
5. measures hit ratio, origin request rate, and latency, and demonstrates that cache failure does not cause uncontrolled origin overload.

No production deployment, ESTAIE implementation, or measured business outcome is implied by completing this temporary scope. Keep it temporary unless the learner and repository owner approve a permanent curriculum change.
