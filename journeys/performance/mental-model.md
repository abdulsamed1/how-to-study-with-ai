---
purpose: Contains one part of the performance and traffic-spike study map.
read_when: When diagnosing or practising the named performance concern.
depends_on:
  - ../../workspace/mission.md
  - ../../workspace/resources.md
---

# Mental Model



There are two different questions that are often mixed together.

### Performance

**How efficiently does the current system perform work?**

Examples:

- too much CPU work per request;
- excessive allocations or blocking;
- unnecessary database round trips;
- inefficient queries;
- contention;
- slow network calls;
- long queues caused by limited resources.

### Scalability / Capacity

**How much load can the system handle while continuing to meet its required behavior?**

Foundations of Scalable Systems frames scalability around increasing capacity in some operational dimension and identifies two broad ways to increase capacity: **replication** and **optimization**. It also explicitly warns that replicating resources that are not the real bottleneck adds cost without giving a scalability benefit.

**Study implication:** optimization can increase capacity; replication can increase capacity; neither should be selected before the constraint is understood.

> Source: *Foundations of Scalable Systems* (S28), Ian Gorton, Ch. 1 (read), especially the sections on scalability, replication, optimization, performance, and the relationship between bottlenecks and added capacity.

---
