---
purpose: Defines one teaching procedure or workspace format.
read_when: When the procedure named in the routing table is required.
depends_on:
  - ../governance/source-policy.md
  - ../governance/evidence-policy.md
---

# P§6. Setting up each tool


## P§6. Setting up each tool

Per-tool setup lives here. [modes.md](modes.md) defines the modes; this file only
says how to configure each tool.

**Python toolchain (required before P2.1; verify installed, do not assume).**

- Interpreter: Python 3.11 or newer (`python --version`).
- Environment: one virtual environment per project (`python -m venv .venv` or `uv venv`); never install into the system interpreter.
- Dependencies: pinned in a lockfile (`requirements.txt` with hashes, or `uv.lock`/`poetry.lock`); reinstall from the lockfile in CI.
- Runtime validation: Pydantic v2 (`pip install pydantic`); validate at every trust boundary, not deep in domain logic.
- Static checking: mypy or pyright (`mypy --strict` or `pyright`); run in CI; treat new errors as failures.
- Tests: pytest (`pytest -q`); contract and error-path tests use a stub provider, not live calls.
- Verification before teaching P2.1: `python --version`, `pip --version`, `pytest --version`, `mypy --version` (or `pyright --version`), and `python -c "import pydantic; print(pydantic.VERSION)"` all succeed. Check the output before proceeding; do not write it to a learner-progress file.
- Scope: this toolchain serves Phases 2–17. TypeScript/Node.js tooling (F3, F5) remains the reading context for P7.7–P7.8 and the owned-system labs; it is not a second implementation track.

**Mode A — workspace**
- The workspace agent reads `../AGENTS.md` and takes extra files from the `instructions` list in `opencode.jsonc` if the user uses OpenCode. Check the current docs for both, since the syntax changes.
- Keep this file out of the always-loaded list; `../AGENTS.md` says when to open it.

**Mode B — chat with files**

*Claude Project*
- Upload the files in the P§9 manifest. Project knowledge holds the files; "Set project instructions" holds the short instruction text (the full rules are in the uploaded file):

      Follow ../AGENTS.md in the project files exactly. Use session-protocol.md only when ../AGENTS.md points to it. The active journey file is the one the user names, otherwise ask.

- Project memory is on by default and is scoped to the project; to keep it fully separate, turn off "Use account memory" on the project page. A reply can be kept by adding it to the project sources.
- A redesigned Projects experience (one conversation, parallel cloud threads) is in beta from 2026-09-17; it does not change the setup above.

*ChatGPT Project*
- Upload the files in the P§9 manifest. File limits depend on the plan; check the current limit in OpenAI's help article "Projects in ChatGPT".
- In Project settings, set Memory to Project-only, and enable the account memory settings the article lists. Memory changes can take a few hours to apply. Project memory is not used to reconstruct lesson progress; the learner names the current unit and part at session start ([modes.md](modes.md)).
- Project instructions (short, because the full rules are in the uploaded file):

      Follow ../AGENTS.md in the project files exactly. Use session-protocol.md only when ../AGENTS.md points to it. The active journey file is the one the user names, otherwise ask.

- Optional, for a reply that must persist verbatim (for example an agreed mission): the response menu offers "Add to project sources", which adds it as a project source.
- For a mission change, update the mission only after explicit learner approval. Do not ask the learner to persist lesson progress.

**Mode C — chat without files**
- The agent sees only what the user pastes. The user pastes the files in the P§9 manifest that the lesson needs, plus the selected primary sources.
- NotebookLM keeps chat history inside the notebook, but the agent does not use it as a progress database. The learner names the current unit and part when starting a new session. Generated quizzes, summaries, and audio are practice artifacts, not sources.
- Chat configuration (the same two sentences, adjusted for sources only):

      Follow ../AGENTS.md among the sources, in mode C. Answer only from the sources and cite them.

### Session continuity (modes B and C)

There is no session-export block and no synchronization of lesson status into the repository.

At the next session, the learner states the active journey, unit, and part. If that information is missing, ask once. The mentor may recommend a next unit from the declared curriculum position but must not mark completion or infer progress from memory.

Actual capstone artifacts — code, tests, ADRs, evaluation reports, deployment records, and runbooks — remain in their project locations because they are deliverables of the system being built, not learner-progress records.

State the applicable mode at session start using [teaching/modes.md](modes.md).
