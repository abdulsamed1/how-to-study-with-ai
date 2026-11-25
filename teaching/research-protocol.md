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
2. Use the strongest available primary material. If a primary source cannot be accessed, use other accessible sources without presenting them as the primary author's account.
3. Select cases for explanatory value, transferability, and source quality. Keep concise case notes in `casebook/<concept>.md` when they materially help future lessons.
4. Record each case concisely: title and URL; what happened; root cause (mechanism); fix or mitigation; transferable pattern; and where it could appear in the user's projects. Do not add source-read or verification-status fields.
5. Add one line per concept to `casebook/INDEX.md`: concept, case titles, the pattern they share.
6. Paraphrase. Quote at most a short phrase. Link every non-obvious claim.
