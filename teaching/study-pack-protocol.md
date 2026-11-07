---
purpose: Defines one teaching procedure or workspace format.
read_when: When the procedure named in the routing table is required.
depends_on:
  - ../governance/source-policy.md
  - ../governance/evidence-policy.md
---

# P§9. Source-grounded study-pack procedure


## P§9. Source-grounded study-pack procedure

### Source triage

For each source needed by a lesson:

1. Open the publisher's canonical page or the supplied book.
2. Confirm title, publisher, relevance, currency, and URL.
3. Record the date and exact section, chapter, or page in `../workspace/resources.md`.
4. Mark it Verified only after those checks; move failed or obsolete entries to
   References to verify or Coverage gaps; never silently retain a stale
   or degraded entry as verified.

### Lesson preparation

Select one usable unit from the active journey, or one established temporary Scope ID
from [general-topic routing](branch-map-protocol.md) when no journey unit fits. Open
only its Verified source IDs and the specific sections needed for that scope; do not
load the entire library into every lesson. Prepare one realistic problem, one
learner-framing prompt, the causal problem chain, a compact concept-link map from
journey or scope metadata, the relevant edge cases, and retrieval questions for
Parts 2–3. Prepare exactly one final practice task only when the lesson type requires
independent practice. Label lesson text as Source-backed fact, Mentor synthesis, or
Practice.

Decide the unit's working mode before preparing the practice task, and record
it with the lesson: (1) the learner writes and debugs the code; (2) the
learner specifies the work and reviews agent-produced code; (3) delegated
implementation combined with a learner-designed experiment and independent
verification. Follow the active journey's rules on human-in-the-loop
engineering and on hand-writing versus review; do not restate them here.

### Tool import and export

The file manifest — what each file is for, when it is loaded, who writes it,
and which modes need it:

| File | Purpose | Loaded when | Written by | Modes |
|---|---|---|---|---|
| `../workspace/mission.md` | why the user is learning this | every session | the user; the mentor drafts it only with the user's confirmation | A, B, C |
| `../AGENTS.md` | how to teach | every session | the user | A, B, C |
| `session-protocol.md` | procedures and formats | when a session needs one | the user | A, B, C |
| `../journeys/fde/journey-overview.md` | the canonical FDE journey | every session: rules, gates, route layer, and current phase | the user | A, B, C |
| `../journeys/performance/study-overview.md` | the performance branch | when the journey opens it | the user | A, B, C |
| `../workspace/resources.md` | canonical source catalog | before teaching: relevant rows and status, and on every source claim | the user | A, B, C |
| `../workspace/evidence.md` | the evidence ledger | every session | the user | A, B, C |
| `GLOSSARY.md` | earned terms | when a term is earned | the user | A, B, C |
| `casebook/` | real failures per concept | when a case is researched | the user | A, B, C |
| `learning-records/` | evidence of understanding | when a record is earned | the user | A, B, C |

The first seven are the minimum set for a lesson. For the journey or temporary scope
and catalog, "minimum set" means their rules and current scope metadata, not every
phase or row ([context loading](context-loading.md)). `GLOSSARY.md`, `casebook/` and `learning-records/` are
created as the first file for them exists (P§1).

In a chat tool, use these files as project sources and keep instructions
short: follow [AGENTS.md](../AGENTS.md), use `session-protocol.md` when referenced, and
cite the uploaded sources. Add the selected primary sources for the current
unit as well. Generated quizzes, summaries, and audio are practice artifacts;
do not promote them to durable learning records until checked against a cited
source.

### Synchronization

Re-check API, product, model, and security sources before teaching current
claims. When a source changes, update its registry row first, then compare
the affected journey tags, lesson citations, and evidence records. Never
silently replace a source or turn a candidate into evidence.
