---
purpose: Contains one FDE journey support register or gate.
read_when: When checking FDE gates, sources, progress, or milestones.
depends_on:
  - journey-overview.md
  - ../../workspace/resources.md
---

# 4. Phase gates: proof before progression


## 4. Phase gates: proof before progression

| Gate | Required proof | Lessons generally involved |
|---|---|---|
| **G1 — Can build and debug** | Five-line Problem Card with labelled hypotheses and an initial success signal; reproducible repo that starts from the README and a lockfile; stub-provider call with one seeded provider failure and a regression test that fails before the fix and passes after; validated external data at trust boundaries; async contract plus runtime evidence for blocking I/O, cleanup, and configuration (closes after Phase 3) | Phases 2–3 |
| **G2 — Can build a correct service** | HTTP contract with error model, validation, database schema, migration, provider contract sheet, integration tests, agent review record for one diff, quality-attribute table, architecture ADR with fitness check | Phases 4–7 |
| **G3 — Understands failure and concurrency** | Idempotency, concurrency test, bounded retries, durable processing, outbox crash test, reconciliation replay | Phases 6–9 |
| **G4 — Can reason about production** | CI/CD with rollback rehearsal, logs/metrics/traces, SLI computed from fault runs, incident analysis with stakeholder update, executed fault matrix and runbook | Phase 9 |
| **G5 — Can choose and design an AI use case** | Option comparison including non-AI, system-design brief (requirements, capacity worksheet, diagrams, ADR with alternatives, failure/security risk matrix, validation plan), three fixed design exercises (P10.8), design review with go/adjust/stop (P10.7), baseline | Phase 10 |
| **G6 — Can build an LLM application with context** | Validated model interface, measurable retrieval, explicit state and failure behavior | Phases 11–12 |
| **G7 — Can measure AI quality and prevent regressions** | Versioned golden set, calibrated judge, separate retrieval/generation results, trace examples, and a CI gate that catches a seeded quality regression | Phase 14 |
| **G8 — Can bound and secure agent behavior** | Bounded tool use, sandbox boundary, explicit stop conditions, budgets, permissions, recovery and approval paths; threat model and adversarial tests | Phases 13 + 15 |
| **G9 — Can deliver and hand over** | Deployment evidence, pilot/feedback, outcome report, runbook, known limitations | Phases 16–17 |

Passing a gate means the user can explain and defend the evidence. It does not mean the user is guaranteed employment or that a lab is equivalent to production experience.
