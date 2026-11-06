---
purpose: Contains one capstone phase section.
read_when: When the FDE capstone or its named support section is active.
depends_on:
  - ../../workspace/mission.md
  - ../../workspace/evidence.md
  - ../../workspace/resources.md
---

# 10. Capability milestone progression (competency-driven; project-first sequencing)


## 10. Capability milestone progression (competency-driven; project-first sequencing)

**Purpose.** This section defines the competency-based milestone progression and route classification. It follows the hands-on project-first sequencing adapted from `ai-roadmap-2026`: Phases 0 and 1 were merged into Phase 2 as the first runnable service, with Gate G1 closing after Phase 3. Live unit IDs from P2.1 onward remain stable. Progression is strictly self-paced and gated by demonstrated proof artifacts, never by an elapsed clock, hours, or arbitrary weeks. If this progression and a hard prerequisite disagree, the hard prerequisite wins. A unit is marked complete only when its proof exists, following the hard dependency order.

**Route classification.** Every live unit has exactly one label. **Core** means required for the core staging portfolio (Milestone 9) and gates G1–G8. **Conditional** means deferred unless the named trigger is true. **Later Deepening** means post-staging production deepening, activated only when a real-user pilot exists (Milestone 10 / G9). Units P16.1–P16.3 and P17.1–P17.2 are Core; units P16.4–P16.5 and P17.3–P17.4 are Later Deepening.

| Phase | Core units | Conditional units | Later Deepening |
|---|---|---|---|
| 2 | P2.1–P2.5 | — | — |
| 3 | P3.1, P3.2, P3.4–P3.7 | — | — |
| 4 | P4.1–P4.6, P4.7a, P4.7b, P4.8a, P4.8b, P4.9 | — | — |
| 5 | P5.1–P5.7 | — | — |
| 6 | P6.1–P6.6 | — | — |
| 7 | P7.1–P7.4, P7.5a–P7.5c | P7.7, P7.8 | P7.6 |
| 8 | P8.1–P8.7 | — | — |
| 9 | P9.1–P9.7 | — | — |
| 10 | P10.1–P10.3, P10.4a–P10.4c, P10.5–P10.8 | — | — |
| 11 | P11.1–P11.6 | — | — |
| 12 | P12.1–P12.6 | P12.7 | — |
| 13 | P13.1–P13.5 | P13.6, P13.7 | — |
| 14 | P14.1–P14.7 | — | — |
| 15 | P15.1–P15.6 | — | — |
| 16 | P16.1–P16.3 | — | P16.4–P16.5 |
| 17 | P17.1–P17.2 | — | P17.3–P17.4 |

**Conditional triggers (specific, not "when needed").**

- **P7.7** — the capstone has a browser UI, or a target posting names Next.js/React and the learner needs the data-flow defense. Otherwise the opran Next.js evidence stays a reading context, not a completed unit.
- **P7.8** — a target posting names NestJS/Twenty, or an Eagles verification task needs the host-versus-app boundary. Otherwise Twenty stays a code-reading context.
- **P12.7** — the chosen workflow needs cross-session memory beyond stored business facts (for example, a returning user's unresolved case). A stateless request/response workflow does not trigger it.
- **P13.6** — a measured single-agent/workflow baseline fails the P14 evaluation threshold, and a multi-agent design is the candidate fix. Interest in multi-agent systems is not a trigger.
- **P13.7** — the chosen workflow genuinely needs voice or browser interaction. A text API is the default.

**Later Deepening triggers (concrete; not "when needed").**

- **P16.4** — a real workflow owner runs the system with real users and records observed feedback and a prioritized improvement log. Without a pilot, the unit is not started and no pilot claim is made.
- **P16.5** — a measured before/after outcome exists from a real pilot, with data provenance and honest limitations. Without a real pilot, the outcome report is not produced and no business-outcome claim is made.
- **P17.3** — P16.4 and P16.5 are complete (real pilot evidence available), so the consolidated evidence pack can mark simulated evidence explicitly and verify which agent-written parts were independently checked.
- **P17.4** — P17.3 is complete; the defense then covers the pilot evidence, not only the staging slice.

**Milestone & capability progression track.** Progression is self-paced: each milestone represents a coherent engineering capability validated by tangible proof artifacts. Units within a milestone are executed in topological dependency order. For project implementations, specialized distributed components (such as transactional outbox/reconciliation in P8.6–P8.7) or multi-system design drills (P10.8) are scoped directly to the project architecture or practiced as standalone engineering drills without blocking initial end-to-end model integration. Cloud deployment is anchored to a single concrete cloud target for staging. A unit is marked complete when its proof artifact exists and meets the exit criteria; a gate is claimed only when all its constituent proofs are defended.

| Milestone | Units in execution order | Capability milestone & deliverables | Gate closed |
|---|---|---|---|
| **M1 — Python Service Runtime, Workbench & Contracts** | P2.1, P2.2, P2.3, P2.4, P2.5, P3.1, P3.2, P3.4, P3.5, P3.6, P3.7, P4.1, P4.2, P4.3, P4.4 | Five-line Problem Card (`docs/problem-card.md`) with labelled hypotheses, short evidence-based baseline in `../../workspace/evidence.md`, reproducible Python repo that starts from the README and a lockfile, stub-provider call with a seeded provider failure and a red→green regression test, trust-boundary validation fixtures, runtime failure debugging harness, async contract with bounded concurrency, service adapter, test seams, reproducible Python service, event loop/cancellation evidence, HTTP contract & auth boundary | **G1** |
| **M2 — Service Architecture, Data Correctness & Early Evaluation** | P4.5, P4.6, P4.7a, P5.1, P7.1, P10.1, P4.7b, P4.8a, P5.2, P4.8b, P4.9, P5.3, P5.4, P5.5, P5.6, P5.7, P6.1, P6.2, P6.3, P6.4, P6.5, P6.6, P7.2, P7.3, P7.4, P7.5a, P7.5b, P7.5c, P14.1 | Schema migrations, fault harness, provider contract sheet, credential lifecycle, transactional invariants, race/lock tests, architecture diagrams, ADR + fitness functions, customer discovery workflow map (P10.1), and the **first evaluation test case set (P14.1)** constructed from the workflow and testing discipline *before* any model integration. Once G1 has closed and P14.1's case set is complete, run the **early model-exposure checkpoint** (one live-provider call, one typed provider failure, one latency measurement) before M3; it is recorded as exploratory and changes no unit proof | **G2** |
| **M3 — First Model Integration, Complexity Floor & Reliability Foundations** | P8.1, P10.2, P11.1, P11.2, P11.3, P8.2, P8.3, P8.4, P8.5, P8.6, P8.7 | Partial failure handling, deterministic vs AI option comparison (P10.2), model guarantees & failure modes (P11.1), first typed Python model call (P11.2) evaluated against the P14.1 case set, schema-validated structured output (P11.3), idempotency keys (P8.2), retry budgets (P8.3), webhook receiver/sender (P8.4), durable worker (P8.5), and transactional outbox/reconciliation (P8.6–P8.7) | **G3** |
| **M4 — Production Reliability, Operations & Model Levers** | P9.1, P9.2, P9.3, P9.4, P10.3, P9.5, P9.6, P9.7, P11.4, P11.5 | Single-target cloud staging deployment, containerization, CI/CD with rollback rehearsal, correlation tracing, SLIs/SLOs from fault runs, measurement plan, postmortem with stakeholder update, controlled load test diagnosis, executed fault matrix & operational runbook, plus model cost/latency budgets & prompt caching (P11.4), and prompt/context versioning (P11.5) | **G4** |
| **M5 — FDE System Design & Architecture Decisions** | P10.4a, P10.5, P10.6, P10.4b, P10.4c, P10.8, P10.7, P11.6 | Three-part system design brief (requirements & capacity worksheet, components & interfaces & ADR, failure/security risk matrix & validation plan), three design exercises (rate limiter, notification, payments), formal go/adjust/stop review, and model-informed architectural placement with failure containment (P11.6) | **G5** |
| **M6 — Context Engineering, Retrieval & Grounded RAG** | P12.1, P12.2, P12.3, P12.4, P12.5, P12.6 | Context budgets, document ingestion lifecycle, hybrid search & rerank, citation grounding & abstention, independent retrieval evaluation | **G6** |
| **M7 — AI Evaluation & Observability Before Agents** | P14.2, P14.3, P14.4, P14.5, P14.6, P14.7 | Complete the Docs Q&A evaluation mini-project: 50-item golden set (at least five unanswerable cases), 20 human-labelled comparisons for judge calibration, separate retrieval/generation results, two comparable trace/eval runs, and a CI regression that fails when reranking is disabled; P14.1's first case set already exists from M2 | **G7** |
| **M8 — Bounded Agents, Harness, MCP & Security** | P13.1, P13.2, P13.3, P13.4, P13.5, P13.6, P13.7, P15.1, P15.2, P15.3, P15.4, P15.5, P15.6 | Research Agent with Sandbox; tool schemas and permissions; explicit stop reasons, step/time/token-cost budgets, traces and citations; MCP trust/authorization boundary; threat model, prompt-injection tests, least-privilege matrix, data-lifecycle review, and security runbook | **G8** |
| **M9 — Production AI Delivery & Staging Capstone** | P16.1, P16.2, P16.3, P17.1, P17.2 | Ship the research-agent slice to a repeatable staging URL behind input/output checks, a tool allowlist, request budget, and tested fallback; dashboard token/cost/latency over at least 50 runs; 20 prompt-injection/red-team cases with the top three findings fixed and re-tested; CI runs both evals and red-team cases; plus the deterministic baseline, migrations, full tests, rollout/rollback plan, runbook, and agent review records | **Staging Portfolio Ready** |
| **M10 — Real Pilot, Measured Outcome & Defense** | P16.4, P16.5, P17.3, P17.4 | Observed real pilot feedback, measured business outcome before/after report, consolidated evidence pack (ADRs, threat model, eval report, runbook, verified agent contributions), scenario defense cards and full technical defense | **G9** |

**Capstone evolution flow.** The capstone system evolves organically across milestones rather than starting at the end. Each artifact belongs to the stage that can produce it honestly:
1. **Five-line Problem Card (P2.1):** the seed — intended user, workflow, current pain or hypothesis, initial success signal, most important constraint; unknowns are hypotheses, not facts.
2. **Evidence-informed discovery and selection (P10.1–P10.3):** current-state workflow map, stakeholder questions, the non-AI comparison (P10.2), and the baseline measurement plan with an owner and collection method (P10.3). P10.1 replaces the Problem Card's provisional workflow observation; it does not inherit the card as a finished brief.
3. **Early evaluation case set (P14.1):** representative, edge, and adversarial cases from the workflow and testing discipline, completed before the first model call in M3; model-specific cases are added after P11.2–P11.3.
4. **Formal system design (P10.4a–P10.4c) and design review (P10.7):** requirements and capacity, interfaces and components, the architecture decision, failure/security risk matrix, validation plan, and the go/adjust/stop decision.
5. **AI-dependency containment and rollout design (P16.1, P16.3):** degradation, fallback to deterministic rules, human escalation, and stop conditions — designed before the capstone build, not after it.
6. **Capstone selection and vertical slices (P17.1–P17.2):** confirm data/users, a measurable baseline, bounded risk, and a reason AI is appropriate; then deliver thin vertical slices with tests, contracts, migrations, failure paths, and an agent review record per slice.
7. **Real pilot, measured outcome, evidence pack, and defense (P16.4–P16.5, P17.3–P17.4):** observed pilot feedback, before/after outcome with data provenance, the consolidated pack, and the technical defense. These stay conditional on a real workflow owner and real users.

**Early model-exposure checkpoint (between M1 and M3; not a unit).** Once G1 has closed, the P2.4 adapter plus the P4.1–P4.4 HTTP foundations are demonstrated, and P14.1's first case set is complete, run one deliberate live-provider checkpoint before the formal model sequence in M3. It has three parts: (1) one real model call through the P2.4 adapter, using a provider contract opened at teach time (endpoint, auth, request and response fields, documented error codes) and a stated spend cap; (2) one controlled failure — a documented provider error or an invalid credential — handled as a typed failure, not a crash; (3) one latency measurement over a stated number of calls (n, median, p95), recorded with the date and model identifier. This is exploratory exposure, explicitly **not** P11.2: it does not satisfy P11.1–P11.4, does not change any unit's proof, priority, or dependency, does not create an evaluation claim, and is not production evidence. If credentials or a verified contract are unavailable, run the labelled alternative: the P2.4 adapter against the P2.1 stub with a recorded provider-shaped response, logged as **"simulated — no model call"**. The stub-only rehearsal does not close the checkpoint; record it as deferred with the reason, and M3's P11.2 remains the first real model call.

**Core staging portfolio vs live pilot evidence.**
- **Core Staging Portfolio (Milestone 9):** Contains the complete G1–G8 gate records with their artifacts; P16.1–P16.3 (containment, deployment notes/smoke tests, rollout plan); P17.1 (capstone brief) and P17.2 (working vertical slice with tests, migrations, contract, failure paths, and agent review records); a deployed staging instance (single cloud target); a rollback rehearsal; a runbook a second person can follow; a portfolio README; and a job-search log. This bundle proves end-to-end engineering competence in a staging/simulated environment.
- **Production Pilot & Business Outcomes (Milestone 10 / G9):** Observed real pilot feedback (P16.4), measured before/after outcome report with real data provenance (P16.5), consolidated post-pilot pack (P17.3), and live outcome defense (P17.4). These require an actual enterprise workflow owner and real users. Where a live pilot is not present, staging evidence is labeled honestly as simulated, and G9 is not claimed.

**Topological dependency & integrity guarantees.**
- 116 unit lines, 111 live units, 5 tombstones; all 111 live units have a priority, source tags, and a dependency line.
- This refactor adds and removes no live unit IDs. The five tombstones are P3.3, P4.7, P4.8, P7.5t, and P10.4; every other ID is live and unchanged. Each live unit has exactly one route classification and one priority (41 must-have, 67 important, 3 useful).
- 0 hard dependencies point forward in file order; the topological sort succeeds with 0 cycles. Phase 14 precedes Phase 13 in the actual file order; the progress ledger remains numerically sorted only for stable IDs.
- The early model-exposure checkpoint creates no unit, no dependency edge, and no proof claim; P11.2 remains the first real model call in the formal sequence.
- **Early evaluation discipline is preserved:** P14.1's first test case set is completed at the end of M2 from the P10.1 workflow map and P7.2 testing discipline, *before* the first live model call — the exploratory checkpoint above runs only after it, and formal model integration begins in M3 (P11.2).
- **Milestone dependency order holds:** P10.2 executes in M3 (depends on P10.1, P7.5b, P8.1), cleanly preceding P10.4a in M5 (which depends on P10.2). AI milestones then execute RAG (M6) → evaluation (M7) → agents/security (M8) → staging delivery (M9) → real pilot and outcome evidence (M10).
- P11.2 strictly depends on P11.1, P2.2, and P2.4; P11.1 depends on P10.2 and P4.6. Under these hard dependencies, model calls are placed only after contract validation, testing seams, and architecture complexity floors are established.
