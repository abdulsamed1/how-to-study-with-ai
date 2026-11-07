---
purpose: Contains one part of the FDE learning journey.
read_when: When the FDE journey or the named phase is active.
depends_on:
  - ../../workspace/mission.md
  - ../../workspace/resources.md
---

# Phase 6 — Transactions, concurrency, and correctness



**Goal:** Prevent data corruption when operations overlap or fail halfway.

**Handbook reading path (S69 [TOC]):** Ch. 15 §§15.1–15.14 (ACID, anomalies, PostgreSQL isolation/MVCC, locks and deadlocks, optimistic versus pessimistic control, queue tables, idempotency, serialization retries, long transactions); Ch. 12 §12.14 (state machines) and Ch. 13 §13.8 (atomic write/upsert patterns). Ch. 15 §15.15 (outbox/sagas) is reserved for Phase 8 so transaction-local correctness is distinguished from cross-system coordination.

- **P6.1 — Atomicity and transaction boundaries** — **Priority:** must-have. Depends on: P5.2–P5.6. Group state changes that must succeed or fail together. **Proof:** transactionally persist one business operation and test rollback. Source: F6, S19.
- **P6.2 — Isolation and anomalies** — **Priority:** important. Depends on: P6.1. Lost updates, non-repeatable/phantom reads, check-then-act races, and the PostgreSQL MVCC mental model; choose the isolation detail required by the reproduced failure rather than memorizing every anomaly. **Proof:** reproduce one race using two concurrent clients and identify the conflicting reads/writes from recorded evidence. Source: F6, S19; S69 ch. 15 §§15.3–15.5 [TOC].
- **P6.3 — Locking, optimistic concurrency, and uniqueness** — **Priority:** important. Depends on: P5.3, P6.1–P6.2. Unique constraints, version checks, row locks, deadlocks, and their trade-offs. A serialization/deadlock retry must retry the whole transaction only when the database's documented error semantics make that safe; this unit does not set the distributed retry policy from P8.3. **Owned-system lab (conditional code reading):** inspect Eagles' `version` fields (for example `eagles-wrms-app/src/objects/lead-attribution.object.ts`) against AD-13, then state which concurrent write AD-13's version check is meant to stop and whether the check is visible in application code or only in the decision record. **Proof:** fix the race from P6.2 and prove it with a concurrency test; explain the recovery boundary for one detected serialization/deadlock failure. Sources: F6, S19; S69 ch. 15 §§15.6–15.9, 15.13 [TOC].
- **P6.4 — Consistency invariants across multiple writes** — **Priority:** important. Depends on: P6.1–P6.3. Identify which records must remain consistent and what happens when only one write succeeds. This unit applies the **[failure-matrix template](journey-overview.md#3-lesson-design-and-completion-criteria)** — the first unit to use it, and where its shape is tested against a real multi-write case; the other applying units reuse it with their own delta. **Proof:** failure matrix for a multi-step state change, in the [failure-matrix template](journey-overview.md#3-lesson-design-and-completion-criteria). Sources: S19, S26.
- **P6.5 — Time, ordering, and duplicate events** — **Priority:** must-have. Depends on: P2.2, P4.5–P4.6, P6.1–P6.4. Event time vs processing time, duplicate delivery, out-of-order updates, and event identity. **Proof:** define a state transition table for repeated and stale events, including a stale read after a successful write (replication or provider-index lag). **AI-dependency bridge:** replay the P4.7b harness's duplicate-delivery mode against the P2.1 service's stored state and show which transition absorbs the duplicate and which rejects it. Sources: S19 ch. 6 (read: replication lag and stale reads), S27 ch. 8 [TOC], S65 (read: replica lag causing a duplicate payment in an idempotency store).
- **P6.6 — Design and defend one correctness invariant** — **Priority:** important. Depends on: P6.1–P6.5. Translate a business guarantee into DB constraints, transaction behavior, tests, and known limits. **Proof:** ADR + tests + written failure analysis; the invariant tests are designed by the learner before reading any generated implementation. Sources: F6, S19.
