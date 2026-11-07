---
purpose: Contains one part of the FDE learning journey.
read_when: When the FDE journey or the named phase is active.
depends_on:
  - ../../workspace/mission.md
  - ../../workspace/resources.md
---

# FDE Journey Map — Deep Engineering Roadmap



**Purpose:** Build durable engineering capability for taking a real business problem from discovery to a reliable, evaluated, secure, deployed AI-enabled system. This is a long-form learning journey.

**Mission alignment:** FDE = problem discovery → choose the right solution (including non-AI) → build → evaluate → secure → deploy → integrate into work → measure impact → hand over. The target is demonstrable engineering judgment, not completion of a syllabus.

Phases 0-1 were merged into Phase 2; the old-to-new mapping is in §8.

**Loading:** follow [context loading](../../teaching/context-loading.md). Read this map by section; the phase headings are the boundaries.

---

## 1. Rules for this journey

1. **Follow dependencies, not enthusiasm.** Each lesson lists its prerequisite lesson IDs. A lesson is ready only when its prerequisite's exit evidence exists.
2. **Teach one lesson unit at a time.** Progression is competency-based and self-paced: a unit is complete when its proof artifact meets the exit criteria, not when a clock expires. Standard units cover one focused capability; implementation units span larger multi-part builds.
3. **Teaching mechanics live in the routed teaching procedures.** The lesson loop,
   evidence and synthesis separation, retrieval, records, and honest capability
   claims follow [lesson protocol](../../teaching/lesson-protocol.md),
   [retrieval and transfer](../../teaching/retrieval-and-transfer.md),
   [workspace formats](../../teaching/workspace-formats.md), and
   [evidence policy](../../governance/evidence-policy.md).
4. **No progress by attendance.** Mark a lesson complete only when its proof artifact or practical performance meets the exit criteria.
5. **Respect established experience.** The user already has C++, OOP, and DSA experience. Do not teach beginner programming, object-oriented programming, or generic algorithm lessons. Use diagnostics to identify only the language, runtime, API, data, or AI-engineering gaps needed for the capstone.
6. **One evolving capstone.** Build a small, deterministic business workflow first; add persistence and integrations; introduce AI only when the use case justifies it; then evaluate, secure, deploy, pilot, and document it. Keep scope narrow.
7. **Source discipline.** `../../workspace/resources.md` remains the canonical project source register. Existing `S#` tags refer to it. The `F#` references below are official starting points checked on 2026-10-09; re-open the relevant page and record the exact section/version before teaching. Current API/model/security behavior must be verified at lesson time. A chapter tagged `[TOC]` was identified from a book's table of contents only and has not been read; keep the tag until the exact passage is read in an available tool and recorded in the `../../workspace/resources.md` reading-status table. A read that covered only the supporting sections is tagged `(read: <sections>)`; a chapter read in full is tagged `(read)`.
8. **This is a dependency graph represented as a mostly linear path.** Some concepts can be revisited later. Do not force advanced internals when the mission does not need them.
9. **Stay on the FDE/AI-engineer track.** Out of scope: training or building foundation models, ML research, and math beyond the applied evaluation protocol in P14.3 (see `../../workspace/mission.md`). Teach models and providers as engineering constraints — guarantees, cost, latency, failure modes — never as model internals.
10. **Human-in-the-loop engineering.** The learner directs coding agents and stays accountable for the result; an agent's output is an input to review, never proof by itself. Before delegating, write the problem, requirements, constraints, acceptance criteria, and architecture decisions. After the agent changes the code, review the diff, its dependencies and side effects, and the tests it wrote; design at least one verification independently of the agent's own tests; observe the real behavior across API, application logic, database, and user-facing workflow; diagnose failures from logs, traces, measurements, and failure injection; then record accept, reject, or redirect with evidence (the agent review record in section 3). Passing tests are necessary, not sufficient (S40, S41). A lab proves a lab skill: label simulated data and pilots honestly, and phrase
missing experience using [evidence policy](../../governance/evidence-policy.md). Projects in languages the capstone does not need (for example Rust) remain code-review contexts, not additional language tracks.

11. **Hand-writing versus review.** Hand-write first when the skill is the learning target: a new concept the learner has not yet demonstrated unaided, correctness-critical work (transactions, concurrency, authorization, idempotency), and debugging. Delegate repeated mechanics and work in skills the learner has already demonstrated unaided; the delegation brief, diff review, independent verification, and accept/reject/redirect decision stay exactly as in rule 10. When an agent is used to learn, use it to build comprehension as well as output — ask it for explanations and conceptual questions, not only for code (S44). Delegating never transfers accountability: the learner still explains, modifies, or fixes the result without the agent, and owns it in the evidence pack (P17.3–P17.4) (S43).

## 2. Roadmap at a glance

Use the levels below to scan the journey quickly. The detailed phase sections that follow remain the source of truth for each unit's priority, hard dependencies, coupled units, sources, and exit evidence. This index adds no lesson IDs or prerequisites and does not mark progress as complete. Use `../../workspace/evidence.md` for demonstrated capability and `../../workspace/resources.md` for source status. Retired IDs are retained as tombstones for traceability, not as active lessons.

```text
LEVEL 0 — Reproducible foundation [Phases 2–3 | G1]
├─ P2: runnable service, seeded provider fault, data contracts, async contract, adapters, test seams
└─ P3: types and runtime, process lifecycle, non-blocking I/O, cancellation, cleanup, logs/config/secrets

LEVEL 1 — API contracts and relational data [Phases 4–5 | contributes to G2]
├─ P4: HTTP, API/auth contracts, schema evolution, fault-injection harness, provider contract and credentials
└─ P5: relational model, SQL, constraints, indexes, migrations, application data access, backup/restore

LEVEL 2 — Correct state, tests, and architecture [Phases 6–7 | G2]
├─ P6: transactions, isolation, concurrency, invariants, ordering, duplicate events
└─ P7: test strategy, honest test doubles, refactoring/review, architecture trade-offs, ADRs and fitness checks

LEVEL 3 — Distributed integration and operations [Phases 8–9 | G3–G4]
├─ P8: ambiguous outcomes, idempotency, bounded retries, webhooks, queues, outbox/saga, reconciliation
└─ P9: containers/CI/CD, logs-metrics-traces, SLI/SLOs, incidents, capacity diagnosis, degradation and runbooks

LEVEL 4 — Discover and design the right solution [Phase 10 | G5]
└─ Workflow discovery, deterministic-vs-AI choice, baseline/adoption plan, capacity and system design, failure review, go/adjust/stop

LEVEL 5 — Build an LLM application with context [Phases 11–12 | G6]
├─ P11: model/API contract, structured output, provider limits/cost, versioning, where an LLM belongs
└─ P12: context budgets, ingestion, hybrid retrieval/reranking, RAG grounding/citations/abstention, retrieval metrics, memory

LEVEL 6 — Evaluate before adding agent autonomy [Phase 14 | G7]
└─ Golden set, graders and human comparison, uncertainty, CI regression gate, request tracing, production-side evaluation

LEVEL 7 — Bounded agents and AI security [Phases 13 → 15 | G8]
├─ P13: workflows, safe tools, bounded agent loop, budgets/checkpoints, MCP; optional multi-agent/voice/browser only when justified
└─ P15: threat model, prompt injection, least privilege/approvals, sensitive data, secure boundaries, audit and governance

LEVEL 8 — Ship, adopt, measure, and hand over [Phases 16–17 | G9]
├─ P16: containment/fallback, deployment, rollout/rollback, user feedback, measured outcomes and ownership
└─ P17: narrow workflow selection, vertical slices, evidence pack, decision defense and limitations
```

**How to read the levels.** They group related phases for orientation; they do not replace the actual dependency graph. Follow each unit's `Depends on` line and require its exit evidence before advancing. Gates G1–G9 are the progression contract; the gate table in §4 states the required proof. G9 needs a real workflow owner, real users, and measured outcome evidence; staging work alone does not close it.

**AI execution order (S48).** The path is Phase 11 → Phase 12 → Phase 14 → Phase 13 → Phase 15. Phase IDs are stable identifiers, not a promise of numeric execution order. This uses the explicitly ordered 12-week sample plan in the designated AI Roadmap 2026 (S48), which puts Evaluation before Agents; its descriptive layer pages list Layer 3 before Layer 4, so the selected execution order and source caveat are recorded in `../../workspace/resources.md`. The first P14.1 case set starts in M2 before the first live model call; the full evaluation slice follows RAG and precedes agents.

**Implementation track.** Python is the only default implementation language for the capstone and AI labs (Phases 2–17). Backend services, API integrations, data access, evaluation, and model calls use Python; setup and verification are defined in `../../teaching/session-protocol.md` P§6. Read another language or framework only when an existing-system task (currently the conditional P7.7/P7.8 work) or an explicitly named target role requires it. That work is bounded code reading and verification, not a second implementation track. Do not add Node.js, TypeScript, NestJS, or Next.js as default study tracks.

**Using the supplied handbook (S69).** The handbook's contents provide a broad, practical reading path across the phases; the chapter pointers below are navigation aids and remain `[TOC]` until the exact passage is opened and recorded in `../../workspace/resources.md`. Use the book for topic coverage, examples, and interview practice, not as the authority for current API/model behavior, pricing, or security standards. Its own opening note says version numbers, model names, and prices are illustrative; current claims still require dated primary documentation. Node.js, TypeScript, and NestJS examples are out of the default route unless a named existing-system task or target role requires them.

**Provider dependency thread.** Provider-shaped failure is a recurring engineering context from P2.1 onward, not only a Phase 11 topic. Section 3 defines the bridge exercises and the unit that owns each mechanism. The optional live-provider checkpoint in §10 is the only live-provider step before Phase 11; it is exploratory, does not satisfy P11.2, and does not change any unit's proof or dependency. P11.2 remains the first real model call in the formal sequence.

---

## 3. Lesson design and completion criteria

Every lesson follows this record shape:

- **ID and objective:** one capability that can be demonstrated.
- **Priority:** must-have, important, or useful — a planning weight, not permission to skip prerequisites (see Priority below).
- **Depends on (hard prerequisite):** required lesson IDs that must appear **earlier in this file's order**, not just earlier topics. The forward-dependency and cycle checks are run with an ad-hoc script at edit time; no inventory script is currently committed (the previous script was removed in `ee744ff`).
- **Coupled with:** a non-blocking relationship built in one phase and verified (or completed) in a later one. May point forward; it must reference an existing unit ID but the cycle and file-order checks ignore it. Used so that an earlier unit does not silently re-teach a later phase's content.
- **Source:** specific project source IDs and/or official documentation to open.
- **Lesson:** scenario → concept → mechanism → failure modes → production implications.
- **Practice:** one tangible task, preferably on the evolving capstone or a deliberately small lab.
- **Exit evidence:** one primary proof artifact (checkable sub-items inside it are allowed).
- **Retrieval:** defined once in the Retrieval table below — a named later unit whose scenario re-tests this one. No per-unit Retrieval field.
- **Unit type:** standard lesson units (focused capability and proof) vs **implementation unit (multi-session)** (larger architectural build, multi-part design, or lab).

### Depth scale

| Depth | What it means | Example evidence |
|---|---|---|
| 0 — Recognize | Identify a concept when described | Correct classification with explanation |
| 1 — Explain | Describe why it exists and its limits | Clear explanation plus one failure mode |
| 2 — Use | Apply it in a guided, bounded task | Working implementation with basic tests |
| 3 — Engineer | Implement, debug, test, and handle failure cases | Tests, error paths, reproducible diagnosis |
| 4 — Design | Compare alternatives, consistency, security, operations, and cost | ADR plus failure analysis |
| 5 — Deep internals | Explain implementation details and edge cases | Only where required by project scope |

**Default standard:** Depth 2–3 for routine implementation lessons; Depth 3–4 for data correctness, integrations, evaluation, security, and production decisions. Depth 5 is selective, not a universal requirement.

### Priority

Each unit carries one of three priorities, keeping the priority vocabulary of the pre-rewrite journey map so the readiness check in [context loading](../../teaching/context-loading.md) has the metadata it names:

- **must-have** — the unit sits on the capstone's critical path: it is a dependency hub (seven or more units depend on it), it closes a gap listed in `../../workspace/evidence.md`, it produces the G1 Problem Card/short baseline, the provider contract sheet, the regression gate, or the threat model, or it is a Phase 17 capstone unit (selection, build, evidence pack, or defense).
- **important** — expected on the standard path: later units build on it or it grounds a phase gate.
- **useful** — valuable depth: compress or defer when diagnostics, the capstone, or a supporting branch show the capability is already present or not yet needed.

The old **awareness** tier has no units: every unit here carries a proof artifact, so deferral happens through the supporting branches or the project's needs, not by tagging a unit away.

### Agent review record

Used wherever a proof names an *agent review record* (rule 10). It is a short Markdown note kept with the change, with five fields:

1. **Delegation brief:** the problem, requirements, constraints, acceptance criteria, and the architecture decisions the agent must respect, written before delegating.
2. **Diff review:** the files changed, the dependencies and side effects found, and the most important changes explained in the learner's own words.
3. **Independent verification:** at least one test, query, or runtime check designed from the requirements rather than copied from the agent's own tests, plus the assumptions that remain untested.
4. **Observed evidence:** logs, traces, measurements, or failure-injection results that were actually seen.
5. **Decision:** accept, reject, or redirect, with the evidence that justifies it.

A passing generated test suite is an input to this record, never the verdict. The record is practice evidence only; it is not production experience (rule 10) and does not enter `../../workspace/evidence.md` as an achievement until the artifact exists.

### AI-provider dependency thread (Phases 2–9)

A model provider is an external service with a contract, a failure surface, a latency profile, and a price. The thread below makes that context recur from the first service onward without moving any advanced mechanism out of its owning unit. Each row is a **bridge exercise inside the primary unit named**, run against the P2.1 stub provider (extended by P4.7b) or a recorded fixture; the other units in a row are ownership boundaries, not additional bridges. No row is a new unit, a new gate, or evidence that a later unit is complete.

| Phase | Bridge exercise: fault scenario | Owning unit and capability | Boundary |
|---|---|---|---|
| 2 | The stub provider returns a provider-shaped 5xx error body; later, a malformed or unexpected payload | P2.1 fails visibly and proves it with a regression test; P2.2 owns trust-boundary validation and runtime rejection | P2.1 does not validate schemas or classify retries; P2.2 does not decide retry policy |
| 3 | A slow provider call holds execution resources past the caller's deadline | P3.6 owns timeout, cancellation, and bounded cleanup, against the async contract defined in P2.3 | A timeout is a failure, not a fix; retries stay out |
| 4 | A provider HTTP outcome violates the expected contract | P4.5 owns retryable-versus-permanent classification; P4.8a owns the provider contract sheet | Budgets, backoff curves, and jitter stay in P8.3 |
| 5 | Validated provider output must become persisted business state | P5.3 and P5.6 own constraints, integrity, and parameterized access | No model semantics enter the schema |
| 6 | A repeated or overlapping request risks a duplicate business effect | P6.5 owns duplicate and stale event transitions; P8.2 owns operation keys and retention | P6 does not build a queue or a delivery guarantee |
| 7 | A green suite passes while a meaningful behavioral defect survives | P7.2–P7.3 own independent regression tests and honest test doubles | A mock passing is not evidence about the provider |
| 8 | Rate limiting, transient failure, repeated delivery, or partial completion | P8.3 owns bounded retries and backoff; P8.4 webhook contracts; P8.5 durable workers | P8 does not re-teach the HTTP categories from P4.5 |
| 9 | Provider latency, request volume, or cost rises while the system degrades | P9.3 tracing, P9.4 SLI, P9.6 capacity diagnosis | Cost stays an estimate until a real provider bill or measured usage exists |

**Ownership rules.**

1. The bridge changes how a unit is practised, not what it proves. The unit's own proof artifact and exit criteria stand.
2. A bridge never marks a later unit complete, and no later unit may depend on a bridge.
3. A later unit may re-use the bridge's fixture, but it must re-derive its own contract, measurement, or test from its own source.
4. The early model-exposure checkpoint (§10) is the only live-provider step before Phase 11; every other bridge is stub-based and labelled simulated.

---

### AI Roadmap 2026 project ladder (S48; execution order selected for this journey)

Use the roadmap to set the AI-topic sequence and project evidence, not to replace the FDE mission. The execution path is **Layer 1 Foundations → Layer 2 LLM Engineering → Layer 4 Evaluation → Layer 3 Agents → Layer 5 Production**. These are cumulative portfolio slices in one evolving repository or a small set of tightly connected repositories, not five disconnected capstones. The FDE-specific work remains mandatory: discovery, deciding whether AI is justified, security, adoption, business measurement, and handover.

| Roadmap layer and order | Journey mapping | Mini-project slice | Target proof |
|---|---|---|---|
| **L1 — Foundations** | Phases 2–10, followed by the formal provider bridge in P11.2 and model-operating levers in P11.4 | **LLM Proxy API** | One async `/chat` endpoint behind the stable adapter; request records with timestamp, outcome, and latency (provider token/cost fields where actually available); a SQL summary of request count and average latency; bounded retries from P8.3 and explicit budgets from P11.4. P2.1 remains stub-only; this project gets its first real model call at P11.2 and adds cost/latency controls when their prerequisites are met. |
| **L2 — LLM Engineering** | P11.1–P11.6 and P12.1–P12.7 | **Docs Q&A with citations** | A versioned documentation corpus, hybrid lexical/vector retrieval and reranking, grounded answers with citations, and abstention when the corpus does not support an answer. Separate retrieval failure from generation failure. The read-only `ask_docs` tool can be shaped here; its MCP wrapper is added in P13.5 after evaluation and must pass the same regression suite. |
| **L4 — Evaluation** | P14.1–P14.7; the initial P14.1 case set still starts in M2, before the first model call | **Evaluate the Docs Q&A system** | A 50-item versioned golden set with at least five unanswerable questions; at least 20 human labels compared with an LLM judge, with disagreements and calibration recorded; retrieval and answer quality measured separately; two comparable trace/evaluation runs; and a CI check that fails on a seeded regression such as disabling reranking. Use Langfuse or Phoenix when available; if neither can be used, save equivalent traces and scores as a reproducible artifact and record the deviation. Model-specific cases are added only after P11.2–P11.3. |
| **L3 — Agents** | P13.1–P13.7, after the evaluation layer | **Research Agent with a Sandbox** | A bounded multi-step research workflow that produces a report whose factual claims cite URLs the agent actually opened; a read-only research tool; model-written code isolated in a sandbox when computation is needed; step, wall-clock, and token/cost limits; per-step run records; and a low-cap test that stops with an explicit partial result rather than hanging or claiming success. Compare a simple workflow/single-agent baseline first; add planner-worker or multiple agents only when evaluation demonstrates that the extra latency, cost, and failure surface are justified. |
| **L5 — Production / LLMOps** | P15.1–P15.6, P16.1–P16.3, and the staging slice in P17.2 | **Ship the Research Agent** | A repeatable staging deployment behind input/output checks, a tool allowlist, a per-request budget, and safe failure/fallback behavior; a cost/latency dashboard over at least 50 runs; 20 prompt-injection/red-team cases, with the three highest-impact findings fixed and re-tested; and CI that runs the evaluation suite and red-team cases before release. P16.4–P16.5 and G9 remain conditional on a real workflow owner, real users, and measured outcomes. |

**Scope guardrails.** Keep the journey framework-agnostic: learn the agent loop and harness contract before choosing an SDK. MCP is an interoperability boundary, not a safety control. Fine-tuning, quantization, GPU serving internals, and model-training work remain out of scope under `../../workspace/mission.md` and §1 rule 9; the roadmap's broad production layer does not override that filter. A lab, staged deployment, or synthetic evaluation is never labelled a production outcome.
