---
purpose: Explains the learner-led workflow for studying with AI.
read_when: When a human is starting or using a learning workspace.
depends_on:
  - ../AGENTS.md
  - ../workspace/mission.md
---

# The repeatable learning loop

1. **Define the goal.** State the real-world outcome and why it matters.
2. **Choose the journey.** Use the existing curriculum and prerequisites; do not invent a parallel roadmap.
3. **Declare your current position.** At the start of each session, tell the assistant the journey, unit, and part you want to continue.
4. **Verify the material.** Open the relevant source and check the exact passage/version.
5. **Learn one part at a time.** Start with a problem, learn the smallest useful concepts, inspect failure modes, then apply the idea.
6. **Retrieve and connect.** Recall important ideas without copying. Earlier concepts should reappear naturally in later lessons when relevant.
7. **Practise in a changed scenario.** Use one meaningful application task when the lesson requires it.
8. **Own the sequence.** You decide when a unit is complete and what to study next. The assistant may recommend a next unit, but it does not track your progress or infer it from chat history.
9. **Protect real-world claims.** Keep actual project outputs such as tests, ADRs, evaluation reports, traces, deployments, and runbooks. Do not mistake a lab for production experience.

## Starting your own learning workspace

Begin with a small setup:

- Define `workspace/mission.md`.
- Configure `AGENTS.md` with reusable mentor rules.
- Choose or build a journey with stable unit IDs, prerequisites, sources, and practice/exit criteria.
- Maintain `workspace/resources.md` for source verification and research gaps.
- Keep actual project deliverables in the project they belong to.

Do not create a separate learner-progress ledger, learning-record folder, or review schedule.

## Session-start prompt

~~~text
I am continuing this learning journey:

Journey:
Current unit:
Current part:

I have already studied:
[Optional note. I own this learning history; do not try to infer it.]

Please use this declared position. Do not repeat a completed lesson unless I ask.
Reconnect relevant earlier concepts briefly when they help explain the current unit.
Teach one part at a time, use verified sources, and wait for my response at the interaction points.
~~~

## Reusable principles

- Goal before roadmap.
- Prerequisites before advanced topics.
- Teach before testing.
- Retrieve and re-encounter concepts in relevant later lessons.
- Prefer changed scenarios to repeating the same question.
- Verify source-backed claims.
- Keep project artifacts separate from learner-progress state.
- Human ownership: the learner controls the learning sequence and is accountable for real project decisions.
- Keep context lean: load only the current unit and the sources it needs.

## What this system is not

- It is not a progress tracker or learner profile database.
- It does not infer which lessons you have completed.
- It does not guarantee expertise because an AI says you are doing well.
- It is not tied to one AI tool or model provider.

AI systems can make mistakes, cite weak sources, and miss context. Verify important information against original sources and inspect real project behavior.
