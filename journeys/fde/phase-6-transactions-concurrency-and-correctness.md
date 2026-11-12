---
purpose: Contains one part of the FDE learning journey.
read_when: When the FDE journey or the named phase is active.
depends_on:
  - ../../workspace/mission.md
  - ../../workspace/resources.md
---

# Phase 6 — Transactions, concurrency, and correctness

**Goal:** Prevent data corruption when operations overlap, fail halfway, or observe state that has changed elsewhere.

**Handbook reading path (S69 [TOC]):** Ch. 15 §§15.1–15.14 (ACID, anomalies, PostgreSQL isolation/MVCC, locks and deadlocks, optimistic versus pessimistic control, queue tables, idempotency, serialization retries, long transactions); Ch. 12 §12.14 (state machines) and Ch. 13 §13.8 (atomic write/upsert patterns). Ch. 15 §15.15 (outbox/sagas) remains in Phase 8 so transaction-local correctness is distinguished from cross-system coordination.

- **P6.1 — Atomicity and transaction boundaries** — **Priority:** must-have. Depends on: P5.2–P5.6. Group state changes that must succeed or fail together. **Proof:** transactionally persist one business operation and test rollback. Sources: F6, S19.
- **P6.2 — Isolation and anomalies** — **Priority:** important. Depends on: P6.1. Lost updates, non-repeatable/phantom reads, check-then-act races, and PostgreSQL MVCC. Choose the isolation detail required by the reproduced failure rather than memorizing every anomaly. **Proof:** reproduce one race using two concurrent clients and identify the conflicting reads/writes from evidence. Sources: F6, S19.
- **P6.3 — Locking, optimistic concurrency, and uniqueness** — **Priority:** important. Depends on: P5.3, P6.1–P6.2. Unique constraints, version checks, row locks, deadlocks, and their trade-offs. A serialization/deadlock retry must retry the whole transaction only when the database's documented error semantics make that safe; distributed retry policy belongs to P8.3. **Proof:** fix the race from P6.2 with a concurrency test and explain the recovery boundary. Sources: F6, S19.
- **P6.4 — Consistency invariants across multiple writes** — **Priority:** important. Depends on: P6.1–P6.3. Identify which records must remain consistent and what happens when only one write succeeds. Apply the [failure-matrix template](journey-overview.md#3-lesson-design-and-completion-criteria). **Proof:** failure matrix for a multi-step state change. Sources: S19, S26.
- **P6.5 — Time, ordering, and duplicate events** — **Priority:** must-have. Depends on: P2.2, P4.5–P4.6, P6.1–P6.4. Event time versus processing time, duplicate delivery, out-of-order updates, and event identity. Distributed clock behavior is deepened in P8.0b. **Proof:** define a state-transition table for repeated and stale events, including a stale read after a successful write. Sources: S19 ch. 6 (read: replication lag and stale reads), S27 ch. 8 [TOC], S65.
- **P6.6 — Design and defend one correctness invariant** — **Priority:** important. Depends on: P6.1–P6.5. Translate a business guarantee into database constraints, transaction behavior, tests, and known limits. **Proof:** ADR + tests + written failure analysis; design invariant tests before reading any generated implementation. Sources: F6, S19.
- **P6.7 — Serializable isolation and advanced conflict control** — **Priority:** important. Depends on: P6.2–P6.3, P6.6. Study write skew and predicate-level conflicts, serializable execution, and why some databases abort a transaction rather than permit a non-serializable result. Compare the documented PostgreSQL approach with locking and constraints. Do not turn this into a survey of every database isolation implementation. **Proof:** reproduce a write-skew anomaly under a weaker isolation level, then protect the invariant with an appropriate constraint, lock, or serializable transaction; include the required whole-transaction retry test and explain its safety boundary. Sources: S19 ch. 6 (read: consistency/replication sections where relevant), F6 PostgreSQL 18 docs, ch. 13; S27 ch. 10 [TOC].
