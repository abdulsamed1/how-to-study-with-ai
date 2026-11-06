---
purpose: Contains one capstone phase section.
read_when: When the FDE capstone or its named support section is active.
depends_on:
  - ../../workspace/mission.md
  - ../../workspace/evidence.md
  - ../../workspace/resources.md
---

# 5. Suggested capstone shape


## 5. Suggested capstone shape

Start with a narrow workflow such as an internal operations request or support-triage process using synthetic or approved data. Do not start by building a general-purpose autonomous assistant.

1. **Deterministic baseline:** request intake, validation, persisted state, audit history, and a clear human workflow (the P2.1 Problem Card is the seed, not the final brief).
2. **Integration:** one external API or webhook with authentication, deduplication, bounded retries, and reconciliation.
3. **AI feature only if justified:** for example classification, extraction, or grounded knowledge lookup. Compare its results with a deterministic baseline.
4. **Evaluation and safety:** labelled test set, edge/adversarial cases, regression checks, permission controls, and human approval for consequential actions.
5. **Production shape:** observability, timeouts/budgets, deployment, rollback, small pilot, runbook, and honest impact measurement.

The capstone must remain small enough to finish and test. Add a component only when a requirement or observed failure justifies it. Build the backend, integration, and AI parts in Python with PostgreSQL; keep the model call behind a stable contract. Treat existing TypeScript/Node.js, Next.js, or NestJS projects as conditional code-reading contexts only when P7.7/P7.8 or a named target-role requirement justifies the work; they are not implementation requirements for the capstone. Delegate each slice from a written brief and close it with an agent review record.
