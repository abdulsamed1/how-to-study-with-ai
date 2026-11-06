---
purpose: Contains one part of the performance and traffic-spike study map.
read_when: When diagnosing or practising the named performance concern.
depends_on:
  - ../../workspace/mission.md
  - ../../workspace/resources.md
---

# L2 — Resource and Execution Bottlenecks



## Target

Learn to identify **where request processing is actually consuming capacity**.

## Branch A — CPU-bound work

Learn to distinguish:

- genuine compute saturation;
- expensive algorithmic work;
- excessive repeated work;
- unnecessary serialization/deserialization;
- high allocation pressure;
- CPU spent because another subsystem is causing pathological work.

The goal is not to memorize Big-O formulas. The goal is to connect workload growth to actual work performed and then verify the hypothesis with profiling or measurement.

## Branch B — Memory and garbage collection

Investigate:

- memory growth over time;
- allocation volume;
- cache growth without a bound;
- object retention;
- garbage-collection pressure where the runtime exposes it;
- whether memory pressure is causing secondary latency effects.

A memory graph that rises is evidence to investigate, not proof that more RAM is the correct remedy.

## Branch C — Threads, pools, blocking, and queues

This is critical for burst scenarios.

Understand the request-processing path:

```text
Incoming request
      ↓
accept / socket queue
      ↓
request worker / thread pool
      ↓
blocking operation or dependency
      ↓
resource pool
      ↓
response
```

The important lesson from *Foundations of Scalable Systems* is that response time can include both actual processing time and time spent waiting for scarce resources such as threads or database connections. Under heavy load, queues can grow, consume resources, and worsen latency further.

## Branch D — Concurrency and contention

Understand enough concurrency to diagnose:

- lock contention;
- blocked work;
- race conditions;
- serialized critical sections;
- contention increasing as concurrency rises.

Do not turn this branch into a general concurrency course. Learn only what is required to explain the observed production behavior.

## Practice

Scenario:

> Application latency rises sharply under load. CPU is only 60%. Thread count is high. Database CPU is 30%. Requests spend a large fraction of their time waiting for an application resource pool.

Explain why increasing the number of application instances might change the symptom without addressing the underlying bottleneck.

## Exit criteria

I can distinguish:

`CPU saturation` vs `queue/pool waiting` vs `blocking/contended work` vs `inefficient execution`.

I know what profiling or runtime telemetry I need before changing instance size.

## Source path

- *Foundations of Scalable Systems* (S28), Ch. 5 [TOC] — application service execution, thread pools, request queues, database connection pools, utilization, latency.
- *Foundations of Scalable Systems* (S28), Part I [TOC] — concurrency fundamentals only to the depth required to reason about contention and performance.

---
