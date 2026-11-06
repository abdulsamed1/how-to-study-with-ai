---
purpose: Contains one part of the performance and traffic-spike study map.
read_when: When diagnosing or practising the named performance concern.
depends_on:
  - ../../workspace/mission.md
  - ../../workspace/resources.md
---

# Production Performance & Traffic-Spike Engineering — Study Map



> **Purpose:** Build the ability to diagnose, explain, mitigate, and permanently improve production systems when latency rises, throughput collapses, resources saturate, dependencies slow down, or traffic changes abruptly.

> **Scope:** This is a focused journey for **performance incidents, overload, capacity limits, bottleneck analysis, resilience under pressure, and production debugging**.

> **Core principle:** Do not memorize a fixed recipe such as `Load Balancer → Scale → Redis → Queue`. Diagnose the mechanism first. The intervention depends on the actual constraint, workload, correctness requirements, and failure mode.

---

## How to use this map

**Supporting branch.** Opened from `journey-overview.md` (P2.1 baseline, or when P9.6 exposes a gap) or when the user asks for production-incident diagnosis. It is not the default start of any other journey.

*Revised 2026-10-22. This file says WHAT to learn. Teaching, assessment, and record rules are in `../../AGENTS.md`; templates in `../../teaching/session-protocol.md`.*

- **Branch IDs:** `PERF-L0` … `PERF-L9`, plus the branch letter where one exists (`PERF-L2-C`). Use them when stating a session outcome.
- **Evidence rule:** tick a Mastery box only when a learning record, a lab result, or a project file proves it, and write its reference beside the box.
- **Source markers:** every chapter citation names its `../../workspace/resources.md` ID and its read status, following journey rule 7: `(read)` = the chapter was read in full, `(read: …)` = only the named sections were read, `[TOC]` = the chapter was identified from the book's table of contents and has not been read yet. The read-status record is the `../../workspace/resources.md` reading-status table.

| Level | Casebook concepts to research (`casebook/<slug>.md`) | Lab |
|---|---|---|
| L0 | `symptom-vs-mechanism` | none (written practice) |
| L1 | `observability-evidence` | none |
| L2 | `cpu-vs-queueing`, `pool-exhaustion` | 1, 3 |
| L3 | `n-plus-one`, `database-bottleneck` | 2 |
| L4 | `slow-dependency`, `retry-storm` | 4 |
| L5 | `load-shedding-vs-rate-limiting`, `queue-backlog` | 5 |
| L6 | `bottleneck-migration`, `cache-as-dependency` | 6, 7 |
| L7 | `profiling-and-load-testing` | all |
| L8 | full scenarios A-G | none (reasoning) |
| L9 | `llm-system-performance` | 8, 9 |

---

## Mission

### Why

Become able to answer production scenarios such as:

- "Traffic increased 20× and the API started timing out. What do you do?"
- "CPU is 95%, but adding servers did not solve the incident. Why?"
- "Application instances scaled from 5 to 50, but database CPU became saturated. What changed?"
- "Latency increased while CPU and memory stayed normal. Where do you investigate?"
- "A downstream payment provider became slow and took the whole request path with it. How do you contain the failure?"
- "A short-lived burst overloaded the service, but the work did not need to finish synchronously. What should change?"

### Success looks like

I can take a production symptom and move through:

`Symptom → Evidence → Hypothesis → Isolation → Targeted intervention → Validation → Root cause → Prevention`

without jumping directly to a technology choice.

I can also explain why a tempting intervention is **wrong for the diagnosed mechanism**.

### Constraints

- Learn the **decision-making skill**, not a catalog of architecture components.
- Use real production cases and controlled experiments.
- Prefer profiling, measurements, traces, query plans, load tests, and incident evidence over intuition.
- Treat scalability and performance as related but distinct problems.
- Treat a high CPU/memory/error metric as a **signal to investigate**, not automatically as the root cause.
- Do not claim production experience with a tool merely because it was studied (`../../AGENTS.md` §11).

### Out of scope

Do not turn this journey into a complete course on:

- microservices architecture;
- distributed consensus;
- leader election;
- sharding internals;
- Kubernetes internals;
- Kafka internals;
- service-mesh internals;
- cloud-provider certification material;
- generic design-pattern memorization;
- framework tutorials without a performance/production scenario.

---
