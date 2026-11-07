---
purpose: Defines one teaching procedure or workspace format.
read_when: When the procedure named in the routing table is required.
depends_on:
  - ../governance/source-policy.md
  - ../governance/evidence-policy.md
---

# P§3. Problem-based lesson layers and parts

Use the adaptive blueprint and principles in
[pedagogical-principles.md](pedagogical-principles.md). This remains the canonical
four-part delivery procedure. It is an individual, guided adaptation of problem-based
learning, not a claim that one method is universally superior.

## Preparation

1. Read the active unit, prerequisites, concept owners, source tags, and later
   retrieval entry.
2. Choose one verified case or a clearly labelled synthetic scenario.
3. Separate facts, assumptions, unknowns, constraints, and the eventual decision.
4. Prepare a causal chain: symptom → mechanism → consequence → required property →
   boundary. Prepare only the curriculum links that help this unit.
5. Select relevant failure cases and one transfer change. Do not reveal the complete
   answer before the learner has a useful chance to reason.

## Four-part delivery

| Part | Required behavior | Ends with |
|---|---|---|
| 1 — Curiosity and framing | Open with a concise problem, establish relevance, invite one prediction or framing response, and wait when interaction is needed. Diagnose assumptions without shaming. | One focused prompt |
| 2 — Discovery and formation | Select the smallest gaps from the response. Teach at most two new concepts, intuitively first, then concretely and technically. Use a purposeful visual or analogy when helpful. | One short retrieval question |
| 3 — Exploration and boundaries | Reinforce with a new representation, inspect the normal path and relevant misconceptions, failures, limitations, and trade-offs. Name prerequisite, coupled, owning, and later-transfer links only when useful. | One short retrieval question |
| 4 — Return and transfer | Resolve the original problem, explain why the solution works, state limitations and production evidence, then give exactly one meaningful changed-scenario practice task. | Exactly one practice task |

The parts form one conversation, not four unrelated essays. Wait after Part 1 when
the learner's response determines the scaffolding or concept selection. Keep one
objective and no more than two new primary concepts. If more are needed, sequence
them into later units rather than silently expanding this lesson. Keep the scenario
under 120 words. Cite the selected source and section for source-backed claims;
preserve synthetic labels.

## Interaction pauses and citation

- Part 1 must wait when framing or prediction determines the next teaching move.
- Parts 2 and 3 may pause after their retrieval question when the answer will change
  the next explanation, representation, or support level. Do not continue a long
  monologue after a meaningful question that requires learner input.
- A direct-answer request is an explicit exception to discovery pauses. Answer first,
  then offer one retrieval or application check when useful.
- Use this compact source label without inventing fields:
  `Source-backed fact — [S-ID], <registered title>, <exact chapter/section>,`
  `<canonical URL>, accessed <YYYY-MM-DD>.`
  Label mentor synthesis, hypothesis, and synthetic examples separately. The source
  catalogue remains authoritative for the actual identity and status of `<S-ID>`.

## Adaptive controls

- Use [scaffolding-and-feedback.md](scaffolding-and-feedback.md) to choose support.
- Use [visual-explanations.md](visual-explanations.md) to choose a representation.
- Use [retrieval-and-transfer.md](retrieval-and-transfer.md) with the existing
  [retrieval protocol](retrieval-protocol.md), not a competing schedule.
- Preserve journey IDs, hard prerequisites, evidence gates, and source ownership.
- Direct explanation is always allowed when requested or when further discovery is no
  longer useful.

## Incident-grounded variant

Keep the four parts. Part 1 carries observed incident facts and initial hypothesis;
Part 2 forms a testable mechanism; Part 3 designs or inspects the harness and limits;
Part 4 carries fix, regression, and transfer. A lab is not the incident. Label what it
can and cannot reproduce. Mode A may write the existing HTML lesson format; Modes B
and C use Markdown.
