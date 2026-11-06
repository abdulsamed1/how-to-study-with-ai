---
purpose: Contains one part of the performance and traffic-spike study map.
read_when: When diagnosing or practising the named performance concern.
depends_on:
  - ../../workspace/mission.md
  - ../../workspace/resources.md
---

# L4 — Downstream Dependencies and Failure Propagation



## Target

Understand what happens when the system is healthy but one dependency becomes slow, unavailable, or partially degraded.

## Learn

### 1. Slow is a failure mode

A dependency does not have to return errors to damage the caller.

```text
Client
  ↓
API
  ↓
Slow dependency
  ↓
Requests remain open
  ↓
Concurrency accumulates
  ↓
Pools / threads / sockets become scarce
  ↓
Caller degrades
```

Vitillo describes slow network calls as difficult-to-detect failures because waiting consumes resources and can degrade the system.

### 2. Timeouts

Learn:

- why every potentially non-returning network operation needs bounded waiting;
- how timeout policy relates to downstream latency distribution;
- why timeout values must be observable;
- how timeout behavior prevents failure from propagating indefinitely.

### 3. Retries

Retries are not free capacity.

Learn:

- transient vs persistent failure;
- bounded retries;
- exponential backoff;
- jitter;
- retry storms;
- retry amplification across dependency chains;
- idempotency and correctness before retrying non-idempotent operations.

Vitillo explicitly shows that retries can worsen overload when performed immediately and that multiple retrying layers can amplify downstream load.

### 4. Circuit breaking / isolation

Study circuit breakers only to the depth required to answer:

> "How do I stop a failing dependency from taking down its callers?"

The important idea is **failure containment**, not memorizing a library API.

## Practice

Scenario:

> Your API calls a payment provider. The provider changes from 150 ms P95 to 5 seconds. The provider returns successful responses for most requests. The API has no application error spike yet, but its worker pool is filling and requests begin timing out.

Explain the mechanism and choose the first containment controls.

## Exit criteria

I can explain why:

`"dependency has no errors"` does **not** imply `"dependency is healthy"`.

I can reason about timeout, retry, and circuit-breaker trade-offs without treating them as a fixed trio that must always be installed.

## Source path

- *Understanding Distributed Systems* (S27), Ch. 24 [TOC] — Common Failure Causes.
- *Understanding Distributed Systems* (S27), Ch. 27 [TOC] — Downstream Resiliency: 27.1 Timeout; 27.2 Retry; retry backoff, jitter, and amplification; 27.3 Circuit breaker.

---
