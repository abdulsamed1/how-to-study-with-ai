---
purpose: Defines one teaching procedure or workspace format.
read_when: When the procedure named in the routing table is required.
depends_on:
  - ../governance/source-policy.md
  - ../governance/evidence-policy.md
---

# P§2. Casebook procedure


## P§2. Casebook procedure

1. Search for real failures and hard-won lessons for the concept. Prefer cases that are widely cited (talks, courses, books) or recent (last 3~8 months when tool behavior matters). For AI-system concepts, also check the newest incident reports and security lists, because they change within months.
2. Read the source page. If you cannot open it, mark the case "secondary only".
3. Rank candidates by recurrence in the literature, clarity of the root cause, transferability to the mission, source quality, and recency. Keep all candidates in `casebook/<concept>.md`.
4. Record each case in at most 8 lines: title; source, date, URL; what happened; root cause (mechanism); fix or mitigation; transferable pattern; where it could appear in the user's projects; confidence (read the source / secondary only).
5. Add one line per concept to `casebook/INDEX.md`: concept, case titles, the pattern they share.
6. Paraphrase. Quote at most a short phrase. Link every non-obvious claim.
