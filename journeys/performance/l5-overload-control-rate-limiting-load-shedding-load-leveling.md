---
purpose: Contains one part of the performance and traffic-spike study map.
read_when: When diagnosing or practising the named performance concern.
depends_on:
  - ../../workspace/mission.md
  - ../../workspace/resources.md
---

# L5 — Overload Control: Rate Limiting, Load Shedding, Load Leveling



## Target

Learn to control incoming work when demand exceeds what the system can safely process.

## Learn

### 1. Load shedding

Load shedding is a response to **local overload**.

Vitillo's model:

```text
Current local work
       ↓
Is the service over its safe capacity?
       ↓
Reject excess work early
       ↓
Protect work already in progress
```

It can be selective when requests have different priorities.

### 2. Rate limiting

Rate limiting is different from local load shedding.

It controls a quota based on a key such as:

- user;
- API key;
- tenant;
- IP address;
- another application-specific identity.

The study target is the **policy distinction**:

- load shedding → local protection from overload;
- rate limiting → traffic control according to a quota/global policy.

### 3. Load leveling with queues

When the client does not need immediate completion, asynchronous work can decouple arrival rate from processing capacity.

```text
Producer
   ↓
Queue
   ↓
Workers
   ↓
Database / external service
```

The queue absorbs short-lived bursts by allowing consumers to work at their own pace.

But learn the failure mode too:

- backlog growth;
- consumer lag;
- poison messages / repeated failures;
- downstream saturation;
- indefinite backlog if arrival rate remains above service rate.

### 4. Graceful degradation

Learn to protect the business-critical path by changing non-critical behavior under pressure.

Examples from the supplied material include:

- delaying background email/SMS work;
- reducing expensive reports;
- disabling non-critical recommendations.

The decision must be tied to business priority, not applied mechanically.

## Practice

Scenario:

> A flash sale creates a short burst of writes. Users only need confirmation that the event was accepted; persistence can complete asynchronously. The downstream database cannot safely process the burst synchronously.

Compare:

`load shedding` vs `rate limiting` vs `queue/load leveling`.

State which one addresses the user-visible requirement and what new failure mode the choice introduces.

## Exit criteria

I can distinguish the three controls and choose among them based on **work semantics and overload behavior**, not tool familiarity.

## Source path

- *Understanding Distributed Systems* (S27), Ch. 28 (read) — Upstream Resiliency: 28.1 Load Shedding; 28.2 Load Leveling; 28.3 Rate Limiting; 28.4 Constant Work.
- *Foundations of Scalable Systems* (S28), Ch. 2 [TOC] — increasing responsiveness with asynchronous queueing.
- *Designing Distributed Systems* (S29), Ch. 11 [TOC] — Work Queue Systems; Ch. 12 [TOC] — Event-Driven Batch Processing.

---
