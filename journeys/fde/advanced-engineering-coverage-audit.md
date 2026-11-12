---
purpose: Records the source-grounded coverage audit and the expanded engineering map for Phases 5–10.
read_when: When reviewing curriculum completeness, source coverage, or new advanced-engineering units.
depends_on:
  - ../../workspace/mission.md
  - ../../workspace/resources.md
  - journey-overview.md
---

# Advanced engineering coverage audit — Phases 5–10

## 1. Scope and method

This audit compares the live FDE curriculum with the eight user-supplied EPUBs and the registered official documentation. It is a coverage audit, not a claim that every book or chapter has been read in full.

Evidence labels used here:

- **Passage checked:** selected passages were opened in the EPUB or official documentation during this audit; the precise scope is recorded in `../../workspace/resources-reading-status.md`.
- **TOC lead:** a topic/chapter was identified from a table of contents only. It is a reading lead, not evidence that the detailed content was reviewed.
- **Curriculum synthesis:** the mapping from source concepts to FDE units is an instructional design decision, not a quotation or claim made by the source.

The mission remains FDE: design and deliver one real, evaluated, secured, deployed, and handed-over AI-enabled system when the business problem justifies AI. The broader engineering topics below support that outcome; they do not turn every advanced distributed-systems specialty into a mandatory prerequisite.

## 2. Coverage crosswalk

| Capability area | Existing coverage before audit | Coverage after audit | Main source support |
|---|---|---|---|
| Relational data and SQL | P5.1–P5.7 | Retained; added model choice, storage-engine/WAL concepts, and table partitioning in P5.8–P5.10 | S19 ch. 3–4; F6; S76 |
| Transactions and concurrency | P6.1–P6.6 | Retained; added serializable conflict control and write-skew proof in P6.7 | S19; S27; F6 |
| Software architecture | P7.1–P7.8 | Retained; added domain modeling, bounded contexts, aggregate boundaries, component decomposition, data ownership, and service granularity in P7.9–P7.10 | S20; S26; S38 |
| Distributed-systems foundations | Mostly surfaced through P8.1 and P10.6 | Added system models, failure detection, distributed time/causality, replication/consistency, partitioning/sharding, consensus/leader election, leases/fencing in P8.0a–P8.0e | S19 ch. 6–10; S27 ch. 2–11; S29 |
| Messaging and event-driven systems | P8.1–P8.7 | Retained and clarified; added optional CQRS/Event Sourcing, CDC, stream processing, and distributed batch in P8.8–P8.11 | S19 ch. 3, 5, 11–12; S26; S29; S75 |
| Production infrastructure and resilience | P9.1–P9.7 | Retained; added service discovery/load balancing, caching/read scaling, failure domains/fault isolation, and controlled chaos validation in P9.8–P9.11 | S26; S27; S28; S29; S25; S76 |
| System design application | P10.1–P10.8 | Retained; now consumes the new architecture/distribution prerequisites; added optional analytical data architecture in P10.9 | S19; S20; S28; S38 |

## 3. Book-to-curriculum map

| Uploaded book | Relevant concepts surfaced in the reviewed material | Curriculum ownership |
|---|---|---|
| *Designing Data-Intensive Applications*, 2nd ed. — Martin Kleppmann and Chris Riccomini | Data models; B-tree/LSM storage; dataflow; partial failures and clocks; replication/consistency; consensus; batch; streams/CDC | P5.8–P5.9, P6.7, P8.0b–P8.0e, P8.6–P8.11, P10.9 |
| *Understanding Distributed Systems*, 2nd ed. — Roberto Vitillo | Network flow/congestion control; discovery; system models; failure detection; clocks; leader election; replication/consistency; coordination avoidance; messaging and fault isolation | P8.0a–P8.0e, P9.8, P9.10 |
| *Foundations of Scalable Systems* — Ian Gorton | Scalable data/system architecture and caching; additional chapter references remain TOC-only unless recorded otherwise | P5.8, P8.0d, P9.9, P10.6; use TOC-only pointers cautiously |
| *Fundamentals of Software Architecture*, 2nd ed. — Mark Richards and Neal Ford | Coupling, modularity, architecture partitioning, service granularity, event/message distinction, caching/consistency, orchestration, bounded contexts, CQRS and hexagonal architecture | P7.1, P7.5a, P7.9–P7.10, P8.8, P9.9 |
| *Software Architecture: The Hard Parts* — Neal Ford, Mark Richards, Pramod Sadalage, and Zhamak Dehghani | Dynamic coupling/architecture quantum; decomposition; operational data ownership; service granularity; orchestration/choreography; saga state machines; strict/loose contracts; trade-off analysis | P7.5a–P7.6, P7.10, P8.6, P8.8, P10.9 |
| *Building Microservices*, 2nd ed. — Sam Newman | Bounded contexts/aggregates; communication and discovery; migration/decomposition; sagas; resilience/chaos; scaling and caching | P7.9–P7.10, P8.4–P8.6, P9.8–P9.11 |
| *Designing Distributed Systems*, 2nd ed. — Brendan Burns | Replicated/load-balanced services; consistent hashing/hot shards; scatter/gather; leader election/locks; work queues; pub/sub; join/barrier/reduce; thundering herd | P8.0d–P8.0e, P8.5, P8.11, P9.8–P9.10 |
| *A Common-Sense Guide to AI Engineering* — Jay Wengrow | Evals, RAG, agents, safe tools, guardrails, monitoring, and error handling; this is an AI-engineering source, not a foundation for Phases 5–10 | Primarily Phases 11–16; not used to justify the backend/distributed-systems additions |

**Reading boundary:** the map above is a crosswalk, not a statement that all referenced chapters were read. See the source register and reading-status table. Chapters explicitly marked `[TOC]` remain leads until their exact passages are opened.

## 4. Core path versus specialist depth

The standard FDE core now includes:
- Database model/storage literacy needed to justify data and durability decisions.
- Transactional correctness and concurrency control.
- Domain modeling, component boundaries, and data ownership.
- Distributed failure/time/consistency/replication fundamentals.
- Reliable messaging and distributed workflow patterns.
- Production discovery, caching, load balancing, fault isolation, and recovery.
- Integrated system design with explicit trade-offs and evidence.

The following remain conditional specializations, not universal prerequisites:
- Implementing Raft or another consensus algorithm from scratch.
- Deep CRDT design/implementation and multi-region active-active databases.
- Kafka protocol internals or operating a large multi-cluster Kafka estate.
- Running a full Flink/Spark production platform.
- Distributed scheduler internals, work stealing, and advanced batch frameworks.
- Full service-mesh/Kubernetes platform engineering.
- Data Mesh organizational transformation and lakehouse platform operations.

A specialist unit becomes active only when the capstone, a verified capability gap, or a named target role requires it. A useful unit can be deferred without blocking the FDE core.

## 5. Boundary and anti-duplication rules

- P5 owns storage/data-model and database-engine reasoning; P6 owns transaction-local correctness and concurrency.
- P7 owns domain/component boundaries and data ownership; P10 reuses those decisions in a concrete design brief.
- P8.0 owns distributed-systems mechanisms; P8.1–P8.7 apply them to delivery, messaging, and workflows.
- P9 owns operating/diagnosing and validating production infrastructure; P10.5–P10.6 own choosing and justifying mechanisms against a workload.
- P8.8–P8.11 and P10.9 are conditional paths; they do not silently become requirements for every capstone.
- Preserve existing unit IDs and learning records. New units add explicit prerequisites and proof; they do not imply that any learner has completed them.

## 6. Known source limitations

- Kafka documentation S72 was located, but direct full-page retrieval failed during the 2026-11-12 audit. Verify the exact deployed Kafka version and official pages before teaching client/configuration details.
- *Foundations of Scalable Systems* remains a useful coverage lead, but the relevant newly mapped chapters are marked TOC-only until read.
- The 2026 Jay Wengrow book has verified bibliographic information; its content was not used as evidence for Phases 5–10.
- Official PostgreSQL 18 documentation is version-specific. Re-check the deployed database major version before using its operational instructions.
