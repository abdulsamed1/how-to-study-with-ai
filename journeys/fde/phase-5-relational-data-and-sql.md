---
purpose: Contains one part of the FDE learning journey.
read_when: When the FDE journey or the named phase is active.
depends_on:
  - ../../workspace/mission.md
  - ../../workspace/resources.md
---

# Phase 5 — Relational data and SQL



**Goal:** Model persisted facts correctly before relying on AI or distributed behavior.

**Handbook reading path (S69 [TOC]):** Ch. 12 §§12.1–12.10, 12.14, 12.18–12.19 (relational modeling, constraints, status/state, schema review); Ch. 13 §§13.1–13.10, 13.15, 13.17, 13.19 (NULL semantics, joins, aggregation, CTE/window queries, writes, search, roles); Ch. 14 §§14.2–14.15, 14.18, 14.20 (indexes, plans, N+1, pagination, connections, replication lag, DDL locks); Ch. 16 §§16.1–16.7 (migration safety). Use Ch. 37 §37.12 only if an ORM/migration library is selected for the Python capstone; SQL remains the required foundation.

- **P5.1 — Relational modeling and data invariants** — **Priority:** important. Depends on: P2.3, P4.3. Entities, relationships, keys, cardinality, nullability, and invariants. **Proof:** schema sketch for users, requests, events, and processing state. Source: F6.
- **P5.2 — SQL reads/writes, joins, aggregation** — **Priority:** must-have. Depends on: P5.1. CRUD, filtering, NULL semantics, joins, grouping, ordering, and transaction boundaries. Add CTEs, window functions, and `RETURNING`/`UPSERT` when a concrete query or invariant calls for them; do not study each feature in isolation from a business question. **Proof:** answer representative business questions with SQL rather than application loops, including one ranked/top-per-group query and one safe write whose result is checked. Source: F6; S69 ch. 13 §§13.1–13.10 [TOC].
- **P5.3 — Constraints and integrity** — **Priority:** must-have. Depends on: P5.1–P5.2. Primary/foreign keys, uniqueness, check constraints, and why application checks alone can race. **Proof:** encode key invariants in the database. **AI-dependency bridge:** take one validated provider record and show that its business invariant is enforced by the schema (or an explicit state), so an absent or null field cannot silently become a default that later reads as fact. Source: F6.
- **P5.4 — Indexes and query plans** — **Priority:** important. Depends on: P5.2–P5.3. Query patterns, selectivity, composite/partial index trade-offs, `EXPLAIN` versus actual execution evidence, and the write/storage cost of indexes. Include N+1 and OFFSET-versus-keyset pagination when the measured access pattern makes them relevant; do not add an index from intuition alone. **Proof:** capture the same query's plan and measured latency before/after one justified index or query-shape change, and state the trade-off and what the measurement cannot establish. Sources: F6; S69 ch. 14 §§14.2–14.15 [TOC].
- **P5.5 — Schema migrations and safe change** — **Priority:** must-have. Depends on: P5.1–P5.4, P2.1. Versioned schema changes, backfill, deploy order, rollback limits, and compatibility. **Proof:** perform an additive migration and document its rollout sequence, then complete one expand → backfill → contract change while the old and new application versions both pass tests against the intermediate schema; review any agent-generated migration for destructive or locking steps before running it. Source: F6.
- **P5.6 — Database access from the application** — **Priority:** must-have. Depends on: P3.4, P4.7a, P5.1–P5.5. Parameterized queries or a query builder, connection pooling concepts, mapping and validation. **Proof:** persist and retrieve capstone records with tests; one parameterized query is written by hand, and state what the connection pool bounds. Sources: F3, F6.
- **P5.7 — Backup, restore, and data lifecycle basics** — **Priority:** important. Depends on: P5.5–P5.6. What backups protect, what they do not, retention/deletion, and restore verification. This unit owns the data-level evidence; service-level degradation and RTO/RPO drills are P9.7, which reuses this proof. **Proof:** document and test a local recovery procedure. Sources: S25, F10.
