---
purpose: Contains one part of the performance and traffic-spike study map.
read_when: When diagnosing or practising the named performance concern.
depends_on:
  - ../../workspace/mission.md
  - ../../workspace/resources.md
---

# L1 — Measure and Localize: Build the Evidence Path



## Target

Turn an incident into a measurable search problem.

## Learn

### 1. Request-level signals

Know how to reason about:

- throughput / requests per second;
- response-time distributions;
- latency percentiles such as P95 and P99;
- error rate;
- timeouts;
- concurrency;
- queue depth where applicable.

Vitillo emphasizes throughput and response time as primary performance measures and explains why percentiles provide a better view of user experience than an average alone.

### 2. Resource and dependency signals

At minimum, be able to correlate application behavior with:

- CPU;
- memory;
- resource-pool utilization;
- database response time;
- database connection usage;
- dependency availability and latency;
- queue depth;
- cache hit/miss behavior when caching is involved.

### 3. Metrics → logs → traces

Learn the distinction:

- **Metrics** help detect and trend system behavior.
- **Logs** provide detailed event context.
- **Traces** connect latency and behavior across request boundaries.

Vitillo describes monitoring as focused on detecting failures and system health, while observability adds the ability to understand and debug system behavior by providing granular context.

### 4. Hypothesis-driven investigation

Do not inspect every signal equally.

Form a hypothesis:

> "The latency increase is caused by database wait time."

Then choose telemetry that can confirm or reject it:

- request trace;
- database timing;
- query duration;
- connection-pool wait;
- database CPU/locks;
- deployment timeline.

## Practice

Scenario:

> P99 latency doubled. CPU is 55%. Memory is stable. Error rate is unchanged. One endpoint is affected, and the endpoint spends most of its time waiting on another service.

Construct the evidence chain you would collect before changing architecture.

## Exit criteria

I can move from a dashboard symptom to a bounded hypothesis and name the telemetry that would falsify it.

## Source path

- *Understanding Distributed Systems* (S27), Ch. 31 [TOC] — Monitoring; Ch. 32 [TOC] — Observability.
- *Designing Distributed Systems*, 2nd ed., Brendan Burns (S29), Ch. 14 (read: monitoring and observability patterns) — metrics, request monitoring, alerting, tracing.
- *Foundations of Scalable Systems* (S28), Ch. 5 [TOC] material on application-service metrics, queues, thread pools, database connection pools, and data-driven performance experiments.

---
