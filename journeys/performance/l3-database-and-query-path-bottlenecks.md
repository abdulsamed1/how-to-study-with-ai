---
purpose: Contains one part of the performance and traffic-spike study map.
read_when: When diagnosing or practising the named performance concern.
depends_on:
  - ../../workspace/mission.md
  - ../../workspace/resources.md
---

# L3 — Database and Query-Path Bottlenecks



## Target

Become strong at the most common class of performance failures in request/response systems: the application is waiting on the data path.

## Learn

### 1. Count database work before optimizing hardware

Be able to ask:

- How many queries does one request generate?
- How much data is read?
- How many round trips occur?
- How long does each query take?
- Are queries repeated unnecessarily?
- Is the database waiting on CPU, I/O, locks, connections, or something else?

### 2. N+1 query pattern

Use this concrete mechanism from the supplied article material:

```text
Get N orders
   ↓
Loop through orders
   ↓
Query customer for each order
   ↓
N additional round trips
```

The important skill is not memorizing the label "N+1". It is recognizing **repeated remote work inside a loop** and checking whether a set-based operation, join, batching, or another access pattern is appropriate.

### 3. Indexing and query plans

Learn to investigate:

- whether a query can use an appropriate index;
- whether the database is scanning far more data than necessary;
- whether the query shape matches available indexes;
- whether the query plan explains the observed latency;
- whether an index improves the actual workload rather than merely existing.

Do not replace query-plan evidence with a simplistic statement such as "indexes make everything O(log N)". The study target is **real query behavior**.

### 4. Connection pools

A database connection is a bounded resource.

Understand:

```text
Application concurrency
        ↓
Connection pool
   ┌────┴────┐
available  waiting
              ↓
           timeout
```

A database can become the bottleneck even after the application tier is scaled out.

### 5. Locks and contention

Learn enough PostgreSQL/relational behavior to investigate:

- blocked queries;
- lock contention;
- long-running transactions;
- concurrency-sensitive code paths;
- connection exhaustion caused by waiting work.

### 6. Read replicas and caching — only after the read path is understood

Caching is an optimization, not a substitute for diagnosis.

Before using it, establish:

- the data is read-heavy enough;
- the same data is requested repeatedly;
- stale data is acceptable to the required degree;
- invalidation/expiration is manageable;
- a cache failure will not turn into an origin overload event.

Vitillo explicitly notes that caching introduces consistency and operational issues, and that a cache failure can expose the origin to a sudden surge of traffic. The origin therefore still needs protection.

## Practice

Scenario:

> API instances scale from 5 → 50. P95 latency improves briefly. Then database CPU reaches 100%, database connections are exhausted, and API latency becomes worse than before.

Diagnose the mechanism and list the **first database-side measurements** you would need before considering more API instances.

## Exit criteria

I can analyze a slow endpoint from:

`request → query count → query latency → query plan → connection wait → locks/contention → data-access redesign`

before suggesting database scaling.

## Source path

- Supplied article material — N+1 query and performance-engineering examples.
- *Foundations of Scalable Systems* (S28), Ch. 1 (read), Ch. 2 [TOC] — optimization, database bottlenecks, caching, and service/database interaction.
- *Understanding Distributed Systems* (S27), Ch. 19 [TOC] — Data Storage; Ch. 20 [TOC] — Caching.

---
