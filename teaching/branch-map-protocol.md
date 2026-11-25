---
purpose: Defines one teaching procedure or workspace format.
read_when: When the procedure named in the routing table is required.
depends_on:
  - ../governance/source-policy.md
  - ../governance/evidence-policy.md
---

# P§10. Building a branch map (when the journey lacks lesson-level units)


## P§10. Building a branch map (when the journey lacks lesson-level units)

Use when the readiness check in [context loading](context-loading.md) finds no usable unit.

1. Read the active journey's goal and gates and `../workspace/mission.md`.
2. Research broadly across Project Sources and the wider source landscape. Start with relevant books for foundational concepts and use current primary sources for changing technical claims. Follow cross-references and compare strong treatments. Do not create source-read or verification-status registers.
3. Write the branch in the format used by `../journeys/fde/journey-overview.md`: phases, units with IDs (`P<phase>.<n>`), dependency statements, optional source suggestions, and explicit proof criteria. Source suggestions are not exclusive reading paths. Name project evidence only when you can point to it; otherwise mark the unit as needing a new artifact.
4. Do not maintain source-coverage gap or read-status ledgers. Search for strong material when a topic needs deeper coverage.
5. Show the tree to the user in compact form. After confirmation, teach the first unit. Do not teach during map building.

## General-topic routing

When a learner asks for a topic that is not owned by an existing journey unit:

1. Search the journey maps and supporting branches for a suitable existing unit.
2. Reuse that unit when its objective, prerequisites, source boundary, and evidence
   criteria fit. Do not create a duplicate owner.
3. If no unit fits, create a focused temporary learning scope for the request. Give
   it a stable Scope ID such as `TMP:<topic-slug>:<version>`; do not use a
   session-only timestamp as its identity. Record one owner (the mentor until a
   journey owner is assigned), one objective, explicit prerequisites, source tags,
   and a proof or no-evidence boundary.
4. Define the important prerequisite and later-connection links in the temporary scope so relevant concepts can recur naturally in later lessons. Do not create a learner retrieval record.
5. Keep the scope temporary unless the learner and repository owner approve a
   permanent journey change. Do not silently add a new curriculum branch.
6. Preserve curriculum traceability by reusing the stable Scope ID in any later journey unit that adopts the topic. This is curriculum provenance, not learner progress tracking.

The temporary scope may be taught through P§3 after its objective and source boundary
are recorded. If the topic needs multiple dependent units, stop and build a compact
branch map before teaching rather than hiding a new curriculum inside one lesson.
