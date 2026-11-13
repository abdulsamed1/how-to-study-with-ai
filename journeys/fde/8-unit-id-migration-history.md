---
purpose: Preserves historical lesson-ID changes for traceability; it is not a learner progress ledger.
read_when: When interpreting retired or migrated unit IDs in the FDE journey.
depends_on:
  - journey-overview.md
  - ../../workspace/resources.md
---

# 8. Unit ID migration history

This file records only structural history: retired unit identifiers and their successor units. It contains no completion checkboxes, learner status, or evidence records. Retired IDs are never reused.

| Old ID | New ID | Structural change |
|---|---|---|
| P0.1 | P2.1 + P10.2 | Merged/split by responsibility. The demo / working-system / deployed-outcome distinction remains in the [delivery loop](../../teaching/delivery-loop.md) and is applied in P10.2; P2.1 no longer draws a delivery-loop diagram. |
| P0.2 | P2.1 | Merged. Toolchain setup and the initial Problem Card moved into P2.1. |
| P0.3 | P2.1 + P10.1 | Split by stage. P2.1 owns the five-line Problem Card; P10.1 produces the evidence-informed workflow map and problem statement. |
| P1.1 | P2.1 | Merged. Virtual environment, paths, processes, and environment variables are bootstrapped in P2.1. |
| P1.2 | P2.1 + P9.2 | Split by stage. Repository initialization stays in P2.1; branching and merge-conflict resolution move to the P9.2 release rehearsal. |
| P1.3 | P2.2 | Merged. Code reading across an unfamiliar codebase is practised in the P2.2 owned-system lab. |
| P1.4 | P2.2 | Merged. Runtime failure reproduction, inspection, and regression verification are covered by the P2.2 fixture harness. |
| P1.5 | P2.2 | Merged. Requirement-first testing and red/green assertions are covered by P2.2 validation fixtures. |
| P3.3 | P2.2 | Merged. Runtime validation at trust boundaries has one owner in P2.2. |
| P4.7 | P4.7a + P4.7b | Split into HTTP service/client and shared fault-injection harness. |
| P4.8 | P4.8a + P4.8b | Split into provider contract sheet/drift tests and credential lifecycle/failure matrix. |
| P7.5b (old combined unit) | P7.5b + P7.5c; retired combined ID P7.5t | Split architecture diagrams/ADRs from fitness functions/risk analysis. The live P7.5b remains the diagrams/ADR unit. |
| P10.4 | P10.4a + P10.4b + P10.4c | Split the system-design brief into requirements/capacity, interfaces/data/components, and failure/operations/validation. |

The migration history is retained so old references can be interpreted. It is not used to determine which lessons the learner has completed.
