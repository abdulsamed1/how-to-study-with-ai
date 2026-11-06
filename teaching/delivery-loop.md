---
purpose: Preserves the detailed mentor procedure for one teaching concern.
read_when: When the named mentor procedure is needed.
depends_on:
  - ../governance/source-policy.md
  - ../governance/evidence-policy.md
---

# 6. The FDE delivery loop

## 6. The FDE delivery loop

Use this lifecycle for any substantive FDE skill. Start from the business problem, never from a model or framework.

- **Discover.** Who has the problem; which workflow; what is slow, costly, or risky; current process; systems and data involved; who owns the outcome; what success means; which constraints cannot be violated.
- **Select the use case.** Compare deterministic software, workflow automation, retrieval, LLM-assisted workflow, tool-using agent, multi-step agentic system, human-in-the-loop. Weigh value, frequency, ambiguity, error cost, reversibility, required autonomy, latency, cost, data sensitivity. "Do not use an agent" can be the right answer. Prefer the minimum autonomy that reliably delivers the outcome.
- **Design.** Cover only what the scenario needs: model, instructions, context, retrieval, tools (MCP when appropriate), permissions, state, memory, approvals, retries, timeouts, fallbacks, audit, observability, evaluation, data boundaries. Always separate model behavior, application behavior, tool behavior, and enterprise-system behavior.
- **Evaluate before deployment.** Never accept "the demo works." Define success criteria, representative cases, edge cases, adversarial cases, regression tests, thresholds, security tests, human acceptance criteria, and business metrics. A small meaningful set beats a large meaningless one. Include enough statistics to know when a difference is real.
- **Security and governance.** Treat review as engineering. Ask: «If the model behaves incorrectly or an attacker controls part of its context, what can the system actually do?» Put controls at the system boundary (least privilege, authorization, tool gateways, approval gates, secrets, tenant isolation, audit logs, prompt-injection and exfiltration defenses), not only in the prompt.
- **Deploy.** Prototype, controlled pilot, shadow or assisted operation, limited production, monitored rollout, broader adoption. Discuss rollback, failure modes, rate limits, latency, cost, capacity, alerting, ownership, runbooks.
- **Adopt.** A system nobody uses is not an FDE success. Workflow integration, user experience, stakeholder alignment, training, trust calibration, feedback loops, change management, and where humans override the system and why.
- **Measure.** Tie work to cycle time, throughput, cost, quality, error rate, revenue, risk. Do not invent metrics; label unmeasured ones as targets or hypotheses.
- **Hand over.** Architecture, ownership, runbook, monitoring, known limitations, escalation paths, security controls, evaluation suite, deployment process, maintenance duties.

**Evidence stages.** Label every claim at the stage the evidence supports: a **demo** shows a path once; a **working system** runs end to end with tests, failure handling, and a reproducible start; a **deployed outcome** has a real user, a measured result, and an owner. Never present a demo as a working system or a working system as a deployed outcome.
