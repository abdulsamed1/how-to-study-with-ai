---
purpose: Contains one part of the performance and traffic-spike study map.
read_when: When diagnosing or practising the named performance concern.
depends_on:
  - ../../workspace/mission.md
  - ../../workspace/resources.md
---

# What Not to Memorize



This journey deliberately avoids turning these technologies into default answers:

| Technology / pattern | Do not memorize as | Learn instead |
|---|---|---|
| Load balancer | "Traffic spike solution" | A traffic-distribution and health-management mechanism |
| Horizontal scaling | "More users = more servers" | Capacity replication for a diagnosed bottleneck |
| Redis / cache | "Latency is high = add Redis" | Read-path optimization with consistency/failure trade-offs |
| Queue | "High traffic = Kafka/RabbitMQ/SQS" | Load leveling when work can be asynchronous |
| Rate limiting | "Protect everything with 429" | Quota-based traffic control with explicit policy |
| Load shedding | "Return 503 when busy" | Local overload protection and admission control |
| Retry | "Retry transient errors" | Bounded, backoff-aware, idempotency-aware recovery |
| Circuit breaker | "Always install it" | Downstream failure isolation |
| Kubernetes autoscaling | "Scale on CPU" | Capacity control tied to the actual workload/resource |
| Index | "Indexes always make queries fast" | Query-plan-driven data-access optimization |

---
