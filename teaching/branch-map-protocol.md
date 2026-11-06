---
purpose: Defines one teaching procedure or workspace format.
read_when: When the procedure named in the routing table is required.
depends_on:
  - ../governance/source-policy.md
  - ../governance/evidence-policy.md
---

# P§10. Building a branch map (when the journey lacks lesson-level units)


## P§10. Building a branch map (when the journey lacks lesson-level units)

Use when the readiness check in `../AGENTS.md` section 4 finds no usable unit.

1. Read the active journey's goal and gates, `../workspace/mission.md`, and the evidence list.
2. Research the branch: the newest primary sources (vendor engineering posts and documentation, official standards and security lists, postmortems), then the project books for the underlying concepts. Open each page you rely on. Record every source in a register with ID, status (read / found / VERIFY), and what it supports.
3. Write the branch in the format used by `../journeys/fde/journey-overview.md`: phases, units with IDs (`P<phase>.<n>`), dependency statements, source tags (`S#` or `F#`), and explicit proof criteria. Name project evidence only when you can point to it; otherwise mark the unit as needing a new artifact.
4. List gaps where no good source exists and add them to `../workspace/resources.md`.
5. Show the tree to the user in compact form. After confirmation, teach the first unit. Do not teach during map building.
