---
purpose: Contains one part of the performance and traffic-spike study map.
read_when: When diagnosing or practising the named performance concern.
depends_on:
  - ../../workspace/mission.md
  - ../../workspace/resources.md
---

# Mastery Criteria



The journey is complete when I can handle the following cases without falling into a generic architecture checklist.

The evidence rule above applies to every box.

## Performance diagnosis

- [ ] I can explain why high CPU is a symptom, not automatically the root cause.
- [ ] I can distinguish CPU saturation from queueing/waiting.
- [ ] I can find where latency is spent using metrics, logs, and traces.
- [ ] I can use profiling to verify expensive execution paths.

## Database diagnosis

- [ ] I can detect query amplification such as N+1.
- [ ] I can reason from query count and query latency to database pressure.
- [ ] I can inspect query plans before assuming an indexing solution.
- [ ] I understand connection-pool exhaustion and blocking.
- [ ] I can recognize that scaling application instances can overload a shared database.

## Dependency resilience

- [ ] I can explain why slow dependencies are dangerous even when they return 200 responses.
- [ ] I can choose timeout behavior based on an explicit latency/error budget.
- [ ] I can reason about retries, backoff, jitter, and amplification.
- [ ] I can explain the correctness implications of retrying non-idempotent operations.

## Overload control

- [ ] I can distinguish rate limiting from load shedding.
- [ ] I can recognize when load leveling is appropriate.
- [ ] I can reason about queue backlog and consumer capacity.
- [ ] I can choose graceful degradation based on business-criticality.

## Scaling decisions

- [ ] I can justify scale-up vs scale-out from measured evidence.
- [ ] I can identify the likely downstream bottleneck created by a scaling change.
- [ ] I can explain why statelessness matters for horizontal scaling.
- [ ] I can discuss health checks and load balancing at the operational level.

## Production judgment

- [ ] I mitigate user impact before trying to perfect the root-cause fix.
- [ ] I can state what I do not know and what measurement would resolve the uncertainty.
- [ ] I validate changes under controlled load.
- [ ] I can turn an incident into prevention work: instrumentation, tests, limits, runbooks, and postmortem actions.

## Interview judgment

- [ ] I do not begin a 20× traffic answer by naming Redis, Kubernetes, or a load balancer.
- [ ] I start by establishing the observed failure and the bottleneck evidence.
- [ ] I select interventions conditionally.
- [ ] I explicitly discuss trade-offs and downstream effects.
- [ ] I can say, truthfully: **"I would diagnose the bottleneck first; the solution depends on which resource or dependency is actually limiting the system."**

## AI-system bridge

- [ ] I can explain why raising concurrency can lower throughput once a provider rate limit binds.
- [ ] I can decide which agent steps are safe to retry and which need idempotency protection.
- [ ] I can list the per-call fields needed to trace latency, cost, and failures of model calls.
- [ ] I can bound context growth and show with an evaluation set that quality held.
- [ ] I can choose a degradation order (smaller model, deterministic path, human review) by business criticality.

---
