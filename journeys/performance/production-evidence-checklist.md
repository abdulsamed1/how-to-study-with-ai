---
purpose: Contains one part of the performance and traffic-spike study map.
read_when: When diagnosing or practising the named performance concern.
depends_on:
  - ../../workspace/mission.md
  - ../../workspace/resources.md
---

# Production Evidence Checklist



Use this before proposing a fix in a real incident.

## Request behavior

- [ ] RPS / throughput
- [ ] P50 / P95 / P99 latency
- [ ] Error rate
- [ ] Timeout rate
- [ ] Concurrency
- [ ] Endpoint/request mix

## Application

- [ ] CPU
- [ ] Memory
- [ ] Allocation / GC behavior where relevant
- [ ] Thread / worker saturation
- [ ] Queue/wait time
- [ ] Internal pool saturation
- [ ] Profile of expensive paths

## Database

- [ ] Query count per request
- [ ] Query latency
- [ ] Query plan
- [ ] Connection-pool utilization
- [ ] Locks/blocking
- [ ] CPU / I/O
- [ ] Hot queries / hot keys
- [ ] Read/write distribution

## Dependencies

- [ ] Downstream latency
- [ ] Downstream error rate
- [ ] Timeout behavior
- [ ] Retry volume
- [ ] Retry amplification
- [ ] Dependency-specific quotas/limits

## Protection mechanisms

- [ ] Rate limits
- [ ] Load shedding
- [ ] Queue depth / backlog
- [ ] Worker throughput
- [ ] Graceful degradation
- [ ] Cache hit ratio and origin load

## After the fix

- [ ] Did the original bottleneck improve?
- [ ] Did throughput improve?
- [ ] Did tail latency improve?
- [ ] Did correctness remain intact?
- [ ] Did cost remain acceptable?
- [ ] Did the bottleneck move downstream?
- [ ] Can the failure be reproduced in a controlled test?

---
