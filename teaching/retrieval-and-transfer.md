---
purpose: Integrates retrieval, retention, interleaving, transfer, and mastery evidence.
read_when: When planning assessment, a lesson close, or a future review.
depends_on:
  - pedagogical-principles.md
  - retrieval-protocol.md
  - ../workspace/evidence.md
  - records.md
---

# Retrieval, retention, and transfer

Use the existing records and journey retrieval fields. This procedure adds no second
calendar or scoring system.

## Evidence ladder

| State | What it shows |
|---|---|
| Read an explanation | Exposure only |
| Followed a guided example | Supported recognition or procedure |
| Solved a familiar problem unaided | Initial capability in a known context |
| Applied the idea in a changed scenario | Transfer evidence |
| Repeated transfer with the journey proof artifact | Stronger capability evidence |

## Persisted retrieval record

For every future review opportunity that should survive the session, update the
existing learning record or its session export with one stable target entry:

| Field | Required content |
|---|---|
| Retrieval target | Concept, skill, or capability to recall later; use the existing unit ID when one exists |
| Retrieval reason | Difficulty, repeated misconception, failed transfer, high importance, weak unaided recall, or demonstrated uncertainty |
| Next eligible review | Next session, a later session, when a related concept appears, or when another difficulty triggers review |
| Evidence level | Exposure, guided understanding, familiar independent application, or changed-context transfer |
| Supporting evidence | The observed response, task, record, or artifact that justifies the entry |
| Review outcome | Successful recall, recall with hint, misconception persisted, independent application succeeded, or transfer remains unproven |

Use one entry per stable target and update its outcome rather than creating duplicate
entries. A review outcome is optional until the target is revisited. Older records
without these fields remain valid: interpret them as having no persisted retrieval
metadata and add the fields at the next relevant session. Scheduling remains owned by
[P§5](retrieval-protocol.md); these fields do not create a second scheduler.

## Retrieval moves

- **Immediate:** after the concept, ask for a brief explanation, contrast, or mechanism
  without showing the answer. Use one question, not an interrogation.
- **Delayed:** place important or difficult ideas in the existing later-session
  retrieval record and revisit them in a changed scenario.
- **Interleaving:** mix related concepts only after initial acquisition, to make the
  learner distinguish mechanisms or decisions rather than repeat a pattern.
- **Transfer:** change the constraint, input, failure point, stakeholder, or business
  consequence. Ask for reasoning and evidence, not only a label.

## Adaptive review

Choose future review from importance, difficulty, previous performance, misconception
risk, and available session state. State the rationale. Do not invent universal
intervals or claim a review schedule is evidence-based without a registered source.

## Close and record

End the lesson with exactly one practice task when [P§3](lesson-protocol.md) requires
independent practice. Diagnostic and retrieval questions do not count as practice.
Record what the learner independently demonstrated, what remained supported, the
misconception corrected, and the next retrieval target. Do not advance because content
was covered.
