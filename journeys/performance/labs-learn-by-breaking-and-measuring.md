---
purpose: Contains one part of the performance and traffic-spike study map.
read_when: When diagnosing or practising the named performance concern.
depends_on:
  - ../../workspace/mission.md
  - ../../workspace/resources.md
---

# Labs — Learn by Breaking and Measuring



The project should have a small repeatable lab environment where the same API can be subjected to different failure modes. Run it as the TypeScript/Node.js capstone service plus the P4.7b stub provider; Lab 8's stub model service may be written in Python where the AI lessons require it. When an agent wrote the code under test, state the hypothesis and the measurement before reading the code (journey rule 10 and P9.3's proof).

## Lab 1 — CPU inefficiency

Create an endpoint with intentionally expensive request-local work.

Measure:

- RPS;
- P95/P99;
- CPU;
- request cost.

Change the implementation, then compare the same workload.

**Goal:** experience optimization increasing capacity without adding replicas.

## Lab 2 — Database amplification

Create an endpoint that retrieves a collection and then performs repeated database lookups per item.

Measure:

- queries/request;
- total query rate;
- database latency;
- connection usage;
- API latency.

Replace the access pattern with a set-based approach and re-measure.

**Goal:** connect application-level structure to database pressure.

## Lab 3 — Pool exhaustion

Introduce a deliberately slow dependency or database operation.

Increase concurrency while keeping CPU moderate.

Measure:

- in-flight requests;
- pool wait time;
- queue depth;
- timeout rate.

**Goal:** see how waiting can dominate response time even without CPU saturation.

## Lab 4 — Downstream retry storm

Create a dependency that intermittently fails.

Compare:

- immediate retries;
- capped backoff;
- jitter;
- no retry for permanent errors.

**Goal:** observe retry amplification rather than learning it only as a definition.

## Lab 5 — Burst + queue

Create asynchronous work that does not need to finish during the request.

Compare:

- synchronous processing;
- queued processing.

Then push arrival rate above worker capacity temporarily and observe backlog behavior.

**Goal:** understand what a queue absorbs and what it does not solve.

## Lab 6 — Scale-out shifts the bottleneck

Run the same workload with:

`1 → 2 → 4 → 8 application replicas`

while keeping a shared database resource bounded.

Track the point at which the database becomes the limiting resource.

**Goal:** experience bottleneck migration directly.

## Lab 7 — Cache as an optimization, not a dependency

Introduce a cache in front of a slower origin.

Measure:

- hit ratio;
- origin request rate;
- latency;
- memory use as the number of distinct keys grows without a bound, diagnosed from runtime evidence, and the effect of adding a size bound;
- behavior when the cache is unavailable.

**Goal:** see both the benefit and the failure mode.

## Lab 8 — LLM call under rate limits (L9)

Put a stub model service in front of a worker pool. Make the stub slow with a long tail, and make it return rate-limit errors above a request-rate threshold. Run the pool at increasing concurrency.

Compare:

- fixed retries;
- capped exponential backoff with jitter and a retry budget;
- a queue with a worker count set below the stub's limit.

Measure throughput, error rate, wasted calls, and total cost units.

**Goal:** see that raising concurrency past the provider limit lowers useful throughput, and that retries can multiply load.

## Lab 9 — Context growth and an evaluation gate (L9)

Build a small agent loop whose history grows each step. Measure latency and token counts per step. Add a bound (truncate or summarize) and re-measure. Run a small evaluation set before and after.

**Goal:** treat context as bounded state, and prove that a performance change did not break quality.

---
