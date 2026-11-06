---
purpose: Contains one part of the FDE learning journey.
read_when: When the FDE journey or the named phase is active.
depends_on:
  - ../../workspace/mission.md
  - ../../workspace/resources.md
---

# Phase 15 — Security, privacy, and AI governance



**Goal:** Bound what the system, model, and tools can access or change, even when the model is wrong or manipulated.

**Handbook reading path (S69 [TOC]):** Ch. 9 §§9.1–9.14 (identity and credentials), Ch. 10 §§10.1–10.13 (authorization, tenant isolation, BOLA/IDOR, action auditing and tests), Ch. 11 §§11.1, 11.3–11.9, 11.11–11.25 (threat modeling, API risks, injection, SSRF, deserialization, mass assignment, secrets, privacy, supply chain, DoS, LLM security, security testing/review), and Ch. 32 §32.11 (LLM risks). The handbook's OWASP references are older; current taxonomy and governance must remain grounded in S16–S17 and S24, plus current provider guidance.

**Source pins for every lesson below:** OWASP LLM Top 10 2026 (published 2026-08-04) and OWASP Top 10 for Agentic Applications 2026 (December 2025, ASI01–ASI10) — always cite the edition; NIST AI RMF 1.0 (January 2023) plus the GenAI Profile NIST AI 600-1 (July 2024, twelve GAI risks with Govern/Map/Measure/Manage actions) — cite the profile, not just the framework homepage.

- **P15.1 — Assets, threat actors, trust boundaries, and abuse cases** — **Priority:** must-have. Depends on: P4.4, P10.4c, P11.6. Identify data, credentials, actions, tenants, external systems, and likely attack paths. **Proof:** threat model with mitigations and residual risk. Sources: S16–S17, S24, F11.
- **P15.2 — Prompt injection and untrusted content** — Implementation unit (multi-session). **Priority:** important. Depends on: P12.2–P12.5, P13.2. Direct/indirect injection, data-as-instruction confusion, and why prompting alone is not a security boundary. Start from a short list of attack categories, then pick two to test. When the two hand-built categories need scale or repetition, an automated black-box attack harness is the documented option (S61): promptfoo-style red-team tooling generates adversarial inputs against the running application, grades them, and reports quantified risk, with separate plugin classes for broken object-level and broken function-level authorization that reinforce (not replace) the permission-matrix and secure-boundary work of the later units in this phase; automated runs can ride CI like the P14.4 gate. The mitigation plan stays architecture-level regardless of tooling; plugin taxonomies are vendor naming, not a security standard. **Proof:** adversarial tests and an architecture-level mitigation plan. Sources: S16–S17; anchor case S32 (EchoLeak: benign-email XPIA bypass → reference-style Markdown link-redaction bypass → image auto-fetch → Teams preview-API CSP proxy; fixed server-side mid-2025; no in-the-wild exploitation observed); S61 for the automated-harness option. Teach it as demonstrated vulnerability with defense-in-depth mitigations (provenance-based access control, output sandboxing, strict CSP without open proxies), never as a how-to.
- **P15.3 — Least privilege, authorization, and human approvals** — **Priority:** important. Depends on: P4.4, P13.2–P13.5, P15.1. Allowlisted tools, scoped identities, user confirmation for consequential actions, and server-side policy enforcement. **Proof:** tool permission matrix plus denied-action tests. Sources: S16–S17, S24.
- **P15.4 — Sensitive data, secrets, tenant isolation, and retention** — **Priority:** important. Depends on: P3.7, P5.1–P5.6, P15.1. Coupled with: P12.2. Data minimization, access controls, log redaction, encryption responsibilities, and deletion flows. **Proof:** data-flow and retention review that checks the ingestion-time permission and retention hooks built in P12.2 and records any gap rather than retrofitting silently. Sources: S16, S24, F11.
- **P15.5 — Secure API and dependency boundaries** — **Priority:** important. Depends on: P4.4–P4.6, P9.1–P9.2, P15.1–P15.4. Authorization flaws, injection, resource exhaustion, dependency trust, and configuration mistakes. **Proof:** security checklist and tests mapped to actual routes and tools, including a cross-user or cross-tenant access test written from the requirement rather than from the generated handler. Sources: F11, S39 (§2.2, REC-API-12.3).
- **P15.6 — Audit, incident response, and AI risk governance** — **Priority:** important. Depends on: P9.5, P14.5, P15.1–P15.5. Logs, kill switches, incident ownership, residual risk, and lifecycle-based risk review. **Proof:** operational security runbook and risk register. Sources: S16–S17, S24.
