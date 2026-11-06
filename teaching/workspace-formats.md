---
purpose: Defines one teaching procedure or workspace format.
read_when: When the procedure named in the routing table is required.
depends_on:
  - ../governance/source-policy.md
  - ../governance/evidence-policy.md
---

# P§1. Workspace layout and file formats


## P§1. Workspace layout and file formats

    ../workspace/mission.md                      why the user is learning this; one screen at most
    ../workspace/evidence.md                     supported by evidence / needs learning / must not be claimed
    ../workspace/resources.md                    verified references / references to verify / coverage gaps
    GLOSSARY.md                     one-line definitions; every lesson uses these terms
    casebook/INDEX.md               concept -> cases -> transferable pattern
    casebook/<concept>.md           researched real failures for one concept
    learning-records/NNNN-slug.md   evidence of understanding
    lessons/NNNN-slug.html          one short lesson each (modes B and C: Markdown in the reply)
    reference/*.html                cheat sheets, sequence diagrams, checklists
    assets/                         shared stylesheet and reusable components

Create directories lazily, when the first file for them exists. In modes B and C these files exist only as uploads or as the user's notes; state lives as described in `../AGENTS.md` section 2 and P§6.

**../workspace/mission.md**

    # Mission: <topic>
    ## Why              1-3 concrete sentences: the real-world outcome, not "to understand X"
    ## Success looks like   specific, observable things the user will be able to do
    ## Constraints      time, budget, preferences
    ## Out of scope     adjacent topics deliberately not chased now

One mission per workspace. Push back on vagueness: interview before writing. Keep it under one screen. Confirm with the user before changing it, and record a change as a learning record. A stale mission steers every later session wrongly.

**../workspace/resources.md**

The section contract lives in the file itself: `../workspace/resources.md` opens with `## How to use this file`, defining the three sections (Verified references / References to verify / Coverage gaps) and the entry rules for each. Keep the template operative there instead of a copy in this file.

Rules: annotate every entry; surface gaps explicitly; prune sources that prove shallow or wrong; record if the user opted out of communities. Apply [source policy](../governance/source-policy.md).

**GLOSSARY.md**

    **Term**:
    One or two sentence definition of what it IS, using other glossary terms.
    _Avoid_: alias 1, alias 2

Rules: add a term only when the user can use it correctly (compressing a concept into a definition is itself evidence of understanding); be opinionated about the one preferred word; flag loose usage in the wider field; update in place as understanding deepens; group under subheadings once clusters appear.

**Learning record** (`learning-records/NNNN-slug.md`, numbering increments)

    # <short title of what was learned or established>
    <1-3 sentences: what, and why it changes what to teach next.>

Optional: `Status: active | superseded by LR-NNNN`; `Evidence:` how the user demonstrated it; `Implications:` what it unlocks or rules out.
Write one when: the user demonstrated non-trivial understanding; disclosed prior knowledge (record the depth claimed); a misconception was corrected (these predict later stumbling); the mission shifted. Do not write one for material merely covered, for facts already in the glossary, or as a session log. Mark contradicted records superseded; never delete them.

**../workspace/evidence.md**

    ## Supported by evidence      <claim> — <file, commit, record, or demo that proves it>
    ## Needs learning             <capability not yet demonstrated>
    ## Must not be claimed        <experience, metric, or deployment with no evidence>

The P2.1 baseline is short: one line per assessed dimension with the evidence that supports it. It is an assessment recorded in the three lists, not a separate document; an unassessed dimension is named as unassessed rather than left out.
