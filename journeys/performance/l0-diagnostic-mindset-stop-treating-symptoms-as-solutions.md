---
purpose: Contains one part of the performance and traffic-spike study map.
read_when: When diagnosing or practising the named performance concern.
depends_on:
  - ../../workspace/mission.md
  - ../../workspace/resources.md
---

# L0 — Diagnostic Mindset: Stop Treating Symptoms as Solutions



## Target

Build the first mental habit: **a production symptom is not yet a diagnosis**.

## Learn

### 1. Symptom vs. mechanism vs. root cause

A symptom is what the system exposes:

- high latency;
- high CPU;
- high memory;
- rising error rate;
- exhausted connections;
- growing queue depth;
- timeouts;
- throughput collapse.

The mechanism describes what is physically happening:

- a query is slow;
- requests are blocked on a pool;
- a downstream call is waiting;
- a hot key concentrates load;
- work is repeated unnecessarily;
- the service has exceeded a local resource limit.

The root cause is the underlying condition that explains why the mechanism appeared.

### 2. Performance vs. capacity

Learn to separate:

- **inefficiency:** the system does too much work for the same result;
- **capacity:** the system has reached a real resource or architectural limit under the required workload.

### 3. Workload matters

"20× traffic" is incomplete information.

The relevant load characteristics can include:

- request rate;
- concurrency;
- request mix;
- read/write ratio;
- data size;
- hot-key distribution;
- expensive versus cheap endpoints;
- synchronous versus asynchronous work;
- dependency behavior under load.

The books explicitly describe load in terms of resources consumed and note that performance and capacity depend on the workload and architecture.

## Practice

Given:

> Traffic increases 10×. CPU reaches 95%. Latency increases 4×. Database CPU is 45%.

Before proposing a fix, write **five measurements or traces** you would inspect to distinguish between:

- legitimate compute saturation;
- inefficient application work;
- blocking or queueing;
- downstream latency;
- another bottleneck.

## Exit criteria

I can explain why "CPU is 95% → add servers" is an incomplete diagnosis.

I can state what evidence would make scaling appropriate and what evidence would point to optimization instead.

## Source path

- *Foundations of Scalable Systems* (S28), Ch. 1 (read) — scalability, replication, optimization, performance, bottlenecks.
- *Understanding Distributed Systems*, 2nd ed., Roberto Vitillo (S27), Ch. 1.3 [TOC] — performance, throughput, response time, capacity.

---
