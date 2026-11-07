---
purpose: Defines the canonical pedagogical principles for every learning interaction.
read_when: When designing, delivering, reviewing, or improving a lesson.
depends_on:
  - ../governance/source-policy.md
  - ../governance/evidence-policy.md
  - ../governance/language-and-style.md
  - lesson-protocol.md
---

# Canonical pedagogical principles

These principles operationalise an engaging, evidence-aware learning experience. They
are instructional design rules, not a claim that one branded teaching method is
universally superior. Head First is an inspiration for interaction and representation,
not a source of empirical validation or reusable content.

| ID | Rule |
|---|---|
| P01 | Start with a meaningful question, contradiction, context, or challenge. Give a definition first only when the learner asks or a reference is the clear need. |
| P02 | Introduce a concept because an observed problem or knowledge gap makes it useful. State the problem, insufficiency, new idea, and remaining limits. |
| P03 | Invite a useful prediction before revealing an outcome when prediction will expose reasoning or prepare discovery. Do not turn every turn into a quiz. |
| P04 | Use a short adaptive conversation: ask one focused question, interpret the response, diagnose the gap, then choose the next explanation. Give a direct answer when it is more helpful or requested. |
| P05 | Disclose progressively: intuition, concrete example, concept, mechanism, technical precision, then boundaries and trade-offs. |
| P06 | Use coherent realistic scenarios. Label synthetic scenarios and never present invented events as verified incidents. |
| P07 | Use a visual only when it reduces conceptual complexity. Give each visual one instructional purpose and explain it. |
| P08 | Give important ideas more than one useful representation: prose, analogy, scenario, visual, code or mathematics, and application as appropriate. |
| P09 | Revisit important ideas in changed contexts or representations. Repetition must add discrimination, connection, or retrieval value. |
| P10 | Treat wrong answers as evidence about a mental model. Use contrast, counterexample, or a smaller hint without shame. |
| P11 | Scaffold from reconsideration, to hint, observation, clarification, partial example, small demonstration, and direct explanation. Reduce support as capability grows. |
| P12 | Use the existing retrieval records and future-session state for immediate and delayed retrieval. Do not create a competing review schedule. |
| P13 | Test transfer in an unfamiliar scenario with changed constraints, inputs, risks, or goals. Reading is not mastery evidence. |
| P14 | Use warmth, stories, and light humour only when they improve attention or meaning. Never trade away precision, accessibility, or depth. |

## Evidence boundary

Tag claims as source-backed fact, mentor synthesis, hypothesis, or learner evidence.
Register and verify research sources through the existing resource procedure before
using an empirical claim. A pedagogical preference may guide a lesson without being
described as proven. Content quality and pedagogical quality remain separate gates.

## Research-to-principle traceability

The table below uses only sources currently registered in
[workspace/resources.md](../workspace/resources.md). “Research-informed design
choice” means the source informs the design but does not establish that this
repository's implementation is superior. “Original system design decision” means no
qualifying pedagogical source is currently registered for the specific rule.

| Principle(s) | Supporting source IDs | Evidence type | Scope of support | Limitation |
|---|---|---|---|---|
| P01–P02 | S70 | Research-informed design choice | Case framing, issue identification, prior-knowledge activation, and learner-set goals in PBL method design | S70 is a university method guide with mixed comparative findings; it does not validate this AI-tutor sequence or prove superior outcomes. |
| P04 | S70, S71 | Research-informed design choice | Facilitator variation and the fact that PBL is a family of methods rather than one fixed procedure | S71 is abstract-only; neither source supports a specific adaptive algorithm or interaction policy. |
| P03, P05–P14 | — | Original system design decision | Repository-specific choices for prediction, disclosure, representations, feedback, retrieval, transfer, scenarios, and tone | No qualifying source for these exact rules is currently registered; do not present them as empirically established effects. |

## Operating constraints

- Preserve one objective, at most two new concepts, the existing journey owner, and
  exactly one practice task where [P§3](lesson-protocol.md) requires it.
- Adapt the route from the learner's response; do not mechanically apply every
  principle in every lesson.
- Preserve the evidence rule: a guided answer or generated artifact is not capability
  evidence until the learner demonstrates the skill.
