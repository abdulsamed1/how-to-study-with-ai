---
purpose: Contains one FDE journey support register or gate.
read_when: When checking FDE gates, sources, progress, or milestones.
depends_on:
  - journey-overview.md
  - ../../workspace/resources.md
---

# 8. Progress ledger template


## 8. Progress ledger template

Only update a checkbox when proof exists. Record the artifact path, commit, test report, decision record, or learning record next to it.

```text
Phase 2  [ ] P2.1 [ ] P2.2 [ ] P2.3 [ ] P2.4 [ ] P2.5
Phase 3  [ ] P3.1 [ ] P3.2 [ ] P3.4 [ ] P3.5 [ ] P3.6 [ ] P3.7
Phase 4  [ ] P4.1 [ ] P4.2 [ ] P4.3 [ ] P4.4 [ ] P4.5 [ ] P4.6 [ ] P4.7a [ ] P4.7b [ ] P4.8a [ ] P4.8b [ ] P4.9
Phase 5  [ ] P5.1 [ ] P5.2 [ ] P5.3 [ ] P5.4 [ ] P5.5 [ ] P5.6 [ ] P5.7
Phase 6  [ ] P6.1 [ ] P6.2 [ ] P6.3 [ ] P6.4 [ ] P6.5 [ ] P6.6
Phase 7  [ ] P7.1 [ ] P7.2 [ ] P7.3 [ ] P7.4 [ ] P7.5a [ ] P7.5b [ ] P7.5c [ ] P7.6 [ ] P7.7 [ ] P7.8
Phase 8  [ ] P8.1 [ ] P8.2 [ ] P8.3 [ ] P8.4 [ ] P8.5 [ ] P8.6 [ ] P8.7
Phase 9  [ ] P9.1 [ ] P9.2 [ ] P9.3 [ ] P9.4 [ ] P9.5 [ ] P9.6 [ ] P9.7
Phase 10 [ ] P10.1 [ ] P10.2 [ ] P10.3 [ ] P10.4a [ ] P10.5 [ ] P10.6 [ ] P10.4b [ ] P10.4c [ ] P10.8 [ ] P10.7
Phase 11 [ ] P11.1 [ ] P11.2 [ ] P11.3 [ ] P11.4 [ ] P11.5 [ ] P11.6
Phase 12 [ ] P12.1 [ ] P12.2 [ ] P12.3 [ ] P12.4 [ ] P12.5 [ ] P12.6 [ ] P12.7
Phase 13 [ ] P13.1 [ ] P13.2 [ ] P13.3 [ ] P13.4 [ ] P13.5 [ ] P13.6 [ ] P13.7
Phase 14 [ ] P14.1 [ ] P14.2 [ ] P14.3 [ ] P14.4 [ ] P14.5 [ ] P14.6 [ ] P14.7
Phase 15 [ ] P15.1 [ ] P15.2 [ ] P15.3 [ ] P15.4 [ ] P15.5 [ ] P15.6
Phase 16 [ ] P16.1 [ ] P16.2 [ ] P16.3 [ ] P16.4 [ ] P16.5
Phase 17 [ ] P17.1 [ ] P17.2 [ ] P17.3 [ ] P17.4
```

#### ID migration record

No live unit ID changes in this structural pass. The table records retired units and their consolidated destinations. Retired IDs are never reused.

| Old ID | New ID | Status |
|---|---|---|
| P0.1 | P2.1 + P10.2 | merged; the demo / working-system / deployed-outcome distinction stays definitional in `../../AGENTS.md` §6 and is applied in P10.2; P2.1 no longer draws a delivery-loop diagram |
| P0.2 | P2.1 | merged; toolchain check and a short evidence-based baseline in `../../workspace/evidence.md` |
| P0.3 | P2.1 + P10.1 | split by stage; P2.1 keeps only the five-line Problem Card (`docs/problem-card.md`), and P10.1 produces the evidence-informed workflow map and problem statement |
| P1.1 | P2.1 | merged; virtual environment, paths, processes, and environment variables bootstrapped in P2.1 |
| P1.2 | P2.1 + P9.2 | split by stage; repository initialization stays in P2.1, and branching plus merge-conflict resolution move to the P9.2 release rehearsal |
| P1.3 | P2.2 | merged; code reading across unfamiliar codebase practiced in P2.2 owned-system lab |
| P1.4 | P2.2 | merged; runtime failure reproduction, inspection, and regression verification proven in P2.2 fixture harness |
| P1.5 | P2.2 | merged; requirement-first testing and red-green assertions proven in P2.2 validation fixtures |
| P3.3 | P2.2 | merged |
| P4.7 | P4.7a + P4.7b | split |
| P4.8 | P4.8a + P4.8b | split |
| P7.5b (old combined unit) | P7.5t (tombstone); content split into P7.5b + P7.5c | split; the live P7.5b keeps its ID and progress checkbox |
| P10.4 | P10.4a + P10.4b + P10.4c | split |
