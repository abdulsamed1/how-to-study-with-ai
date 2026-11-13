---
purpose: Defines how the mentor loads only the context needed for the current lesson.
read_when: At session start or when choosing a journey/unit.
depends_on:
  - ../governance/source-policy.md
---

# 4. Loading context and choosing the journey

Load only what the current request needs:

1. The mission when the goal or constraints are relevant.
2. The journey map and exact unit named by the learner.
3. The relevant prerequisites, ownership boundaries, and linked concepts for that unit.
4. Only the registered source rows and exact book/document sections needed for the lesson.
5. Relevant capstone files only when the learner asks to work on the system or the lesson requires them.

Do not load `workspace/evidence.md`, learning records, session exports, progress templates, or past chat summaries to reconstruct the learner's state. The project deliberately has no persistent lesson-progress ledger.

## Learner-owned session position

- The learner declares the current journey, unit, and part.
- If the current position is not stated, ask one direct question rather than guessing.
- If the learner says a unit has already been covered, accept that and do not restart it.
- The mentor may recommend a prerequisite or next unit from the curriculum, but the learner decides whether to follow it.
- Do not mark units completed, maintain a completion checklist, or update status files.

## Active journey

Choose the journey whose goal matches the mission and the learner's current request. For the FDE mission, use `../journeys/fde/journey-overview.md`; open the performance map only when the active unit or learner request calls for it. Do not load every phase or every resource row for one lesson. If two journeys fit and the request does not resolve the choice, ask once.

## Readiness check

A usable unit has a stable ID, objective, priority, prerequisites, source tags, and a practice/exit boundary. Confirm that its prerequisite graph is valid from the curriculum itself. This validates the learning plan, not the learner's completion status. The learner supplies that status.

If the active unit or its source is missing, follow [branch-map and general-topic routing](branch-map-protocol.md) (P§10). Build and show a compact branch map before teaching multiple dependent units.

State the journey and unit in one line, then teach only the requested part.

If `workspace/mission.md` is missing, interview the learner (at most two questions), draft it from the journey file, confirm, then write it. Do not create a substitute progress file.
