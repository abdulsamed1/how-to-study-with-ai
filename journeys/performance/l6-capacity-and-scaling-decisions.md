---
purpose: Contains one part of the performance and traffic-spike study map.
read_when: When diagnosing or practising the named performance concern.
depends_on:
  - ../../workspace/mission.md
  - ../../workspace/resources.md
---

# L6 — Capacity and Scaling Decisions



## Target

Learn when scaling is actually the correct intervention and how to scale without moving the bottleneck somewhere else.

## Learn

### 1. Scale up vs. scale out

Understand the trade-off:

- **Scale up:** increase resources available to the existing processing unit.
- **Scale out:** add processing replicas.

Scaling is appropriate when the workload is genuinely exceeding the capacity of the affected resource.

### 2. Bottleneck migration

A classic production sequence:

```text
Application capacity is exhausted
           ↓
Add application replicas
           ↓
Application bottleneck improves
           ↓
Database receives more concurrent work
           ↓
Database becomes the bottleneck
```

This is not automatically a reason to avoid scaling. It is a reason to understand **the full resource chain** before and after the intervention.

### 3. Statelessness as a scaling enabler

When scaling application instances horizontally, the system needs to allow requests to move between instances without depending on instance-local session state.

This is a supporting concept, not a reason to redesign the whole application into microservices.

### 4. Load balancing

Learn only the operational decision surface:

- how traffic reaches multiple replicas;
- health checks;
- removing unhealthy instances;
- uneven/hot workloads;
- the cost and limitations of the load-balancing layer.

Vitillo notes that delayed load information can create surprising balancing behavior and that load balancing itself contributes to system performance and availability.

### 5. Autoscaling

Learn the relationship:

```text
Observed load / resource pressure
             ↓
Capacity policy
             ↓
Add/remove replicas
```

Do not learn autoscaling as "latency high → add pods." Learn which metric is causally connected to useful capacity.

### 6. The database follows the application

Every scaling decision must ask:

> "What shared resource receives the additional work?"

That includes:

- databases;
- caches;
- message brokers;
- external APIs;
- connection pools;
- storage;
- downstream services.

## Practice

Scenario:

> The service handles 1,000 RPS at P99 200 ms. At 1,500 RPS, P99 rises to 2 seconds. CPU is 92%. Database CPU is 40%. Query latency is stable. Profiling shows request-local CPU work is the dominant cost.

Choose between:

`optimize`, `scale up`, `scale out`.

Defend the decision from the evidence and state what you would measure after the change.

## Exit criteria

I can justify scaling from evidence and can predict at least one downstream bottleneck that the intervention could expose.

## Source path

- *Foundations of Scalable Systems* (S28), Ch. 1 (read), Ch. 2 [TOC] — replication, optimization, scale-up/scale-out, service/database bottlenecks, caching, queueing.
- *Understanding Distributed Systems* (S27), Ch. 1.3 [TOC] — capacity and scaling; Ch. 18 [TOC] — Network Load Balancing.
- *Designing Distributed Systems* (S29), Ch. 6 [TOC] — Replicated Load-Balanced Services.

---
