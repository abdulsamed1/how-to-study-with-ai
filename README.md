---
purpose: Explains the repository for human readers.
read_when: When a human needs the repository overview.
depends_on:
  - AGENTS.md
---

# How to study with AI

This repository is a portable, learner-led system for building durable technical capability with AI support. It contains:

- a clear learning mission;
- prerequisite-aware journeys and lesson units;
- verified source catalogues and research gaps;
- problem-first lessons with retrieval, reinforcement, and transfer;
- actual capstone artifacts such as code, tests, ADRs, evaluations, traces, deployment records, and runbooks.

**The learner owns progress.** The repository does not maintain a lesson-completion ledger, learning-record files, retrieval-target database, or session exports. At the start of a session, the learner names the journey, unit, and part. The mentor uses that declared position and never guesses completion from chat history or memory.

## Start here

1. Read [AGENTS.md](AGENTS.md).
2. Read the active [mission](workspace/mission.md).
3. Choose the journey:
   - [FDE journey](journeys/fde/journey-overview.md)
   - [Performance journey](journeys/performance/study-overview.md)
4. At each session, state the current journey, unit, and part.
5. Follow the routed [lesson protocol](teaching/lesson-protocol.md).

Agents must treat `AGENTS.md` and its routed files as the operational source of truth.

## How learning works

The mentor uses a problem-first, four-part lesson:

1. **Curiosity and framing** — encounter a relevant problem and predict or frame it.
2. **Discovery and formation** — teach the smallest useful gaps, progressively.
3. **Exploration and boundaries** — inspect representations, misconceptions, failures, and trade-offs.
4. **Return and transfer** — resolve the original problem and complete one changed-context practice task when the lesson requires it.

The mentor introduces no more than two new primary concepts at a time. Important earlier concepts recur naturally in later lessons when they are needed. Reinforcement uses concise reminders, contrasts, and changed scenarios — not repeated full lectures or a separate review database.

When the learner says a lesson has already been covered, the mentor accepts that correction and moves to the requested gap or next unit.

## Project artifacts are not progress files

The capstone still needs real engineering outputs: code, tests, contracts, ADRs, evaluation reports, traces, deployment notes, runbooks, and measured outcomes. They prove properties of the system being built and support honest portfolio claims. They are not a personal checklist of lessons completed.

Do not confuse these project deliverables with a learner-progress ledger. The latter is deliberately not used.

## Repository map

| Area | Purpose |
|---|---|
| `workspace/mission.md` | Learning outcome, constraints, and scope |
| `workspace/resources*.md` | Registered sources, verification status, and coverage gaps |
| `journeys/` | Ordered learning units, prerequisites, sources, and practice/exit criteria |
| `teaching/` | Lesson delivery, retrieval, reinforcement, visual, and routing procedures |
| `governance/` | Source rules and truthful capability/production claims |
| `casebook/` | Optional researched failures and transferable engineering patterns |
| `reference/` and `lessons/` | Optional reusable lesson artifacts |
| Capstone repository | Actual software, tests, architecture, evaluation, deployment, and operational artifacts |

## Governance

- **Source governance:** use qualifying sources; cite exact sections and distinguish source-backed facts from mentor synthesis and synthetic examples.
- **Capability claims:** do not claim production experience, ownership, deployment, metrics, business results, or mastery beyond what the actual work supports.
- **Journey ownership:** reuse an existing unit before creating curriculum. A topic without an owner can use a focused temporary scope through the [general-topic routing procedure](teaching/branch-map-protocol.md).
- **Learner ownership:** the learner decides what has been studied and what to study next. The mentor does not maintain progress status.
- **Quality:** technical correctness and lesson quality are reviewed separately with the [pedagogical quality gate](teaching/pedagogical-quality-gate.md).

## Validation

The [behavioral acceptance fixture](teaching/behavioral-acceptance-fixture.md) is a documentation-driven review aid. It checks explanation, concept limits, misconception handling, direct-answer requests, transfer, cumulative reinforcement, citation compliance, and general-topic routing. It is not proof of runtime tutor behavior or an empirically validated learning outcome.
