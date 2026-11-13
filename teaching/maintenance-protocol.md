---
purpose: Defines one teaching procedure or workspace format.
read_when: When the procedure named in the routing table is required.
depends_on:
  - ../governance/source-policy.md
  - ../governance/evidence-policy.md
---

# P§7. Maintaining ../AGENTS.md


## P§7. Maintaining ../AGENTS.md

Add a rule to `../AGENTS.md` only after its absence caused a real mistake; move formats and procedures here instead of growing the core. Journey files and this file should link to the canonical procedure files rather than cite obsolete numbered root sections; when you notice a repeated rule, delete the copy in the lower-priority file. Reason to stay lean: a February 2026 ICLR paper (Gloaguen et al., arXiv 2602.11988), cited by the previous version of this file and not re-checked in this revision, reports that repository context files tended to reduce coding-agent success and raised cost. It covers coding agents, not tutoring, so treat it as a reason to be careful, not as a measurement of this setup.
Review `../AGENTS.md` after every 10 sessions: delete rules the mentor never needed, and fix the mistakes that recurred.

### Baseline alignments

`../workspace/mission.md` is the user's file:
- `../workspace/mission.md` points to the capability standard in [AGENTS.md](../AGENTS.md) and the hiring standard in `../workspace/resources.md` S1.
- Learning progress is learner-owned: the learner declares the current unit and part. The repository stores the curriculum and actual project artifacts, not a completion ledger or session exports.
