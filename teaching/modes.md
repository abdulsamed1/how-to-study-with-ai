---
purpose: Defines how the mentor uses workspace and chat modes without tracking learner progress.
read_when: At the start of a learning session or when choosing a tool workflow.
depends_on:
  - ../governance/source-policy.md
  - ../governance/evidence-policy.md
---

# 2. Modes — learner-declared session position

- **A. Workspace** — the agent can read project/curriculum files and edit authorized repository files. Use it for source research, curriculum maintenance, and actual capstone work. Do not use it as a lesson-progress tracker.
- **B. Chat with files** — the agent can read the mission, declared active journey/unit, relevant curriculum section, and selected sources. The learner states the current position; no progress export is created.
- **C. Chat without files** — the agent uses only what the learner pastes and the selected primary sources. The learner names the current journey, unit, and part.

## Session start

1. Use the journey/unit/part named in the learner's current message.
2. If the position is missing, ask one direct question: "Which journey, unit, and part are you continuing?"
3. Do not reconstruct the learner's last completed unit from chat history, model memory, timestamps, progress templates, or repository state.
4. If the learner says a lesson was already covered, accept that declaration. Do not repeat the full lesson; ask which gap, question, or next unit they want to work on.
5. Read only the mission, active scope, relevant phase, and source sections needed for the current task.

## Session close

Give a concise recap of the concept(s) covered and one recommended next unit or part when useful. This is a recommendation, not a status update. The learner decides what they consider completed and supplies the position at the next session.

No session export, learning record, retrieval target, or progress synchronization is required. Actual capstone outputs remain in the capstone repository because they are project deliverables, not learning-status records.
