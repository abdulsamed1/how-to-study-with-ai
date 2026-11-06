---
purpose: Contains one part of the FDE learning journey.
read_when: When the FDE journey or the named phase is active.
depends_on:
  - ../../workspace/mission.md
  - ../../workspace/resources.md
---

# Phase 3 — Chosen implementation runtime



**Goal:** Build production service code in Python. Python implementation claims for P3.1–P3.7 are grounded in verified sources F15–F18 and `../../teaching/session-protocol.md` P§6; language-specific reading of an existing repository is conditional on the linked owned-system task, not a runtime-learning prerequisite.

**Handbook reading path (S69 [TOC]):** Ch. 37 §§37.2, 37.4–37.6, 37.10, 37.13–37.15 (Python/FastAPI, Pydantic models, response/error behavior, async endpoints, tests, project structure, and deployment). Use the Python concepts directly; skip the chapter's Node-comparison and NestJS comparison tracks.

- **P3.1 — Types and compiler/runtime feedback** — **Priority:** important. Depends on: P2.1–P2.5. Use the chosen language's type system, static checks, and diagnostics where available. **Proof:** turn the Phase 2 payload normalizer into typed, checked code. Sources: F15, F16.
- **P3.2 — Valid and invalid data states** — **Priority:** important. Depends on: P3.1, P2.4, P2.2. Model optional data and event variants explicitly. **Proof:** process multiple event types without unsafe assumptions. Sources: F15, F16.
- **P3.3 — merged into P2.2.** Tombstone: runtime validation at trust boundaries is taught once, in P2.2 (which now covers the runtime-vs-static distinction its fixture table demonstrates). Dependents re-pointed to P2.2.
- **P3.4 — Process, packages, and scripts** — **Priority:** must-have. Depends on: P2.1, P2.5, P3.1. Process lifecycle, dependency lockfiles, package scripts, and reproducible startup. Configuration files, config validation, and secret boundaries are P3.7's unit; do not re-teach them here. **Proof:** bootstrap a reproducible Python service using P3.7's configuration and secret conventions. Source: F15.
- **P3.5 — Non-blocking I/O and blocking work** — **Priority:** must-have. Depends on: P2.3, P3.4. Understand why one slow or blocking operation can affect concurrency in the Python service. **Proof:** identify and remove a blocking operation in the capstone service, and show event-loop delay or equivalent Python runtime evidence before and after; record the diagnostic used and what it does not reveal. Sources: F15, F18; S28 ch. 4 (read: concurrent-system models, for general mechanism only; not Python-specific behavior).
- **P3.6 — Async failure, cancellation, timeouts, and resource cleanup** — **Priority:** must-have. Depends on: P2.3, P3.4–P3.5. Avoid orphaned tasks, leaked resources, and work that outlives its request. **Proof:** implement timeout-aware I/O and cleanup paths in Python; find one seeded resource leak from runtime evidence; on shutdown, in-flight work and resources are cleaned up within a bound defined in the test. **AI-dependency bridge:** add a slow mode to the P2.1 stub and use it as the provider that overruns its deadline; the proof is that the call is cancelled, the resource is released, and shutdown completes within the bound — not that a retry hides the delay. Sources: F15, F18; S28 ch. 4 (read: concurrent-system models, for general mechanism only); S19 ch. 9 [TOC]. The leak and shutdown evidence is the learner's own runtime evidence, not a book claim.
- **P3.7 — Logging, configuration, and secret hygiene** — **Priority:** important. Depends on: P3.4, P3.6. The single treatment of configuration, secrets, and diagnostics hygiene in Phases 1–10: structured logs, config validation, secret injection and storage, and redaction in logs. **Proof:** logs support diagnosis without exposing credentials, and one deliberately broken configuration or missing credential is diagnosed from exit code and stderr before the fix (the environment-diagnosis exercise relocated here from P2.1). Sources: F15, F11.

P3.1–P3.2 and P3.4–P3.7 (P3.3 is merged into P2.2; see its tombstone) are implemented in Python. Existing-project code reading remains conditional on P7.7/P7.8 or an explicitly named target-role requirement; it is not a second implementation track.
