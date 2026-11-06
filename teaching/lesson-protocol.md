---
purpose: Defines one teaching procedure or workspace format.
read_when: When the procedure named in the routing table is required.
depends_on:
  - ../governance/source-policy.md
  - ../governance/evidence-policy.md
---

# P§3. Problem-based lesson layers and parts


## P§3. Problem-based lesson layers and parts

A lesson unit gives one tangible win tied to the mission. Use a guided, individual adaptation of problem-based learning (PBL): encounter the problem first, let the learner help define what must be learned, teach the minimum useful knowledge with support, then return to the problem. This is not a group tutorial; the AI acts as a facilitator and source guide. PBL is not one fixed teaching method (S71, abstract only), so use this procedure as the repository's chosen implementation, not as a universal definition.

### Preparation before Part 1

The agent prepares the lesson; it does not reveal the complete answer.

1. Read the current unit, its hard prerequisites, Coupled with links, concept-owner boundaries, source tags, and the later retrieval entries in the active journey.
2. Select one realistic problem that directly exercises the unit's target capability. Prefer a verified incident or source-backed case. If none is available, write a clearly labelled synthetic scenario; never present it as a real incident.
3. Separate the case's observed facts, assumptions, unknowns, constraints, and decision that must eventually be made.
4. Build two connected views:
   - **Causal problem chain:** symptom → mechanism → follow-on failure (including a new gap exposed by the first fix) → required design property → production boundary.
   - **Concept/curriculum links:** prerequisites, adjacent or coupled concepts, the unit that owns a deeper mechanism, and the later unit that will test transfer. Use exact journey IDs. Label any inferred conceptual connection as mentor synthesis, not as a formal dependency.
5. Select the failure and edge cases that could change the diagnosis, correctness, or design. Keep them tied to the central problem; do not prepare an encyclopedic list.

### Problem-to-learning sequence

1. **Problem encounter.** Present the real or labelled synthetic scenario in fewer than 120 words. Give enough context, observations, and constraints to make it understandable, but do not start with a definition, a topic outline, or the final fix.
2. **Learner framing.** Ask one focused question that elicits the learner's problem statement, known facts versus assumptions, first hypothesis, and the evidence they would inspect next. Wait for the learner. Treat an incorrect hypothesis as useful diagnostic information, not failure. If the learner is stuck, scaffold progressively: clarify one term, reveal one additional observation, offer a hint, or reduce the scenario. Do not replace the learner's reasoning with the answer.
3. **Learning issues and concept links.** Use the learner's response to identify the smallest knowledge gaps that matter. Show a compact connection map, using exact journey IDs:
   - **Hard prerequisite:** a required earlier unit; verify its exit evidence. Teach a missing prerequisite before the dependent mechanism.
   - **Coupled / adjacent concept:** a related non-blocking unit; explain the connection without pretending it is required first.
   - **Owning unit / boundary:** the journey unit that teaches the deeper mechanism; name it and defer that content until its place.
   - **Retrieval / transfer:** the later unit that will re-test the idea in a changed scenario; this is not a prerequisite.
   - **Conceptual bridge:** a relevant relationship inferred from the problem; label it as mentor synthesis, not as a journey dependency.
   Show only the links that help explain the current problem. Never invent unit IDs or change the journey graph inside a lesson.
4. **Targeted teaching.** Teach no more than two new concepts at once, selected from the learning issues. Explain what each concept does, why the problem needs it, and the mechanism that produces the observed behavior. Use a short state table, timeline, request trace, code path, or diagram where it makes the causal chain easier to inspect. Give a precise source and section for source-backed claims. Where useful, direct the learner to one primary-source section and a question to investigate before providing the synthesis.
5. **Connected failures and edge cases.** Walk through the normal path and the relevant failure/boundary cases. For each case, state the changed condition, what happens, why the result differs, and which concept or journey unit owns the deeper treatment. Include trade-offs or an alternative only when they affect the current decision. Do not pull an entire future lesson into the current one.
6. **Return, solve, and transfer.** Revisit the original problem. Connect the evidence to the mechanism, show or guide the fix, and explain what to test or monitor in production. Then give exactly one practice task that changes a constraint, timing, failure point, or business consequence so the learner must transfer the reasoning rather than repeat the example.

### Parts — one message each

| Part | Content | Ends with |
|---|---|---|
| 1 | Problem encounter + learner framing | One formative problem-framing prompt; wait for the learner |
| 2 | Learner-specific learning issues + targeted concepts and mechanism | One short retrieval question |
| 3 | Explicit concept links + relevant failure modes and edge cases | One short retrieval question |
| 4 | Return to the original problem + production bridge | Exactly one practice task |

A part is roughly 400–700 words when the topic needs that depth; the problem statement itself stays under 120 words. Do not pad a part to reach the range. The explanation should be clear enough for a B1/B2 reader without flattening the technical detail. Keep the lesson centred on one unit's objective.

### Incident-grounded variant (hands-on reliability units)

Keep the four parts and the eight-step cycle in ../AGENTS.md §8, but add learner framing before revealing the mechanism. Part 1 carries Incident + Evidence and the learner's first problem framing (verified case, observed symptom, unknowns, and initial hypothesis). Part 2 uses the learner's hypothesis to teach the minimum Mechanism and form a testable hypothesis. Part 3 examines the relevant failure cases and designs the Harness + Measure, including what the lab can and cannot reproduce. Part 4 carries Fix + Regression + Transfer and issues the single practice task, in which the learner runs the harness, records the baseline, changes one variable, and shows red → green. The agent must wait for the learner's Part 1 response before choosing how much explanation and scaffolding Part 2 needs. A part may cite the incident but must not present a simulation as the incident itself. When no verified incident fits, say so and use a clearly labelled synthetic scenario instead.

A part cites the selected source in Part 1 and repeats the best primary source at the end. Mode A: also write lessons/NNNN-slug.html: self-contained, linking the shared stylesheet in assets/ and the reference sheets, readable and printable. Reuse assets/ components before writing new ones. Open the file with xdg-open on Fedora. Modes B and C: Markdown in the reply. Reference sheets (reference/*.html) hold the compressed essence of a lesson: checklists, decision tables, sequence diagrams.

**Pedagogical grounding:** S70 documents a learner-centred PBL process in which learners examine a case, identify learning issues, investigate, report back, and reflect. S71 is an abstract-only primary citation for the warning that PBL methods vary; it does not establish that this particular individual-AI adaptation is empirically superior. These sources support teaching-method decisions only, not technical claims.
