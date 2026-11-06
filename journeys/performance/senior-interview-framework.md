---
purpose: Contains one part of the performance and traffic-spike study map.
read_when: When diagnosing or practising the named performance concern.
depends_on:
  - ../../workspace/mission.md
  - ../../workspace/resources.md
---

# Senior Interview Framework



When asked:

> **"Traffic suddenly increases 20×. What would you do?"**

Do **not** recite:

`Load Balancer → Kubernetes → Redis → Queue → Rate Limit`

Use a reasoning structure:

### 1. Establish the failure surface

What changed?

- traffic;
- latency;
- throughput;
- errors;
- concurrency;
- saturation;
- dependency behavior.

### 2. Find the constraint

Which resource or dependency is limiting useful work?

### 3. Verify the mechanism

Use:

- metrics;
- logs;
- traces;
- profiles;
- database/query evidence;
- queue/pool evidence;
- deployment/change timeline.

### 4. Mitigate according to the mechanism

Examples:

- inefficient CPU path → optimize;
- DB query bottleneck → fix access path/query/index/locking issue;
- downstream slowness → bound waiting and contain retries/failure;
- burst of asynchronous work → queue/load-level where semantics permit;
- abusive/excess traffic → rate limit or shed according to policy;
- true compute capacity limit → scale;
- non-critical work → degrade gracefully.

### 5. Re-measure

Prove that:

- latency improved;
- throughput improved;
- errors reduced;
- the original bottleneck eased;
- no more dangerous bottleneck appeared elsewhere.

### 6. Prevent recurrence

After mitigation:

- identify root cause;
- add instrumentation;
- improve tests/load tests;
- add capacity limits or protection;
- improve the runbook;
- perform a postmortem when warranted.

This aligns with Vitillo's operational guidance that incident response first mitigates user impact, then investigates root cause and prevention.

### 7. Say what you have and have not done

State the mechanism you would check, then separate experience from knowledge. Sample answers (keep these in English):

- Experience: "In <project>, I saw <symptom>. I checked <evidence>, found <mechanism>, changed <one thing>, and measured <before/after>."
- Adjacent experience: "I have not run this in production. I have reproduced it in a lab with <setup>, and the measurement showed <result>."
- Unknown: "I do not know yet. The measurement that would tell us is <metric or trace>."


---
