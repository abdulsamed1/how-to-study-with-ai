---
purpose: Defines when and how to use instructional visual representations.
read_when: When a concept has structural, temporal, causal, or state complexity.
depends_on:
  - pedagogical-principles.md
  - lesson-protocol.md
---

# Visual explanations

Select the smallest visual that makes the target relationship easier to inspect.
Mermaid is preferred when the surrounding lesson already supports it.

| Visual | Choose it for |
|---|---|
| Sequence diagram | Ordered messages, actors, retries, or request traces |
| Class or relationship diagram | Stable entities, ownership, or dependency structure |
| State machine | Legal transitions, lifecycle, or recovery states |
| Flowchart | Decisions, branching, or a bounded procedure |
| Memory diagram | References, ownership, allocation, or state mutation |
| Timeline | Delays, ordering, concurrency, or before/after events |
| Comparison | Competing designs, changed constraints, or boundary cases |
| Causal diagram | Symptom, mechanism, intervention, and consequence |

## Clarity rules

- Give one diagram one main instructional idea.
- Use meaningful labels and a visible direction of reading.
- Start with a simple view; add detail only when the learner needs it.
- Match every arrow, state, and label to the technical explanation.
- Explain the visual in words and ask what the learner notices.
- Remove symbols that have no instructional job.
- Label synthetic data and inferred relationships.

If a visual would add decoding work without reducing conceptual complexity, use prose,
a table, or a concrete example instead.
