---
purpose: Defines the small set of reusable workspace files and project artifact conventions.
read_when: When creating a workspace, lesson artifact, glossary, casebook, or capstone document.
depends_on:
  - ../governance/source-policy.md
---

# P§1. Workspace layout and file formats

The repository stores the mission, curriculum, teaching/source rules, and actual project artifacts. It does not store learner-by-learner lesson completion or progress history.

    ../workspace/mission.md          learning goal and constraints
    ../workspace/resources.md        verified sources, sources to verify, coverage gaps
    GLOSSARY.md                      optional one-line definitions
    casebook/INDEX.md                optional concept → real cases → transferable pattern
    casebook/<concept>.md            optional researched failures for one concept
    lessons/<slug>.md                optional reusable lesson material
    reference/<slug>.md              optional checklists, diagrams, decision tables
    project artifacts                code, tests, ADRs, evaluation reports, traces, runbooks, deployment records

Create supporting directories only when a real artifact is needed. Do not create `workspace/evidence.md`, `learning-records/`, lesson-status checklists, session exports, or a retrieval-target database.

## Mission

`workspace/mission.md` defines the real-world outcome, success criteria, constraints, and out-of-scope topics. Keep one mission per workspace and under one screen. Confirm with the learner before changing it.

## Source catalogue

The section contract lives in `workspace/resources.md`: Verified references, References to verify, and Coverage gaps. Add or update a source only after opening the actual artifact and checking the relevant passage. Record bibliographic and reading status there; this is source provenance, not learner progress.

## Optional glossary

A glossary may be created when it materially helps the subject. Add or update a term only when the learner can use it correctly in context. It is not a completion record and is not loaded automatically in every session.

## Capstone and project artifacts

Store real outputs with the project they belong to: code, tests, architecture decisions, contracts, evaluation reports, traces, deployment notes, measured outcomes, and runbooks. These deliverables are necessary to build and defend the FDE capstone; they are not a separate personal learning ledger.

## Session continuity

The learner remembers and declares the current journey, unit, and part at the next session. The mentor asks once when the position is missing and accepts the learner's correction. No session-export format is required.
