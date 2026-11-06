---
purpose: Contains one part of the performance and traffic-spike study map.
read_when: When diagnosing or practising the named performance concern.
depends_on:
  - ../../workspace/mission.md
  - ../../workspace/resources.md
---

# L7 — Controlled Validation: Profiling, Load Testing, Capacity Curves



## Target

Move from "I think this is the bottleneck" to **measured engineering evidence**.

## Learn

### 1. Baseline before intervention

Capture:

- throughput;
- latency distribution;
- error rate;
- resource utilization;
- database behavior;
- dependency behavior;
- queue depth / backlog when relevant.

### 2. Profiling

Use profiling to answer a narrow question:

> "Where is the process spending CPU/time/memory?"

The profile must be interpreted together with production behavior. A hot function is not automatically the root cause; it is evidence about where resources are being consumed.

### 3. Load testing

Learn to construct workload experiments that vary:

- request rate;
- concurrency;
- request mix;
- data volume;
- dependency latency;
- cache hit ratio where relevant.

### 4. Find the knee / capacity boundary

Think in curves, not single numbers:

```text
Load ↑
  │        response time
  │          /
  │         /
  │________/________
           ↑
     capacity boundary
```

Vitillo describes the point where a resource becomes exhausted and performance plateaus or worsens. Gorton likewise connects scalability to maintaining performance as load grows.

### 5. Validate the intervention

After a change, ask:

- Did the original bottleneck move?
- Did total work decrease?
- Did throughput increase?
- Did tail latency improve?
- Did error rate improve?
- Did a downstream resource become saturated?
- Did cost increase disproportionately?
- Did correctness change?

## Practice

Design one load test for the following claim:

> "Adding application instances will let the service absorb a 10× traffic burst."

Your test must be able to detect the case where the application tier scales successfully but the database becomes the new bottleneck.

## Exit criteria

I can design a controlled experiment that separates:

`better software efficiency` from `more compute capacity` from `a bottleneck moved downstream`.

## Source path

- *Foundations of Scalable Systems* (S28), Ch. 1 (read), Ch. 2 [TOC] — performance/scalability experiments and bottleneck-focused scaling.
- *Understanding Distributed Systems* (S27), Ch. 29 [TOC] — Testing; Ch. 31–32 [TOC] — monitoring/observability.
- *Designing Distributed Systems* (S29), Ch. 14 (read: monitoring and observability patterns) — Monitoring and Observability Patterns.

---
