---
purpose: Contains one part of the performance and traffic-spike study map.
read_when: When diagnosing or practising the named performance concern.
depends_on:
  - ../../workspace/mission.md
  - ../../workspace/resources.md
---

# L8 — Full Production Scenarios and Senior-Level Reasoning



## Target

Integrate the branches into realistic incidents without falling back to a memorized architecture recipe.

## Scenario set

### Scenario A — Traffic spike + high CPU

Possible mechanisms to discriminate:

- legitimate compute saturation;
- inefficient request processing;
- hot endpoint;
- excessive allocation/GC;
- lock/contention;
- a downstream failure causing local work to accumulate.

### Scenario B — Traffic spike + normal CPU + high latency

Possible directions:

- database latency;
- connection-pool wait;
- downstream network wait;
- queueing;
- locks;
- external service degradation.

### Scenario C — Scale-out makes the database fail

Investigate:

- query volume per request;
- total query rate;
- connection counts;
- hot queries;
- missing/ineffective indexes;
- locking;
- read amplification;
- cache behavior.

### Scenario D — Dependency becomes slow but still returns 200

Investigate:

- timeout configuration;
- worker/connection occupancy;
- retry behavior;
- retry amplification;
- circuit breaking/isolation;
- fallback or degraded behavior.

### Scenario E — Burst of asynchronous work

Investigate:

- whether the user needs synchronous completion;
- queue/load-leveling suitability;
- worker throughput;
- backlog growth;
- retry behavior;
- poison work;
- database write capacity.

### Scenario F — One tenant or API key dominates the workload

Investigate:

- rate-limiting policy;
- fairness;
- local versus global limits;
- business priority;
- whether rejected work should be retried;
- the cost of enforcing the quota itself.

### Scenario G — Cache disappears and the origin collapses

Investigate:

- cache hit ratio;
- origin capacity;
- cache warm-up behavior;
- request coalescing/thundering-herd risk;
- load shedding at the origin;
- whether the system can continue more slowly without the cache.

Vitillo explicitly treats caching as an optimization and discusses the possibility of cache failure causing a sudden origin surge.

---
