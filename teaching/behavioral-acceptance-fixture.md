---
purpose: Provides a lightweight, repository-native fixture for reviewing teaching behavior.
read_when: When validating a lesson simulation or changing instructional procedures.
depends_on:
  - pedagogical-quality-gate.md
  - lesson-protocol.md
  - retrieval-and-transfer.md
  - branch-map-protocol.md
  - ../governance/source-policy.md
  - ../governance/evidence-policy.md
---

# Behavioral acceptance fixture

This is a simulated, documentation-driven checklist. It is not an executable tutor
test and cannot prove runtime behavior. Record the transcript or review artifact
beside each case when using it.

| ID | Scenario | Expected behavior | Failure condition | Rule / evidence |
|---|---|---|---|---|
| BA-01 | Definition-first opening where discovery is needed | Replace it with a concise problem and wait for framing or prediction. | Definition is delivered without a learner need or explicit request. | P01, P§3; transcript |
| BA-02 | Lesson needs three candidate concepts | Select no more than two primary concepts and defer the rest. | Three independently taught concepts appear in one lesson. | Session loop, P05; concept inventory |
| BA-03 | Supporting term appears | Explain it briefly in service of a primary concept and do not assess it as a separate objective. | Supporting term silently becomes a third concept. | Session loop; concept inventory |
| BA-04 | Repeated misconception | Change intervention: hint, representation, counterexample, partial reasoning, then direct explanation as useful. | Same wording is repeated or learner is shamed. | Scaffolding procedure; transcript |
| BA-05 | Direct explanation requested | Answer directly, state limits, then optionally use one retrieval/application check. | Discovery is forced or the answer is withheld. | MENTOR-09; transcript |
| BA-06 | Analogy causes confusion | Drop or bound the analogy and return to a concrete example or visual. | Analogy is defended as the technical model. | P06/P08; transcript |
| BA-07 | Familiar answer fails in changed context | Diagnose copying, restate the invariant, and require changed-context reasoning before mastery. | Familiar success is recorded as transfer. | P13, evidence ladder; record |
| BA-08 | Immediate retrieval succeeds | Reduce support or increase depth; record only the evidence shown. | Lesson remains artificially basic or claims mastery without transfer. | Scaffolding, EVD-02; record |
| BA-09 | Retrieval needs a hint | Record guided understanding or recall-with-hint and choose a justified future review. | Hint-supported recall is recorded as unaided mastery. | Retrieval fields; record |
| BA-10 | Session closes with future review | Persist one stable retrieval target through record/export fields. | Target exists only in chat prose or is duplicated. | P§1/P§5; two-session record comparison |
| BA-11 | Practice is required | End with exactly one changed-scenario practice task. | Zero or more than one final practice task. | P§3; task count |
| BA-12 | Technical claim is cited | Use registered S-ID, exact section, canonical location, and access/publication data as required; label synthesis/examples. | Missing source identity/section or invented citation. | SRC-01–06; citation review |
| BA-13 | Topic has no journey unit | Search and reuse first; otherwise create a stable temporary scope with owner, objective, prerequisites, sources, evidence boundary, and retrieval target where needed. | Duplicate permanent curriculum unit or untracked lesson. | P§10; routing record |
| BA-14 | Lesson review finds a hard defect | Determine applicable criteria, reject, correct, and re-evaluate. | Presentation quality compensates for a hard invariant violation. | Quality gate; before/after review |
| BA-15 | Learner gives a partial misconception after the last-available-seat prompt | Stop after the opening question; after the learner's answer, preserve the valid part, give one targeted hint, and wait for revision before explaining conditional update, uniqueness, or transaction boundaries. | The mentor invents the learner's answer, reveals the mechanism immediately, or continues through the planned lesson without a response. | Interaction turn discipline; transcript |

## Use

Count primary concepts separately from supporting vocabulary. Mark each case
`pass`, `fail`, or `not applicable`, cite the transcript line or record field, and
rerun affected cases after correction. A completed fixture supports documentation
acceptance only; it is not learner capability evidence.
