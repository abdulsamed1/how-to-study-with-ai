---
purpose: Contains one FDE journey support register or gate.
read_when: When checking FDE gates, sources, progress, or milestones.
depends_on:
  - journey-overview.md
  - ../../workspace/resources.md
---

# 6. Supporting branches — not required all at once

The FDE core includes the database, architecture, distributed-systems, messaging, and production-resilience foundations in Phases 5–10. This register keeps deeper implementation specialties conditional. Do not defer a core unit merely because a nearby specialist topic is optional.

## Production performance and traffic spikes

Open the [performance journey](../performance/study-overview.md) when the P2.1 baseline or a Phase 9 diagnosis exposes a gap, or a real project needs it.

| FDE-map unit | Performance-map levels | Ownership |
|---|---|---|
| P9.6 (performance diagnosis) | L0–L4 | FDE map decides that diagnosis is needed; the performance map owns the detailed diagnostic method. |
| P9.9 (caching/read scaling) | L3.6, L5, L6.3–L6.4 | Phase 9 implements/tests the read-path behavior; the performance map supplies diagnostic criteria and failure modes. |
| P10.5 (overload mechanism decisions) | L5.1–L5.4, L6.3–L6.6 | FDE map owns include/defer/reject decisions; the performance map supplies measured-capacity and overload reasoning. |
| P10.6 (distribution trade-offs) | L6.1–L6.2, L6.6 | FDE map owns consistency/partitioning/coordination decisions; the performance map supplies scale-up/scale-out and bottleneck-migration reasoning. |
| P9.4, P9.7, P9.10–P9.11 | L8 scenarios A–G | The performance map supplies spike, slow-dependency, burst, hot-tenant, cache-loss, and isolation rehearsal scenarios. |
| P10.4a capacity estimates vs P9.6/P17.2 | L7 | P10.4a estimates; the performance map measures curves and capacity boundaries. |

## Conditional engineering specializations

Open only when a capstone requirement, measured gap, or named target role justifies the depth:

- **Consensus and coordination internals:** implement Raft/Paxos, advanced leases, distributed lock services, or quorum algorithms beyond the conceptual/design proof in P8.0e.
- **Conflict-free replicated data:** CRDT algorithms and multi-region active-active conflict resolution beyond the recognition boundary in P8.0c.
- **Streaming platforms:** full Kafka cluster operations, Flink/Spark deployment, state backends, checkpoint tuning, and streaming SQL beyond P8.10.
- **Distributed batch platforms:** scheduler internals, work stealing, large MapReduce frameworks, and large-scale data orchestration beyond P8.11.
- **Platform networking:** deep service-mesh, Kubernetes networking, ingress, and control-plane implementation beyond P9.8.
- **Analytical data platforms:** warehouse/lakehouse implementation and Data Mesh operating models beyond the decision-level P10.9.

AI Security specialization remains deeper after Phase 15 or when the capstone threat model requires it. Framework-specific tutorials remain out of scope unless a named existing-system task or target role requires them.
