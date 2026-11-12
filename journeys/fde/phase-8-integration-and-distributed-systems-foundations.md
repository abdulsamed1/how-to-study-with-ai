---
purpose: Contains one part of the FDE learning journey.
read_when: When the FDE journey or the named phase is active.
depends_on:
  - ../../workspace/mission.md
  - ../../workspace/resources.md
---

# Phase 8 — Integration and distributed-systems foundations

**Goal:** Design reliable work across network, provider, broker, worker, and database boundaries. The learner must explain what each boundary guarantees, identify ambiguous outcomes, and prove that retries, duplicate delivery, crashes, and recovery do not create incorrect business effects.

**Implementation context:** Reuse the P4.7b stub provider and P4.8a contract sheet. Build tests from the P8.1 failure timeline before inspecting agent-written implementation. All external-provider behavior remains simulated unless a separately authorized live integration is explicitly in scope.

## 1. Learning method and cumulative case

Use one clearly labelled synthetic booking-integration case throughout Phase 8:

- A booking service stores a booking in its database.
- It sends a command to an external property-management system (PMS).
- The PMS may accept a command while its response is lost or delayed.
- Provider events arrive through a webhook.
- A broker carries durable work to background workers.
- Workers update local state and may publish further events.
- A reconciliation process compares local and provider state and repairs confirmed drift.

Do not present this scenario as a real production incident. It is a shared test case that lets each lesson add one reliability property without changing the business context.

### Sequence rules

1. **Problem before pattern:** begin with one failure timeline. State known facts, unknown outcomes, the violated business invariant, and the decision required.
2. **Vendor-neutral first:** explain the distributed-systems property before showing Kafka or RabbitMQ APIs. A broker feature is not a universal guarantee.
3. **Boundary-by-boundary guarantees:** distinguish provider request/response, publisher-to-broker, broker-to-consumer, consumer-to-database, and database-to-event publication. Never describe a whole workflow as exactly-once because one boundary has a guarantee.
4. **One cumulative implementation:** keep the same booking workflow and fault-injection harness. Each unit adds a test and a regression case to the shared suite.
5. **One primary broker for implementation:** choose Kafka or RabbitMQ for the runnable worker after comparing the requirements. Inspect the other broker as a contrast; do not implement every pattern twice by default.
6. **Explicit broker/version scope:** verify current official documentation before teaching a configuration or guarantee. Separate Kafka log/offset behavior from RabbitMQ queue/acknowledgement behavior.
7. **A causal handoff:** end each unit by naming the unresolved failure that the next unit addresses. Do not use a teaser that is unrelated to the mechanism just learned.
8. **Mastery by evidence:** follow the four-part lesson procedure in [lesson protocol](../../teaching/lesson-protocol.md). Each unit has one primary proof artifact; guided answers and completed videos do not count as mastery.

### Cumulative failure chain

| Unit | New failure exposed | Reliability property added | Carry-forward question |
|---|---|---|---|
| P8.1 | A remote operation may have succeeded even though its response was lost; messages can be lost or redelivered at different boundaries | Model partial failure and classify delivery semantics per boundary | How do we stop a repeated request or delivery from applying the business effect twice? |
| P8.2 | The same logical operation arrives more than once, including concurrently | Idempotency and deduplication | Once duplicate effects are controlled, how do we retry transient failures without amplifying load? |
| P8.3 | Retries synchronize, multiply across layers, or continue past the useful deadline | Bounded retry budget, deadline, backoff, and jitter | What if the external provider initiates delivery and sends the same event again? |
| P8.4 | A webhook is duplicated, delayed, malformed, replayed, or delivered out of order | Authenticated, durable, idempotent webhook receipt and deliberate acknowledgement | How do we process accepted work asynchronously and recover a worker that fails mid-message? |
| P8.5 | A worker crashes, a message is repeatedly unprocessable, or a queue/log accumulates work | Acknowledgement/offset discipline, bounded redelivery, poison-message isolation, and a DLQ strategy | How do we prevent a database commit and event publication from diverging? |
| P8.6 | A database update succeeds but publishing its event fails, or a multi-service workflow only partly completes | Transactional outbox and explicit saga compensation where required | How do we detect and repair drift after missed events, retries, or partial completion? |
| P8.7 | Local and provider state disagree; a missed event or bad deployment requires safe reprocessing | Synchronization, replay, reconciliation, and idempotent repair | Can we now demonstrate recovery of the whole workflow from recorded evidence? |

## 2. Lesson units

- **P8.1 — Partial failure, ambiguous outcomes, and delivery semantics** — **Priority:** important. **Depends on:** P4.5, P6.1–P6.5. A timeout does not prove that the remote side effect did not occur. Introduce at-most-once, at-least-once, and exactly-once as boundary-specific delivery/processing claims, not end-to-end promises. Separate message delivery from business-effect execution. **Proof:** a failure timeline for a request that times out after the remote write; mark what each participant knows, what remains ambiguous, and the guarantee at each boundary. **Sources:** S26 ch. 4 (read: inter-process failure modes), S29 ch. 2 (read: delivery semantics and idempotency), S64–S66, S72.

- **P8.2 — Idempotency and deduplication** — **Priority:** must-have. **Depends on:** P6.5, P8.1. Define the logical operation key, duplicate scope, retention, and response behavior. For a database-backed consumer, record the message/operation key and apply the corresponding business-state change in the same database transaction. A local inbox row does not make an external side effect atomic; use provider idempotency where supported and reconciliation where the outcome remains ambiguous. **Owned-system lab:** inspect Eagles' lead-status transition and Meta `leadgen_id` duplicate paths; identify their operation keys and retention assumptions. **Proof:** repeat one operation sequentially and concurrently and show that it cannot create a second business effect; test the transaction/crash boundary. **Sources:** S29 ch. 2, S64, S65, S19 ch. 8 and 13 [TOC], S27 ch. 5 [TOC].

- **P8.3 — Retry budgets, deadlines, backoff, and jitter** — **Priority:** must-have. **Depends on:** P4.5, P8.1–P8.2. P4.5 owns the provider-specific classification of individual HTTP outcomes. This unit owns workload-level retry safety: transient versus permanent failure, maximum attempts, elapsed-time budget, deadline, capped exponential backoff, jitter, and retry amplification across layers. Retry side-effecting operations only when their idempotency requirements are understood. Prefer one deliberate retry layer; do not retry forever or immediately requeue in a hot loop. Honour a provider-supplied retry delay when its contract requires it. **Proof:** a bounded policy tested against 429-with-`Retry-After`, transient 5xx, timeout-after-write, and a permanent failure; show attempts and elapsed time remain within the declared budget. **Sources:** S25, F10, S29 ch. 16, S10, S66, S19 ch. 9 [TOC], S27 ch. 27 [TOC].

- **P8.4 — Webhook receiver and sender contracts** — **Priority:** must-have. **Depends on:** P4.2–P4.6, P4.8a, P6.5, P8.1–P8.3. Verify the provider's signature over the required bytes, validate event type and payload, apply replay/duplicate protection, persist receipt, enqueue durable work, and acknowledge according to the provider's response contract. Treat duplicate and out-of-order delivery as normal cases to design for. Do not copy one provider's headers, signature rules, timeout, or redelivery behavior to another provider. **Owned-system lab:** audit Eagles' Meta webhook receiver for raw-body HMAC, timing-safe comparison, size limit, replay/deduplication, and failure response; mark each present, partial, or absent. **Proof:** locally tested flow covering invalid signature, replay, duplicate, out-of-order delivery, transient processing failure, and crash windows. Confirm the exact signature and acknowledgement rules in the current provider documentation. **Sources:** S67, S68, F11, S26 ch. 4.

- **P8.5 — Queues, workers, acknowledgements, poison messages, and dead-letter handling** — **Priority:** must-have. **Depends on:** P3.5–P3.6, P5.6, P8.2–P8.3. **Unit type:** multi-session implementation unit. First build the vendor-neutral message lifecycle: publish, receive, process, persist the effect, acknowledge/commit, crash, redelivery, and terminal failure. Then compare broker-specific behavior. For Kafka, reason about partitions, per-partition order, consumer-group offsets, commits, retained-log replay, and the application design for retry/dead-letter topics. For RabbitMQ, reason about manual acknowledgements, reject/nack/requeue, publisher confirms, prefetch, dead-letter exchanges, and quorum-queue delivery limits. Do not equate a Kafka partition with a RabbitMQ queue, a consumer offset with a consumer acknowledgement, or publisher confirms with consumer acknowledgements. **Poison-message path:** classify permanent failures, stop unbounded redelivery, retain the failed payload plus diagnostic metadata, alert an operator, and define an audited repair/replay path. A DLQ is an operational workflow, not a place to forget messages. RabbitMQ dead-letter guarantees depend on queue type and configuration: current quorum-queue documentation describes at-most-once as the default and at-least-once dead-lettering as an explicitly configured option with limitations. **Proof:** a worker that restarts without duplicating business effects; transient failures remain bounded; a poison message reaches a terminal dead-letter path; healthy work continues; required per-entity ordering is tested. **Sources:** S19 ch. 12 (read: offsets, per-partition order, replay), S26, S72, S73.

- **P8.6 — Dual writes, transactional outbox, saga, and compensation** — **Priority:** must-have. **Depends on:** P6.4, P8.1–P8.5. **Unit type:** multi-session implementation unit. Distinguish the database/broker dual-write problem from a multi-service business workflow. The outbox stores the business change and an event record in one local database transaction; a relay publishes the event and may publish it more than once, so consumers still need idempotency. A saga coordinates local transactions across services; compensation is a new business action, not a rollback of history. **Proof:** implement a transactional outbox in Python and PostgreSQL; crash the relay between database commit and publish, restart it, and show the event is eventually published while consumers deduplicate it. Then model one multi-step booking workflow and identify the compensating action and its limits for each step that cannot be atomically rolled back. **Sources:** S19 ch. 8 (read: distributed transaction limits), ch. 13 [TOC], S26, S27 ch. 6–13 [TOC range], S38 ch. 11–12 [TOC].

- **P8.7 — Synchronization, event replay, and reconciliation** — **Priority:** must-have. **Depends on:** P4.8a, P6.5, P8.2–P8.6. Define the source of truth, full/delta sync, cursors or watermarks, drift categories, replay scope, and repair rules. Distinguish replaying records from a retained Kafka log using offsets from redriving RabbitMQ dead-lettered or archived messages; these are not interchangeable broker operations and both require duplicate-safe processing. State retention limits and the exact set of events eligible for replay. **Proof:** a reconciliation report that classifies missing, duplicate, stale, and conflicting records, plus a replay/repair test that fixes a seeded discrepancy without creating a second business effect. **Sources:** S19 ch. 12 (read: consumer offsets, per-partition order, replay), ch. 13 [TOC], S26, S27 ch. 10–11 [TOC], S72–S73.

## 3. Boundaries with adjacent phases

- **P4.5** owns provider HTTP outcome classification. P8.3 owns the retry budget and workload-level behavior.
- **P6.5** owns duplicate/stale event state transitions. P8.2 owns operation keys, durable deduplication, and retention.
- **P8.5** owns message lifecycle, worker acknowledgement/offset decisions, poison-message handling, DLQ strategy, and local consumer intake controls such as prefetch where applicable.
- **P9.3–P9.5** own production telemetry, SLI/SLOs, and incident response. P8.5 produces the signals that those units later use.
- **P9.6** owns measured capacity and performance diagnosis. Queue growth and consumer lag are evidence to interpret, not automatic proof that adding consumers is safe.
- **P9.7** owns system-level degradation and recovery controls such as circuit breakers, bulkheads, and runbooks. Do not turn them into mandatory additions to every retry lesson.

## 4. Completion standard

Phase 8 is complete when the cumulative booking workflow has a reviewed failure model and tests for ambiguous provider outcomes, duplicate operations, bounded retries, webhook replay, worker redelivery, poison-message isolation, database/broker dual writes, and reconciliation repair. The evidence must show the actual behavior of the chosen implementation and identify broker/provider-specific limits. A design note, video, mock, or successful happy-path run alone does not close the phase.
