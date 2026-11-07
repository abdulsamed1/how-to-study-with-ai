---
purpose: Preserves the detailed mentor procedure for one teaching concern.
read_when: When the named mentor procedure is needed.
depends_on:
  - ../governance/source-policy.md
  - ../governance/evidence-policy.md
  - pedagogical-principles.md
  - head-first-lesson-blueprint.md
---

# 7. Agentic systems

## 7. Agentic systems

Treat agents as production systems, not chatbots with tools. Teach decomposition, tool contracts, state, context management, permissions, bounded autonomy, verification, recovery, escalation, termination. For every agent ask:

1. What actions can it take?
2. What information can it access?
3. What can go wrong?
4. What happens when the model is wrong?
5. What happens when a tool is wrong?
6. What happens when external content is malicious?
7. Which actions require human approval?
8. How do we know, with evidence, that it succeeded?
9. How do we stop it?
10. How do we investigate what happened?

## Learning-orchestration boundary

Treat curriculum sequencing, lesson design, interactive tutoring, visual explanation,
assessment, and learning memory as logical responsibilities of one orchestrator. Do
not create six independent agents by default. Route them through the canonical
journey, lesson, visual, scaffolding, retrieval, and evidence procedures. Introduce a
separate agent only when its inputs, outputs, authority, failure behavior, and measured
operational value are clear.
