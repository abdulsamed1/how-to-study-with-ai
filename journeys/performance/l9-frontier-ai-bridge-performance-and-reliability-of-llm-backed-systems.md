---
purpose: Contains one part of the performance and traffic-spike study map.
read_when: When diagnosing or practising the named performance concern.
depends_on:
  - ../../workspace/mission.md
  - ../../workspace/resources.md
---

# L9 — Frontier-AI Bridge: Performance and Reliability of LLM-Backed Systems



## Target

Apply the diagnostic skill of L0-L8 to systems whose slow, costly, rate-limited, nondeterministic dependency is a model call. This is the level that connects this journey to the Frontier Deployed Engineer mission in `../../AGENTS.md`.

## Why this level exists

L0-L8 are model-agnostic. A deployed agent adds a dependency with unusual properties: long and variable latency, a provider-side rate limit, a cost that grows with input and output size, and output that can be wrong even when the call succeeds. The same mechanisms apply (queueing, pool exhaustion, retry amplification, bottleneck migration), but a few new questions appear.

## Learn

### 1. The model call as a downstream dependency

- Tail latency of generation calls; time to first token versus total time when streaming is available.
- Provider rate limits and the error responses they return; timeouts sized to a latency budget, not to a guess.
- Cost as a capacity dimension: requests per second is not the only load measure; tokens per request and tokens per second matter.

### 2. Retries, side effects, and idempotency

- Retrying a pure model call is cheap in correctness terms but expensive in cost and load. Retrying a step that already triggered a tool with side effects (sending, writing, paying) is a correctness problem: apply the idempotency reasoning from L4.
- Capped exponential backoff with jitter, a retry budget, and honoring any retry guidance the provider returns. Retry storms are amplified when many workers back off in sync.

### 3. Concurrency and work shaping

- Your own pool or worker limit versus the provider's limit: which one binds first? Raising concurrency can lower throughput once the provider limit binds (compare Lab 3 and Lab 6).
- Work that does not need an immediate answer (batch classification, document processing) is a load-leveling candidate (L5). Interactive work needs bounded waiting and graceful degradation.

### 4. Context growth as unbounded state

- A conversation history or retrieved context that grows without a bound raises latency and cost per call and eventually fails. Treat it like the unbounded cache in L2-B: set a bound and a compaction or retrieval policy.

### 5. Trade-offs that need evaluation, not intuition

- Cheaper or faster model, shorter context, fewer tool calls, a cache, or a non-AI fallback each change quality as well as latency and cost. No such change ships without re-running the evaluation set from the [FDE delivery loop](../../teaching/delivery-loop.md).
- Graceful degradation order: smaller model, then deterministic path, then human review, chosen by business criticality.

### 6. Observability for LLM calls

Record per call: workflow step, model identifier, input and output size, latency, retry count, outcome, estimated cost, and a trace id that ties it to the request. Without these fields the L1 diagnostic path cannot run.

Provider limits, error codes, parameters, and pricing change; verify them using the [source policy](../../governance/source-policy.md) before teaching any specific value.

## Practice

> A pipeline processes 5,000 documents per night with an agent. After the team raised worker concurrency 4×, throughput fell, a large share of calls returned rate-limit errors, and the nightly cost rose by about 60%.

Write: (1) the measurements you would pull first; (2) two competing mechanisms; (3) the smallest intervention for each; (4) how you would show, with the evaluation set, that quality did not drop; (5) what you would add so the next change is caught earlier.

## Exit criteria

I can explain why more concurrency can reduce throughput once a provider limit binds.
I can state which retries are safe in an agent workflow and which are not, and why.
I can name the per-call fields I need in a trace to diagnose latency, cost, and failure.
I do not change a model, context size, or retry policy without an evaluation check.

## Source path

- Current official provider documentation on rate limits, errors, streaming, and timeouts (verify and date it).
- *Understanding Distributed Systems* (S27), Vitillo, Ch. 27 [TOC] — Downstream Resiliency.
- *Foundations of Scalable Systems* (S28), Gorton, Ch. 5 [TOC] — pools, queues, utilization.
- Anthropic Engineering, "A postmortem of three recent issues" (Sept 2025): why quality evals on production systems matter (re-open before teaching).

---
