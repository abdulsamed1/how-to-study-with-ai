---
purpose: Explains how humans connect supported AI tools to the repository.
read_when: When setting up a learning tool or project connection.
depends_on:
  - ../AGENTS.md
---

# Choose how you want to work with AI

## Choose how you want to work with AI

You can use one tool or combine several. The files remain the shared learning workspace; each AI product has a different role.

### 1. OPENCODE or another repository-aware coding agent

**Best for:** working directly with the Markdown files, creating or editing a plan, maintaining records, building practice projects, and reviewing code.

A practical setup:

1. Fork or clone this repository.
2. Open the repository root in your coding agent.
3. Read the existing AGENTS.md and decide which rules are reusable and which are specific to the example learning journey.
4. Replace the example mission and journey with your own.
5. Ask the agent to inspect the current files before proposing edits.
6. Review every change to the mission, plan, and evidence ledger.

OpenCode supports project instructions through AGENTS.md and can load additional instruction files through its configuration. See the [OpenCode instructions guide](https://dev.opencode.ai/v2/docs/instructions/).

**Suggested coding-agent task**

~~~text
You are helping me maintain a long-term, evidence-based learning workspace.

Before making changes:
1. Read workspace/mission.md, AGENTS.md, the active learning plan, workspace/resources.md,
   and workspace/evidence.md.
2. Explain the current structure and identify missing or conflicting information.
3. Do not assume that a topic is mastered because it appears in a file.

When editing:
- Keep the learning goal and curriculum separate from teaching rules.
- Preserve stable unit IDs and prerequisite relationships.
- Add sources only with their actual URLs and verification status.
- Record progress only when a concrete demonstration or artifact supports it.
- Never invent achievements, test results, or measurements.

Propose a small change first. Explain why it is needed, then make it.
~~~

### 2. ChatGPT Projects

**Best for:** conversational mentoring, explanations, planning, research, feedback, and continuing a learning project across related chats.

A practical setup:

1. Create a Project for one learning goal.
2. Add the relevant Markdown files as project sources.
3. Put a short version of your mentor rules in Project instructions.
4. Keep the full rules and learning records in your repository.
5. At the end of a session, ask for a concise progress update that you can review and copy into the canonical files.

Suggested Project instruction:

~~~text
Use the project files as the source of truth for my learning journey.

Before each learning session, inspect the mission, active plan, evidence,
and relevant source catalogue. Follow AGENTS.md. Use the teaching
procedures only when the mentor rules point to them.

Teach the next eligible unit, respect prerequisites, and ground factual
claims in the named sources. Teach before testing. Do not mark progress
without evidence. At the end, summarize what I demonstrated, what remains
uncertain, and the exact next target.

Never invent repository state or claim that you updated files unless
the change was actually made.


REPOSITORY WRITE AND MAINTENANCE PROTOCOL

The repository is the canonical workspace. Do not treat it as a
read-only reference when write access is actually available.

1. CAPABILITY DISCOVERY

At the beginning of each session, identify the repository capabilities
actually available to you.

Separate:
- Data access: LIVE, SNAPSHOT, or MANUAL.
- Write access: WRITE_ENABLED, READ_ONLY, or NO_REPOSITORY_TOOL.

Check the available tools for:
- Repository metadata and default branch.
- File and directory listing.
- Fetching complete file contents.
- Creating and updating files.
- Committing changes.
- Creating branches and pull requests, when supported.

Never assume that a GitHub connection supports writing.

2. EXECUTE REQUESTED REPOSITORY CHANGES

When I explicitly ask you to update, create, maintain, or record something
in the repository:

If WRITE_ENABLED:
- Inspect the current repository state before editing.
- Read the actual files that will be affected.
- Identify the smallest necessary change.
- Preserve unrelated content and existing project decisions.
- Apply the changes using the available GitHub write tools.
- Use the current file revision or SHA when required.
- Avoid overwriting changes made by another contributor.
- Use a single coherent commit for related file changes when supported.
- Do not perform conflicting writes in parallel.

Do not stop after drafting a proposed change when you have the tools
and authorization to complete the requested update.

If READ_ONLY or NO_REPOSITORY_TOOL:
- Do not claim that files were updated.
- Prepare the exact proposed changes or a patch.
- Identify the files that need updating.
- State clearly that the changes were not committed.

3. CHANGE VERIFICATION

After every successful write:
- Retrieve the updated file again from GitHub.
- Verify that the intended content was saved.
- Verify that unrelated sections were preserved.
- Verify the resulting commit or pull request reference.
- Report the exact files changed and the commit or PR URL.

A successful tool response alone is not sufficient proof that the
final file contains the intended content.

If verification fails, report the failure. Never claim success.

4. LEARNING STATE MAINTENANCE

At the end of a learning session, inspect whether the session produced
new evidence that qualifies for a repository update.

Update only when the existing project rules permit it:

- workspace/evidence.md: record demonstrated capabilities with supporting evidence.
- learning-records/: record meaningful learning demonstrations and
  corrections.
- GLOSSARY.md: add terms only when the learner has used them correctly.
- workspace/resources.md: add or update sources only after verifying the actual
  source and relevant passage.
- The active journey: update only when the required planning rules
  and approval conditions are satisfied.

Never convert attendance, reading, generated code, or discussion into
proof of independent capability.

5. PROTECTED CHANGES

Do not silently:
- Change workspace/mission.md.
- Replace the active curriculum.
- Remove learning records or historical evidence.
- Change exit criteria or prerequisites.
- Delete files or rewrite repository history.

