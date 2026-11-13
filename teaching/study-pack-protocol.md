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

Use the Journey Unit or Temporary Learning Scope named by the learner. If the current unit is not named, ask one direct question before preparing the lesson. An unrelated temporary topic does not require loading or creating an FDE journey unit. Open only the selected scope's Verified source IDs
and the specific sections needed for that scope; do not load the entire library into
every lesson. Prepare one realistic problem, one learner-framing prompt, the causal
problem chain, a compact concept-link map from scope metadata, the relevant edge
cases, and retrieval questions for Parts 2–3. Prepare exactly one final practice
task only when the lesson type requires independent practice. Label lesson text as
Source-backed fact, Mentor synthesis, or Practice.

The scope handoff is explicit and stable:

| Stage | Required handoff |
|---|---|
| Topic request and scope creation | Stable Journey Unit ID or `TMP:<topic-slug>:<version>` Scope ID, one owner, one objective, prerequisites, source tags, and proof boundary |
| Source preparation and study pack | The same Scope ID, verified source sections, concept links, edge cases, and retrieval questions |
| Lesson blueprint and delivery | The same Scope ID, one outcome, and the scope's prerequisite and evidence boundary |
| Cumulative reinforcement | Relevant prerequisite concepts reappear briefly in later lessons and changed scenarios; no personal retrieval record is created |

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
| `active scope` | the selected Journey Unit or established Temporary Learning Scope | every lesson: scope metadata, prerequisites, source tags, and proof boundary | the user; the mentor records temporary scopes through [branch-map and general-topic routing](branch-map-protocol.md) | A, B, C |
| `../journeys/performance/study-overview.md` | the performance branch | when the journey opens it | the user | A, B, C |
| `../workspace/resources.md` | canonical source catalog | before teaching: relevant rows and status, and on every source claim | the user | A, B, C |
| `GLOSSARY.md` | earned terms | when a term is earned | the user | A, B, C |
| `casebook/` | real failures per concept | when a case is researched | the user | A, B, C |

The repository files listed above plus the selected active scope and relevant catalogue
rows are the minimum set for a lesson. For a journey or temporary scope and catalog,
"minimum set" means their rules and current scope metadata, not every phase or row of
a catalog ([context loading](context-loading.md)). `GLOSSARY.md` and `casebook/` are optional and are created only when useful (P§1). No learner-progress folder is created.

In a chat tool, use these files as project sources and keep instructions
short: follow [AGENTS.md](../AGENTS.md), use `session-protocol.md` when referenced, and
cite the uploaded sources. Add the selected primary sources for the current
unit as well. Generated quizzes, summaries, and audio are practice artifacts, not sources or learner-progress records.

### Synchronization

Re-check API, product, model, and security sources before teaching current
claims. When a source changes, update its registry row first, then compare
the affected journey tags and lesson citations. Never
silently replace a source or turn a candidate into evidence.
