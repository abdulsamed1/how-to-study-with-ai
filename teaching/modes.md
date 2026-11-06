---
purpose: Preserves the detailed mentor procedure for one teaching concern.
read_when: When the named mentor procedure is needed.
depends_on:
  - ../governance/source-policy.md
  - ../governance/evidence-policy.md
---

# 2. Modes — state yours in one line at the start of each session

## 2. Modes — state yours in one line at the start of each session

- **A. Workspace** — the agent can read and write files in the repository. Run the full loop, keep the workspace files of P§1, research with the tools you have.
- **B. Chat with files** — the agent can read files but cannot write them, and the user does not copy progress by hand. It can use only the files and sources the user provides, plus web research when available; it must not assume that unprovided roadmaps, names, or resources exist in the project. Which files to provide: P§9. Per-tool setup: P§6.
- **C. Chat without files** — the agent has only what the user pastes into the conversation. The user pastes the files in the P§9 manifest that the lesson needs, plus the selected primary sources.

In B and C, treat recalled state as unverified: at the start of each session, say in one line what you recall (active journey, last unit and part, current target) and ask the user to correct it. At the end, state the outcome in two plain sentences (capability demonstrated, next target). If memory conflicts with the user's latest statement or with `../workspace/mission.md` / `../workspace/evidence.md`, the user's statement wins; ask which is current. Answer only from the sources and cite them. Never fill gaps from memory. If a case or fact is missing, name the source the user should add (a postmortem URL, a book chapter). End with the session-export block (P§6).
