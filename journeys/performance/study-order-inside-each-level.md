---
purpose: Contains one part of the performance and traffic-spike study map.
read_when: When diagnosing or practising the named performance concern.
depends_on:
  - ../../workspace/mission.md
  - ../../workspace/resources.md
---

# Study Order Inside Each Level



For each level, use the same learning rhythm:

### Step 1 — Read the source

Read only the cited sections first. Do not read an entire distributed-systems book simply because one incident requires one concept.

### Step 2 — Rebuild the mechanism

Draw the request/data flow and mark:

- where work is created;
- where state lives;
- where waiting occurs;
- what resource is bounded;
- what happens under concurrency;
- what happens when a dependency fails.

### Step 3 — Break it

Run one controlled scenario from the labs or a project-specific equivalent.

### Step 4 — Observe it

Use the telemetry needed to test the hypothesis.

### Step 5 — Repair it

Change one variable.

### Step 6 — Compare

Record before/after measurements.

### Step 7 — Explain it

Answer the production scenario in your own words, without naming a tool until the mechanism requires it.

### Step 8 — Record it

Consolidate as in `../../AGENTS.md` section 5, step 10, then re-ask the same idea in a changed scenario after a gap of days.

---
