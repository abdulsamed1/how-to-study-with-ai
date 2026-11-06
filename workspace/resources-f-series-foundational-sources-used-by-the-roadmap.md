---
purpose: Contains one source catalogue section.
read_when: When the named source catalogue section is needed.
depends_on:
  - ../governance/source-policy.md
---

# F-series — foundational sources used by the roadmap


## F-series — foundational sources used by the roadmap

These are concrete artifacts used by the active journey. Re-open the exact
page used before teaching and record the subsection or version in the lesson
record. F13 and F14 are cross-check and discovery sources, not a replacement
for primary technical evidence.

| ID | Source | Publisher | Type | Status | Coverage | Access | Last verified |
|---|---|---|---|---|---|---|---|
| F1 | [Pro Git, 2nd Edition — online book](https://git-scm.com/book/en/v2) | Git | Online book | Current | Git, collaboration, history, branching, and reproducible work | Public | 2026-10-09 |
| F2 | [MDN JavaScript Guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide) | MDN | Official guide | Current | JavaScript language and core concepts | Public; re-check per lesson | 2026-10-09 |
| F3 | [Node.js Learn](https://nodejs.org/learn) | Node.js | Official learning documentation | Current | Runtime, async work, testing, HTTP, diagnostics, and security. Exact page read 2026-10-21: [The Node.js Event Loop](https://nodejs.org/en/learn/asynchronous-work/event-loop-timers-and-nexttick) — What is the Event Loop, Event Loop Explained, Phases Overview and Phases in Detail (timers, pending callbacks, poll, check, close callbacks), setImmediate vs setTimeout, process.nextTick. Other F3 pages remain unrecorded | Public; re-check per lesson | 2026-10-21 |
| F4 | [MDN HTTP Overview](https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/Overview) | MDN | Official guide | Current | HTTP messages, methods, status codes, and API mental models | Public; re-check per lesson | 2026-10-09 |
| F5 | [TypeScript Handbook](https://www.typescriptlang.org/docs/handbook/intro) | TypeScript | Official handbook | Current | Types, narrowing, functions, modules, and compiler behavior | Public; re-check per lesson | 2026-10-09 |
| F6 | [PostgreSQL Documentation](https://www.postgresql.org/docs/current/) | PostgreSQL | Official documentation | Current | SQL, constraints, indexes, transactions, isolation, and concurrency | Public; re-check per lesson | 2026-10-09 |
| F7 | [Docker Get Started](https://docs.docker.com/get-started/) | Docker | Official guide | Current | Containers and local environment fundamentals | Public; re-check per lesson | 2026-10-09 |
| F8 | [Playwright Test documentation](https://playwright.dev/docs/intro) | Playwright | Official documentation | Current | Practical automated testing and CI tests | Public; re-check per lesson | 2026-10-09 |
| F9 | [OpenTelemetry documentation](https://opentelemetry.io/docs/) | OpenTelemetry | Official documentation | Current | Traces, metrics, logs, instrumentation, and context propagation | Public; re-check per lesson | 2026-10-09 |
| F10 | [Google Cloud Well-Architected Framework — Reliability](https://docs.cloud.google.com/architecture/framework/reliability) | Google Cloud | Architecture guidance | Current | Reliability goals, observation, response, recovery, and postmortems | Public; re-check per lesson | 2026-10-09 |
| F11 | [OWASP API Security Project](https://owasp.org/projects/api-security-project) | OWASP | Security guidance | Current | API attack surfaces and authorization/security risks | Public; use current edition | 2026-10-09 |
| F12 | [Effective context engineering for AI agents](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents) and [Contextual Retrieval](https://www.anthropic.com/engineering/contextual-retrieval) | Anthropic Engineering | Engineering articles | Current | Context budgets, retrieval design, and retrieval improvement techniques; these do not replace independent evaluation | Public; re-check per lesson | 2026-10-09 |
| F13 | [AI Engineer roadmap](https://roadmap.sh/ai-engineer) | roadmap.sh | Roadmap cross-check | Cross-check only | AI-engineering coverage across implementation, LLM applications, RAG, agents, deployment, and MLOps | Public; re-check for current scope | 2026-10-09 |
| F14 | [The Batch — AI Careers](https://www.deeplearning.ai/the-batch/tag/ai-careers) | DeepLearning.AI | Career discovery feed | Discovery only | Current AI-career articles and evolving industry skills; not a prerequisite order or sole evidence | Public; re-check per lesson | 2026-10-09 |
| F15 | [Python 3 documentation](https://docs.python.org/3/) (language reference, tutorial, library reference) | Python Software Foundation | Official documentation | Current | Language syntax, standard library, and core semantics for the Phases 2–17 implementation route | Public; re-check per lesson | 2026-10-22 |
| F16 | [Python typing documentation](https://docs.python.org/3/library/typing.html) and [mypy documentation](https://mypy.readthedocs.io/en/stable/) / [pyright](https://github.com/microsoft/pyright) | Python Software Foundation / mypy / Microsoft | Official documentation + tool docs | Current | Static type checking, narrowing, generics, and protocol types for the Python service | Public; re-check per lesson | 2026-10-22 |
| F17 | [Pydantic documentation](https://docs.pydantic.dev/latest/) | Pydantic | Official documentation | Current | Runtime validation at trust boundaries: models, parsing, serialization, and strict mode | Public; re-check per lesson | 2026-10-22 |
| F18 | [pytest documentation](https://docs.pytest.org/en/stable/) and [asyncio documentation](https://docs.python.org/3/library/asyncio.html) | pytest / Python Software Foundation | Official documentation | Current | Test discovery, fixtures, parametrization, and asyncio scheduling, cancellation, and timeouts | Public; re-check per lesson | 2026-10-22 |
