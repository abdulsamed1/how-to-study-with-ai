---
purpose: Defines when and how to use instructional visual representations.
read_when: When a concept has structural, temporal, causal, or state complexity.
depends_on:
  - pedagogical-principles.md
  - lesson-protocol.md
---

# Visual explanations

## Mandatory format: Premium Mermaid only

When a diagram will make a concept easier to understand, use a polished Mermaid
diagram as the **only permitted diagram format**. This is a presentation standard,
not a separate paid Mermaid feature.

- Write diagrams as fenced Mermaid blocks (`\`\`mermaid`) so the learning surface can render them.
- Do not draw diagrams with HTML, CSS, SVG, ASCII art, Unicode boxes, or text-character layouts.
- If the current surface cannot render Mermaid, do not fall back to another diagram format. Explain the relationship with ordinary prose and a concrete example.
- Do not force a diagram into a lesson when it adds no clarity. In that case, teach with prose and a concrete example rather than an alternative diagram.

## Premium quality standard

- Choose the Mermaid diagram type that matches the relationship: messages and timing, decisions, states, dependencies, ownership, or cause and effect.
- Give the diagram one main instructional purpose and a clear reading direction.
- Use a meaningful title, descriptive labels, and explicit actors, boundaries, or states where they matter.
- Keep labels short but unambiguous; avoid unexplained abbreviations and overloaded nodes.
- Use layout, grouping, spacing, and restrained styling to make the structure immediately scannable. Never rely on color alone to communicate meaning.
- Keep the first view simple. Add branches, failure paths, or subgroups only when they are needed to explain the current lesson.
- Make every arrow and transition technically meaningful. The prose explanation must agree with the diagram.
- Put the Mermaid block close to the paragraph that introduces it, then explain how to read it in plain language.
- Label synthetic scenarios, inferred relationships, and illustrative data honestly.

## Selecting a Mermaid representation

| Relationship to explain | Mermaid representation |
|---|---|
| Ordered messages, actors, retries, or request traces | Sequence diagram |
| Decisions, branching, or a bounded procedure | Flowchart |
| Legal transitions, lifecycle, or recovery states | State diagram |
| Stable entities and their relationships | Class or entity-relationship diagram |
| Dependencies, ownership boundaries, or component interaction | Flowchart with clear subgroups |
| Delays, ordering, concurrency, or before/after events | Sequence diagram or timeline |
| Competing designs or changed constraints | Two clearly labelled Mermaid subgraphs or diagrams |
| Symptom, mechanism, intervention, and consequence | Causal flowchart |

## Clarity rules

- Match every node, edge, state, and label to the technical explanation.
- Explain the visual in words; the Mermaid diagram supports the explanation and does not replace it.
- Remove decorative elements that have no instructional job.
- Prefer one readable diagram over several dense diagrams.
