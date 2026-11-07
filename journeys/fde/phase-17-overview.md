---
purpose: Contains one capstone phase section.
read_when: When the FDE capstone or its named support section is active.
depends_on:
  - ../../workspace/mission.md
  - ../../workspace/evidence.md
  - ../../workspace/resources.md
---

# Phase 17 — Capstone and evidence portfolio


---
purpose: Contains one part of the FDE learning journey.
read_when: When the FDE journey or the named phase is active.
depends_on:
  - ../../workspace/mission.md
  - ../../workspace/resources.md
---


**Goal:** Demonstrate end-to-end ownership. This phase is open-ended and should evolve from lessons and real constraints; it is not a fixed tutorial to copy.

**Handbook reading path (S69 [TOC]):** Ch. 29 §§29.2–29.11 and Ch. 30 §§30.0–30.12 for design and case-study comparison; Ch. 21 §§21.1–21.3, 21.5, 21.7, 21.10–21.19, Ch. 22 §§22.10–22.11, and Ch. 24–27 for tests, review, deployment, releases, operations, and handover; Ch. 32–33 for the chosen AI slice. A handbook case study is an example to critique, never evidence that the learner shipped a system or achieved a business result.

- **P17.1 — Select a narrow, high-value workflow** — **Priority:** must-have. Depends on: P10.1–P10.3, P10.4a–P10.4c, P16.1. Confirm access to data/users, a measurable baseline, bounded risks, and a reason AI is appropriate. **Artifact:** problem brief, baseline, stakeholder map, and explicit non-goals. Sources: [evidence policy](../../governance/evidence-policy.md); external scoping sources remain unverified — the real engagement is the evidence.
- **P17.2 — Build in vertical slices** — **Priority:** must-have. Depends on: P4.7a–P4.7b, P5.6, P7.2, P8.2–P8.7, plus the AI units chosen in P17.1 from this list: P11.2–P11.4, P12.1–P12.6, P13.1–P13.5, P14.1–P14.4, P15.1–P15.4. Each slice must run and be tested before the next layer is added, starts from a written delegation brief, is small enough to review, and ends with an agent review record (§3). **Artifact:** repository with tests, migrations, integration contract, failure-path coverage, and an agent review record per slice. Sources: S40, S41.
- **P17.3 — Produce the evidence pack** — **Priority:** must-have. Depends on: P7.5b, P9.3–P9.7, P10.4c, P14.1–P14.6, P15.1–P15.6, P16.2–P16.5. **Artifact:** ADRs, architecture diagram, threat model, evaluation report, trace examples, runbook, rollout plan, known-limitations list, impact report, and the agent review records. Mark simulated evidence explicitly and state which agent-written parts were independently verified. Source: [evidence policy](../../governance/evidence-policy.md).
- **P17.4 — Defend decisions and failure scenarios** — Implementation unit (multi-session). **Priority:** must-have. Depends on: every must-have unit plus the AI units chosen in P17.1 (an explicit list is recorded in the P17.1 problem brief; no vague 'all relevant lessons'). Explain why this design, what alternatives were rejected, where it fails, how a failure is detected, how the system recovers, and what remains unproven; state which parts an agent wrote, how each was verified, and why the accepted changes can be trusted. Extend the defense to the resume projects: build one decision defense card (section 3) for each top-ranked in-scope family — Twenty/NestJS host boundary, Eagles authorization, lead-assignment concurrency, Eagles data lifecycle and attribution, opran's Next.js server/client data flow, and opran's credential-lifecycle and retry decisions — and verify each card's evidence from code, a test, or a recorded run; where a platform-provided decision cannot be exercised, mark it `docs-only` and cap the claim at the documented behavior. Rank families by interview likelihood × the learner's demonstrated depth gap; where depth is unknown, run a diagnostic and record it before ranking. For outside-scope decisions (Cloudflare Workers mechanisms, data provenance, and terms-of-service exposure), the card target is Depth 1: state the decision and tradeoff as the project's ADR does, and make no mechanism claims. **Artifact:** concise case deck, the cards, and scenario walkthrough. Sources: [evidence policy](../../governance/evidence-policy.md), [agentic systems](../../teaching/agentic-systems.md), and journey §3; opran and eagles decision records (docs-only until code-verified).

---

#### Artifact templates

Shared artifact shapes are defined once here, so no unit invents a second format. A unit that uses a template may add a scenario-specific delta — an extra column, a row set, or a filled-in section — but must name that delta in its own proof.

- **Failure-matrix template** — columns: `failure | detection | containment | recovery | owner`. It is defined here rather than in a unit because Phase 4 already needs it. Applied by: P4.8b (provider-side faults), P6.4 (multi-write invariants), P8.1 (ambiguous outcomes), P9.7 (service-level recovery), P10.4c (failure and security risk in the design brief), P10.8 (exercise scenarios), P16.1 (AI-dependency containment). Each applying unit states its own delta.
- **Decision defense card template** — fields: `decision`; `context and constraints`; `options considered`; `chosen`; `rejected options and why`; `tradeoff accepted (technical, operational, commercial)`; `what would make it wrong`; `evidence (file, commit, test, or recorded run)`; `authorship (owner / agent-proposed and owner-approved / platform-provided)`; `verified-by (code, test, run, or docs-only)`; `depth reached (0–5)`; `two likely follow-up questions`; `owner's explanation` (left empty until the learner answers unaided). Cards may be seeded from project docs, but every seeded fact is marked `docs-only` until a code, test, or run check confirms it. For a decision outside the study scope, the target is Depth 1: explain the decision and the tradeoff as the project's ADR states it, and make no mechanism claims. Applied by: P17.4; the owned-system labs in Phases 2–9 may seed individual fields.

#### Retrieval table

Every must-have unit is re-tested in a changed scenario by the named later unit, per `../../teaching/session-protocol.md` P§5 (retrieval and spacing). No per-unit Retrieval field is written in the unit lines; this table is the single definition.

| Unit | Re-tested by | Changed-scenario prompt |
|---|---|---|
| P2.1 | P10.1 | Re-frame the Problem Card for a second, real workflow; declare baseline and constraints again from scratch. |
| P2.1 | P9.2 | Prepare a hotfix release: branching, history, and revert decisions under release pressure. |
| P2.2 | P4.7a | Read an unfamiliar change in the capstone repo and predict its blast radius before running it. |
| P2.2 | P11.3 | Treat an untrusted model response as data entering a trust boundary; validate and reject poisoned fields. |
| P2.3 | P3.6 | Propagate cancellation through the async contract and prove no work outlives its request. |
| P3.4 | P17.2 | Reproduce the capstone slice from a lockfile and scripts with no oral context. |
| P3.5 | P9.6 | From live runtime evidence, find a blocking operation that throttles concurrency in the running service. |
| P3.6 | P8.5 | Kill a worker mid-task and account for every in-flight resource of the at-least-once queue. |
| P4.4 | P13.2 | Design tool permissions: who may call the tool, scoped to what; test allowed and denied calls. |
| P4.5 | P8.3 | Apply a budget to a retry policy and explain which outcomes stay client-retryable. |
| P4.6 | P8.6 | Evolve an API contract without breaking the dual-write/outbox consumers. |
| P4.7a | P17.2 | Extend an existing vertical slice with a contract change and keep its tests honest. |
| P4.7b | P9.7 | Trigger each fault mode of the shared harness during a full degradation drill. |
| P4.8a | P13.5 | Onboard an MCP server like a third-party provider: document its guarantees, tag documented/observed/unknown. |
| P4.9 | P15.3 | Audit the role matrix you issued against a least-privilege policy: for each role, name the actions the policy should deny and show your matrix denies them (issuance side, not tool-consumption side). |
| P4.8b | P13.5 | Drive a token lifecycle against a server whose documented auth differs from its observed behavior. |
| P5.2 | P8.7 | Write the reconciliation query that finds divergent aggregates across two stores. |
| P5.3 | P6.1 | Decide which invariant is enforced by a constraint and which must live inside the transaction. |
| P5.5 | P16.3 | Schedule a schema migration inside a progressive rollout with rollback criteria. |
| P5.6 | P8.7 | Diagnose an application-level data divergence: code bug or data drift; prove which. |
| P6.1 | P8.6 | Redraw transaction boundaries so the outbox write and the state change commit atomically. |
| P6.5 | P8.5 | Explain where measured time comes from, and what duplicates an event delivered at a scaling edge. |
| P7.2 | P14.1 | Build adversarial evaluation cases from requirements the way representative tests were built. |
| P7.3 | P14.2 | Choose graders for the model pipeline exactly as test doubles were chosen: what is faked, what is not. |
| P7.4 | P17.2 | Refactor a slice after agent-written changes and defend the diff in a review record. |
| P8.2 | P13.2 | Make every tool invocation idempotent, including retries by the model's caller. |
| P8.3 | P11.4 | Honor provider rate limits and budget a model call like a dependency call. |
| P8.4 | P13.4 | Accept an event you did not design: signature, ordering, and replay against your receiver contract. |
| P8.5 | P16.1 | Contain a failing AI dependency while the worker keeps delivering without duplicate business effects — what the at-least-once queue guarantees under the containment policy. |
| P8.6 | P17.2 | Investigate a slice's partial write: which side committed, and how the saga compensates. |
| P8.7 | P16.3 | Decide the rollout's verification step: which state the reconciliation loop must reach before expanding. |
| P9.2 | P16.3 | Roll back a deployed pilot using the established release workflow. |
| P9.3 | P17.3 | Walk a stakeholder through one trace from the evidence pack, tying log to span to business step. |
| P9.4 | P16.5 | Report the pilot: which SLI moved, whether the error budget survived, and what did not get measured. |
| P9.7 | P17.2 | Keep a degraded slice serving within stated limits while the failure is fixed. |
| P11.2 | P14.1 | Explain an evaluation failure through the raw request/response metadata, not through folklore. |
| P14.1 | P17.3 | Defend the provenance of every case in the evidence pack's evaluation report. |
| P14.4 | P17.3 | Show which regression gate each capstone change passed and why it was set at that threshold. |
| P15.1 | P15.2 | Model a new adversary (the model itself is untrusted) against the updated trust boundaries. |
| P17.1 | P17.2 | Justify the slice order of the chosen workflow when scope pressure cuts the timeline in half. |
| P17.2 | P17.3 | Assemble the evidence pack per slice, using the review records and traces produced along the way. |
| P17.3 | P17.4 | Defend the evidence pack against a hostile reviewer who discounts one line of evidence. |
| P17.4 | capstone debrief | Re-run the decision defense in a changed scenario (new constraint, new failure) after the debrief. |
