---
purpose: Explains the repository for human readers.
read_when: When a human needs the repository overview.
depends_on:
  - AGENTS.md
---

---
purpose: Explains the repository for human readers.
read_when: When a human needs the repository overview.
depends_on:
  - AGENTS.md
---

# How to study with AI

This repository is a portable learning system for building durable technical
capability with AI support. It combines:

- a learner mission and explicit scope;
- prerequisite-aware journeys;
- source and evidence governance;
- adaptive, problem-first lessons;
- retrieval, transfer, and persistent learning records;
- honest progression from exposure to demonstrated capability.

The goal is not to consume explanations. It is to solve meaningful problems, explain
the reasoning, apply it in changed situations, and collect evidence that the
capability is real.

## Start here

1. Read [AGENTS.md](AGENTS.md). It routes every learning task to the canonical rules.
2. Read the active [mission](workspace/mission.md).
3. Check [evidence](workspace/evidence.md) before claiming progress.
4. Choose the appropriate journey:
   - [FDE journey](journeys/fde/journey-overview.md)
   - [Performance journey](journeys/performance/study-overview.md)
5. For a lesson, follow the routed [lesson protocol](teaching/lesson-protocol.md).

Humans can use this README as the overview. Agents must treat `AGENTS.md` and its
routed files as the operational source of truth.

## How learning works

The mentor preserves the existing problem-based, four-part lesson architecture:

1. **Curiosity and framing** — encounter a relevant problem and predict or frame it.
2. **Discovery and formation** — teach the smallest useful gaps, progressively.
3. **Exploration and boundaries** — inspect representations, misconceptions, failures,
   and trade-offs.
4. **Return and transfer** — solve the original problem and complete one changed-context
   practice task when the lesson requires it.

Lessons adapt to the learner's observable response. They may simplify, change
representation, increase depth, provide progressive hints, or answer directly when
requested. A lesson introduces no more than two new primary concepts; supporting
terms and examples do not silently become additional concepts.

Read the canonical [pedagogical principles](teaching/pedagogical-principles.md),
[adaptive lesson blueprint](teaching/head-first-lesson-blueprint.md), and
[scaffolding and feedback procedure](teaching/scaffolding-and-feedback.md) for the
design rules.

## Evidence and retention

The repository distinguishes:

| State | Meaning |
|---|---|
| Exposure | The learner encountered an explanation |
| Guided understanding | The learner succeeded with substantial support |
| Familiar independent application | The learner solved a known case unaided |
| Changed-context transfer | The learner applied the idea in a new scenario |

Reading, a correct immediate answer, or generated code is not sufficient evidence of
mastery. Future review opportunities are persisted through existing learning records
and session exports with a retrieval target, reason, eligible review opportunity,
evidence level, supporting observation, and review outcome. The system does not create
a second scheduling mechanism.

See [retrieval and transfer](teaching/retrieval-and-transfer.md),
[workspace formats](teaching/workspace-formats.md), and
[evidence policy](governance/evidence-policy.md).

## Repository map

| Area | Purpose |
|---|---|
| `workspace/mission.md` | Learning outcome, constraints, and scope |
| `workspace/evidence.md` | Supported capabilities, learning gaps, and prohibited claims |
| `workspace/resources*.md` | Registered, verified sources and coverage gaps |
| `journeys/` | Ordered learning units, prerequisites, and proof criteria |
| `teaching/` | Lesson delivery, assessment, retrieval, visual, and routing procedures |
| `learning-records/` | Demonstrated capability and next teaching target, when created |
| `casebook/` | Researched failures and transferable engineering patterns, when created |
| `reference/` and `lessons/` | Reusable lesson artifacts, when created |

## Governance

- **Source governance:** use registered, qualifying sources; cite exact sections and
  distinguish sourced facts from mentor synthesis and synthetic examples.
- **Evidence governance:** do not claim production experience, ownership, deployment,
  metrics, or mastery without supporting records.
- **Journey ownership:** reuse an existing unit before creating curriculum. A topic
  without an owner can use a traceable temporary learning scope through the
  [general-topic routing procedure](teaching/branch-map-protocol.md).
- **Quality:** technical correctness and pedagogical effectiveness are separate
  review dimensions. The [pedagogical quality gate](teaching/pedagogical-quality-gate.md)
  rejects applicable hard instructional violations before considering presentation
  improvements.
- **Agent boundaries:** curriculum, lesson design, tutoring, visual explanation,
  assessment, and learning memory are logical responsibilities of one orchestrated
  system; independent agents are not created for appearance.

## Validation

Future lesson simulations can use the repository-native
[behavioral acceptance fixture](teaching/behavioral-acceptance-fixture.md). It checks
definition-first openings, concept limits, misconception handling, direct-answer
requests, analogy failures, transfer, retrieval persistence, citation compliance,
general-topic routing, and quality-gate rejection.

The fixture is a documentation-driven review aid, not proof of runtime tutor
behavior. This repository currently records and governs the learning system; it does
not claim that the documented methodology has been empirically validated or that a
deployed agent has demonstrated these behaviors.
