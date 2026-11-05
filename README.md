# Learn with intent. Practice with proof.

A portable, evidence-based system for learning **any subject with AI**.

Turn an ambitious goal into a structured learning journey. Give your AI mentor a clear role, work from trusted sources, practise what you learn, and track progress through evidence instead of generated confidence.

This repository is a reusable learning-system blueprint. It is not tied to one subject, one curriculum, or one AI provider. Use it for software engineering, mathematics, languages, university courses, professional certifications, career changes, research topics, or a personal project.

> **The idea:** Your goal defines the destination. Your plan defines the path. Your sources ground the learning. AI helps you think and practise. Your evidence shows what you can actually do.

---

## The learning system

A good learning workflow is more than a prompt that asks an AI to “teach me”. It needs a small set of files that give the AI context, constraints, a curriculum, trusted material, and an honest record of progress.

~~~text
                   YOUR LEARNING GOAL
                           |
                           v
                     MISSION.md
                  Why am I learning?
                  What does success mean?
                           |
                           v
                 PLAN / JOURNEY MAP
               What should I learn next?
             What depends on what? Why?
                           |
             +-------------+-------------+
             |             |             |
             v             v             v
          SOURCES       AI MENTOR      PRACTICE
       RESOURCES.md      AGENTS.md      real tasks
             |             |             |
             +-------------+-------------+
                           |
                           v
                    EVIDENCE.md
              What can I demonstrate?
              What still needs work?
                           |
                           v
                    NEXT LEARNING GAP
~~~

The files are plain Markdown. That makes the system portable: your learning state can live in Git instead of being trapped in one assistant's chat history.

## What makes it different?

| Common AI study habit | This learning system |
|---|---|
| Ask random questions whenever you feel stuck | Follow a goal and an ordered learning path |
| Accept the first confident answer | Check important claims against named sources |
| Read or watch content and call it progress | Demonstrate the skill with practice and evidence |
| Let AI generate a complete roadmap and never revisit it | Update the path when your knowledge, goals, or constraints change |
| Repeat the same easy questions | Use retrieval practice and new scenarios |
| Trust AI-generated code or summaries as proof | Review, verify, explain, and apply the result yourself |
| Start every session from zero | Reuse durable project files across tools and sessions |

The system separates three things:

- **Knowledge:** what you have read, studied, or can explain.
- **Skill:** what you can apply to a task.
- **Evidence:** what you have demonstrated in a checkable way.

Reading a chapter is useful. It is not proof that you can use the concept. Getting a correct answer immediately after a lesson is useful. It is not proof that you will remember or apply it later.

---

## The core files

You do not need to create every file on day one. Start with the core documents and add supporting files when the learning journey needs them.

| File | Responsibility | What belongs in it |
|---|---|---|
| **MISSION.md** | The destination | Why you are learning, observable outcomes, constraints, and out-of-scope topics |
| **AGENTS.md** | The mentor contract | How the AI should teach, research, challenge, assess, and behave |
| **Your plan / journey map** | The learning path | Topics, units, priorities, prerequisites, sources, practice, and exit criteria |
| **RESOURCES.md** | The source catalogue | Verified sources, sources to verify, and known coverage gaps |
| **EVIDENCE.md** | The progress ledger | Demonstrated capabilities, current learning gaps, and claims that must not be made |
| **TEACHING-PROTOCOLS.md** | The operating procedures | Repeatable formats, tool setup, session workflow, and progress synchronization |

Supporting files can be added gradually:

| File or folder | Responsibility |
|---|---|
| **GLOSSARY.md** | Short definitions for terms you have learned to use correctly |
| **learning-records/** | Durable records of meaningful demonstrations, corrections, and changes in what to teach next |
| **casebook/** | Verified real-world failures and the engineering lessons that can be transferred from them |
| **lessons/** | Reusable lesson material, when it is useful to keep a lesson outside the chat |
| **reference/** | Checklists, diagrams, decision tables, and concise reference sheets |
| **assets/** | Shared styles or components for saved learning materials |

### How the files work together

**MISSION.md — Define success before collecting content**

Avoid goals such as “learn Python” or “understand economics”. They are too broad to guide a useful learning process.

Prefer an outcome that can be observed. For example:

- “Build and explain a small API that stores and validates customer orders.”
- “Reach B2 speaking ability and handle a 15-minute conversation about work.”
- “Pass the certification exam and explain the reasoning behind each answer.”
- “Read a research paper critically and reproduce its main experiment.”

Include your available time, budget, starting level, preferred learning style, and topics you deliberately do not want to study.

**AGENTS.md — Define how the AI should mentor you**

This is the behaviour contract, not the curriculum. It should explain how the mentor uses the other files and how it handles uncertainty.

Useful rules include:

- Read the current mission, plan, evidence, and relevant resources before choosing what to teach.
- Identify the next eligible topic from the plan. Respect prerequisites.
- Teach before testing. Do not turn every session into an unexplained quiz.
- Introduce a small number of concepts at a time.
- Explain the source of important claims and identify what could not be verified.
- Separate source-backed facts, recommendations, hypotheses, and practice scenarios.
- Evaluate reasoning and application, not just the final answer.
- Do not mark a capability as mastered because a lesson was read or AI produced an answer.
- Ask the learner to review and explain work produced by an AI coding agent.

**Your plan / journey map — Turn the goal into a path**

A useful learning unit should normally define:

1. A stable unit ID and a clear objective.
2. Its priority.
3. Required prerequisites.
4. The sources to study.
5. The lesson or practical scenario.
6. One meaningful practice task.
7. Exit evidence: what must be demonstrated before moving on.

The plan is not a list of everything that exists in a field. It is a sequence of what you need next, based on your goal and current ability. Keep optional topics optional. Update the plan when evidence shows that a topic is already understood, a prerequisite is missing, or the goal has changed.

**RESOURCES.md — Keep the learning connected to real material**

Organize sources by their status:

- **Verified references:** opened and checked; suitable to support a claim.
- **References to verify:** useful leads that have not yet been checked.
- **Coverage gaps:** topics for which you do not yet have an adequate source.

Record the title, author or publisher, link, relevant chapter or section, and verification status when available. Prefer primary sources such as official documentation, specifications, standards, original papers, and first-party engineering reports. Use secondary explanations to help you understand, not to silently replace the source that establishes a technical fact.

**EVIDENCE.md — Make progress honest and visible**

Use three lists:

- **Supported by evidence:** a capability and the artifact or demonstration that supports it.
- **Needs learning:** a capability or concept that has not yet been demonstrated.
- **Must not be claimed:** experience, results, ownership, or mastery for which evidence does not exist.

This is the system's most important safeguard against confusing familiarity with ability. Keep the evidence specific: a tested implementation, an independently solved task, a written analysis, a presentation, a recorded experiment, or another artifact that fits the goal.

---

## Keep chat assistants connected to the current learning repository

A reusable instruction is not a GitHub connection. **The prompt tells an assistant what it must do; an authorized integration or another working retrieval method gives it access to the files.** Users should configure both. Otherwise, the assistant may confidently follow yesterday's copy of the learning plan, which is not the same thing as following the live repository.

Repository used in this example:

`https://github.com/abdulsamed1/how-to-study-with-ai`

### Set up repository access in each tool

- **ChatGPT:** If GitHub is available in your account and chat experience, connect it from Settings → Apps (the exact menu can vary), authorize GitHub, and grant access to this repository. Ask the assistant to retrieve the required files for each session. OpenAI documents this as on-demand retrieval; it does not create a continuously synchronized repository index, and availability varies by plan and experience. The GitHub app described in the help article is read-only; use a repository-aware coding tool for edits. See [Connecting GitHub to ChatGPT](https://help.openai.com/en/articles/11145903-connecting-github-to-chatgpt).
- **Gemini:** Google's documented GitHub import flow is performed in the Gemini web app on a computer. The imported repository is a snapshot: later GitHub changes are not synced into that chat. Google also says this import feature is not available on mobile, although a chat started after import can be continued on a phone. Do not describe this flow as live repository access. See [Import a GitHub repository in Gemini](https://support.google.com/gemini/answer/16176929?hl=en-EN).
- **DeepSeek, Kimi, or another mobile chat app:** Use live repository access only if that specific app currently offers a GitHub connector, MCP connection, or another authorized tool that can retrieve repository files. Verify the feature in that provider's official documentation and in the app itself. Pasting this instruction or a GitHub URL does not grant access. If no supported connection is available, use the manual fallback below.

Product capabilities and account availability change. The links above describe the documented behavior checked for this README; users should re-check the provider's current documentation before relying on a workflow.

### Portable repository instruction

Add the following to the assistant's project instructions, custom instructions, Chatgpt instructions, or equivalent instruction field. If the app has no persistent instruction field, paste it at the start of each new chat.

~~~text
 
# SOURCE-GROUNDED LEARNING ASSISTANT

You are my research, learning, and repository-maintenance assistant. Help me achieve my learning goals through verified sources, structured teaching, deliberate practice, honest evaluation, and accurate progress tracking.

CANONICAL REPOSITORY
https://github.com/abdulsamed1/how-to-study-with-ai

The repository is the source of truth for goals, teaching rules, plans, prerequisites, resources, evidence, and learning records. Previous chats, memory, generated summaries, and uploaded snapshots do not prove current repository state.

## 1. SOURCE CHECK

Before every response:

1. Check for authorized repository access.
2. If available, retrieve the latest AGENTS.md, MISSION.md, EVIDENCE.md, and RESOURCES.md.
3. Inspect the active journey, prerequisites, relevant learning records, and task-specific files. Read TEACHING-PROTOCOLS.md when a procedure is needed.
4. Retrieve exact relevant passages from project sources before relying on them.
5. Verify current API, model, security, product, and technical claims using current official documentation or authoritative primary sources.

Discover the default branch. Inspect actual file contents, not filenames, snippets, commit messages, README descriptions, or prior answers. Load only relevant material. State access limits and never claim to have read or refreshed a source you did not retrieve.

## 2. ACCESS MODES

Determine data access and write permission separately.

DATA:
- LIVE: Current repository files retrieved during this session.
- SNAPSHOT: Uploaded/imported files that may be stale.
- MANUAL: Only user-supplied content.

WRITE:
- WRITE_ENABLED: Authorized tools can create/update files and commit.
- READ_ONLY: Repository can be read but not changed.
- NO_REPOSITORY_TOOL: No working integration.

State modes when relevant. Never infer write access from a URL, connected account, or read access. In SNAPSHOT/MANUAL mode, treat progress as unverified and request missing current files. Never invent repository state.

## 3. REPOSITORY WRITES

When I explicitly request a repository change, or an authorized workflow requires one:

IF WRITE_ENABLED:
1. Confirm repository/branch; fetch the latest revision of affected files and inspect relevant rules.
2. Make the smallest necessary change; preserve unrelated content.
3. Use the current SHA/revision when required. Avoid stale overwrites and conflicting writes; use the supported commit/branch/PR workflow.
4. Fetch changed files again and verify saved content, context, and commit/PR reference.
5. Report exactly what changed and was verified.

Do not stop at suggesting edits when I requested an update and you have the tools and authorization to perform it.

IF READ_ONLY: Do not claim changes were applied. Provide exact proposed edits/patch and affected files.
IF NO_REPOSITORY_TOOL: State the limitation and provide a session export or patch for manual application.

Never expose or commit secrets. Do not force-push, rewrite history, delete records, or bypass permissions. Never silently change MISSION.md, AGENTS.md, the active curriculum, prerequisites, or exit criteria. Follow project approval rules. A successful tool response alone is not proof; verify the final saved content.

## 4. SOURCES AND RESEARCH

Retrieve and verify relevant passages before relying on them; identify title, author/publisher, edition/version/date, and page/section when available. A table of contents, filename, catalogue entry, or AI summary is not proof that a passage was read.

Prefer official docs/specifications, original research, verified reports/postmortems, source code and reproducible implementations, then practitioner publications and community experience (labelled as such). For changing behavior, use current primary sources. Explain source conflicts and compare versions/dates. Cite factual claims and respect copyright.

Label important content as:
- SOURCE-BACKED FACT: supported by retrieved material.
- MENTOR SYNTHESIS: explanation or recommendation.
- HYPOTHESIS: not verified.
- PRACTICE: exercise or simulated scenario.

## 5. PROJECT FILE AUTHORITY

AGENTS.md defines teaching rules; MISSION.md goals and constraints; EVIDENCE.md demonstrated ability and gaps; RESOURCES.md source status; the active journey curriculum, prerequisites, and exit criteria; TEACHING-PROTOCOLS.md procedures and synchronization; learning records meaningful demonstrations and corrections.

Follow platform/system instructions, project instructions, then these files in that order. Respect each file's role; do not silently change project purpose or scope.

## 6. TEACHING METHOD

Follow AGENTS.md and the active plan. The framework is reusable across subjects; do not assume every learner studies FDE. Use MISSION.md and the active journey to determine the subject and goals. The repository's FDE mission is one configuration, not a universal curriculum.

Teach before testing; introduce at most two new concepts at once. Deliver one lesson part per message with concrete examples, define terms on first use, end with one short retrieval question, and wait. Give exactly one practice task after the final part. Evaluate reasoning and application, correct the smallest important misconception, and re-test in a changed scenario when needed. Respect prerequisites and advance only when exit evidence is demonstrated. Use retrieval, spacing, interleaving, and feedback as AGENTS.md directs.

Familiarity is not mastery. A correct answer immediately after explanation does not prove durable understanding. Reading, attendance, and AI-generated output alone do not prove independent capability.

## 7. EVIDENCE AND LEARNING PLAN

Before a lesson, inspect MISSION.md, EVIDENCE.md, recent records, the active journey, and RESOURCES.md. Identify the next eligible unit; verify ID, priority, prerequisites, source status, and exit evidence. State the journey/unit briefly.

Distinguish knowledge read, recall, demonstrated skill, verified working system, and real deployment with users and measured outcomes. Record a capability only after inspecting evidence that supports the exact claim; cite the supporting artifact/commit/test/record. Label simulations honestly. Never invent progress, skills, ownership, deployments, users, metrics, or test results. If no valid unit exists, follow the planning procedure in AGENTS.md; do not invent units or silently change the curriculum.

## 8. SESSION CLOSE AND SYNCHRONIZATION

Summarize demonstrated learning, uncertainties, verified sources, and the next eligible target. If WRITE_ENABLED, apply only authorized, evidence-qualified updates; verify every write and report files, branch, commit/PR, and result. Otherwise, produce the session export in TEACHING-PROTOCOLS.md, name the files needing updates, and state that no changes were applied. Never claim synchronization without verified repository writes.

## 9. HONESTY AND FAILURE HANDLING

Accuracy is more important than completeness. Never guess state, sources, citations, technical behavior, or evidence. If a tool fails, state what failed and what remains unverified; check current inputs before retrying. Never reuse stale revisions or bypass permissions.

If a substantive source-dependent answer remains unsupported after reasonable targeted investigation, respond exactly:
No confirmed information available to build this.
Then stop. Otherwise, state the limitation and request missing material.

## 10. RESPONSE STANDARD

Be precise and actionable. Follow MISSION.md language/detail requirements. Cite repository paths/headings, books by title/author/edition/page or chapter, and authoritative sources. Separate evidence from interpretation; avoid unrelated detail.

Your purpose is to help me learn, demonstrate capability, and maintain an accurate, verified progress record—not merely to produce answers.
~~~

### If the chat app cannot connect to GitHub

Use this fallback at the beginning of a session:

1. Open the repository on GitHub and download or copy the latest relevant files.
2. Provide at least `AGENTS.md`, `MISSION.md`, `EVIDENCE.md`, `RESOURCES.md`, and the active plan. Add the relevant learning record and source passage for the task.
3. Ask the assistant to label the session **SNAPSHOT** or **MANUAL**, identify missing files, and avoid treating the supplied copy as live.
4. Before the next session, provide refreshed files again. A public repository link by itself is not proof that the assistant can read it.

For a reusable learning system, keep the repository canonical and let every AI tool work from that same source. Do not maintain separate, silently diverging curricula in different chat apps.

---

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
1. Read MISSION.md, AGENTS.md, the active learning plan, RESOURCES.md,
   and EVIDENCE.md.
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

- EVIDENCE.md: record demonstrated capabilities with supporting evidence.
- learning-records/: record meaningful learning demonstrations and
  corrections.
- GLOSSARY.md: add terms only when the learner has used them correctly.
- RESOURCES.md: add or update sources only after verifying the actual
  source and relevant passage.
- The active journey: update only when the required planning rules
  and approval conditions are satisfied.

Never convert attendance, reading, generated code, or discussion into
proof of independent capability.

5. PROTECTED CHANGES

Do not silently:
- Change MISSION.md.
- Replace the active curriculum.
- Remove learning records or historical evidence.
- Change exit criteria or prerequisites.
- Delete files or rewrite repository history.

Follow the approval requirements in AGENTS.md.

6. SESSION MAINTENANCE REPORT

At the end of each session, report:

- Repository branch and access mode.
- Whether write access was available.
- Files inspected.
- Files created or updated.
- Commit or pull request reference, if any.
- Evidence recorded and why it qualifies.
- Remaining gaps and next eligible learning target.

Never report an intended action as a completed action.

~~~

ChatGPT Projects can keep related chats, files, and project instructions together. See [Projects in ChatGPT](https://help.openai.com/en/articles/10169521-projects-in-chatgpt).

### 3. Gemini

**Best for:** another conversational mentor, reusable study instructions, explanations, and alternative ways to explore a topic.

You can create a Skill with repeatable instructions for a learning role. Give it the same mentor contract and refer to the same mission, plan, and evidence files when you start a session. See Google's guide to [using Skills](https://support.google.com/gemini/answer/17094296?sjid=8405572224596321842-EU).

Do not create a separate, conflicting curriculum for every AI tool. Keep one canonical plan and ask each assistant to work from it.

### 4. Google Gemini Notebook (formerly NotebookLM)

**Best for:** source-grounded reading and research.

Google renamed NotebookLM to **Gemini Notebook** on July 16, 2026. It remains a notebook for working with a collection of sources. See Google's [announcement](https://blog.google/innovation-and-ai/products/gemini-notebook/notebooklm-gemini-notebook/).

A practical setup:

1. Create one notebook for a subject, course, or project.
2. Add the original books, papers, official documentation, lecture notes, or other material you have the right to use.
3. Ask focused questions about specific sources or sections.
4. Use citations and source links to return to the original material.
5. Bring useful findings back into your learning workspace, including RESOURCES.md when a source has been checked.

Use the notebook to explore and understand material. Do not treat an AI-generated summary, quiz, flashcard, audio overview, or video as proof that you have mastered the topic. Verify important claims in the original source and demonstrate the skill yourself.

---

## A workflow that connects all the tools

A useful division of responsibility is:

| Work | Best place to do it |
|---|---|
| Own and version the mission, plan, resources, and evidence | Git repository |
| Create or maintain learning files and practical project code | OpenCode or another repository-aware agent |
| Discuss a concept, receive a lesson, and explain your reasoning | ChatGPT Project or Gemini |
| Explore a set of books, papers, PDFs, or official documents | Gemini Notebook |
| Confirm mastery and update the progress record | The learner, supported by the mentor and backed by evidence |

You do not need all four tools. A single assistant can support the full loop. The combination above is useful when you want a clear separation between repository work, mentoring, and source exploration.

### The repeatable learning loop

**1. Define the goal.** Write the mission and identify the real outcome you want.

**2. Establish a baseline.** Identify what you already know, what you can demonstrate, and what is still unknown. Do not start from beginner material automatically.

**3. Build the journey.** Break the outcome into units with prerequisites, sources, practice, and exit evidence. Review the proposed plan before treating it as the curriculum.

**4. Verify the material.** Open the relevant source. Confirm that it supports the lesson and is appropriate for the version or subject you are studying.

**5. Learn one part at a time.** Ask the mentor to explain the next eligible concept using a concrete example. Ask questions before moving forward.

**6. Retrieve and practise.** Recall the concept without simply copying the explanation. Then solve a task or make a decision in a new scenario.

**7. Review the result.** Discuss what worked, what failed, and why. For AI-generated work, inspect and independently verify the result.

**8. Record evidence.** Update EVIDENCE.md only when the result supports a real claim. Record meaningful learning decisions and corrections when useful.

**9. Choose the next gap.** Continue from the plan and current evidence, not from whichever topic looks interesting in the moment.

---

## Start your own learning workspace

You do not need to redesign everything before learning anything. Begin with the smallest useful setup.

### Step 1 — Choose one outcome

Write down:

- What do I want to be able to do?
- Why does it matter?
- How will I demonstrate success?
- What do I already know?
- What are my time, budget, and other constraints?
- What is outside the scope?

### Step 2 — Customize the example

This repository currently contains an FDE-oriented mission and learning journey. They are an example configuration, not a requirement of the system.

For a different goal:

- Replace the contents of **MISSION.md** with your own outcome.
- Review **AGENTS.md** and replace the domain-specific mentor expectations with rules suitable for your subject.
- Replace **fde-journey-map.md** with a plan for your chosen topic, or create a new file such as **python-journey-map.md**, **language-learning-plan.md**, or **cloud-certification-plan.md**.
- Rebuild **RESOURCES.md** around the sources that actually support your plan.
- Reset or rewrite **EVIDENCE.md** so it describes your own demonstrated ability, not someone else's.
- Keep **TEACHING-PROTOCOLS.md** for reusable procedures, and adapt it only when your workflow requires a change.

Do not blindly copy the current FDE topics into an unrelated learning path. Keep the learning method; replace the subject matter.

### Step 3 — Build your first plan

Use this prompt with your preferred AI assistant:

~~~text
I want to build a long-term learning system for this goal:

[Describe the outcome you want.]

My current level:
[Describe what you already know and what you can demonstrate.]

My constraints:
[Time, budget, preferred language, available resources, and other limits.]

Help me create a personalized learning workspace.

First, clarify the outcome and assess my starting point. Then propose:
1. A concise MISSION.md.
2. Reusable mentor rules for AGENTS.md.
3. A learning plan with ordered units and prerequisites.
4. A source catalogue with verified sources and research gaps.
5. An evidence ledger that separates demonstrated skills from learning needs.

Each learning unit should include an objective, priority, prerequisites,
sources, a practical task, and clear exit evidence.

Do not invent my current skills or claim that I have completed anything.
Do not begin teaching the full curriculum before I review the plan.
~~~

### Step 4 — Start the first session

~~~text
Read my learning workspace and tell me:

- What is the goal?
- What is the current learning path?
- What evidence do we have about my current ability?
- Which unit is eligible to study next?
- Are its prerequisites and sources available?

Do not skip prerequisites. Teach only the first part of the next eligible
unit, explain the source, and end with one short retrieval question.
Wait for my response before continuing.
~~~

### Step 5 — Keep the workspace synchronized

At the end of a chat-based session, ask the assistant for a progress export:

~~~text
Prepare a session export for my learning repository.

Include:
- The capability I demonstrated, and the evidence for it.
- Misconceptions corrected or important decisions made.
- Any glossary term I used correctly for the first time.
- Changes needed in EVIDENCE.md and RESOURCES.md.
- The next eligible unit and its current status.

Do not include progress that was merely discussed, read, generated, or
assumed. Do not say that repository files were updated unless you
actually updated them.
~~~

Review this export before updating your files. When using a repository-aware agent, ask it to apply the reviewed changes and show you the diff.

---

## Design principles

These principles keep the system useful without turning learning into bureaucracy.

- **Goal before roadmap.** The learning path exists to serve an outcome, not to become an outcome itself.
- **Prerequisites before advanced topics.** Follow dependencies and close missing foundations.
- **Teach before testing.** Explanation and examples come before assessment.
- **Practice before declaring mastery.** A learner needs to apply ideas, not only recognize them.
- **Evidence before progress claims.** Keep demonstrated ability separate from familiarity and intention.
- **Sources before confident claims.** Verify facts that matter and name gaps when evidence is missing.
- **Small steps, real feedback.** Focus on one important learning gap at a time.
- **Human ownership.** AI can explain, research, draft, and implement. The learner remains responsible for understanding and verifying the result.
- **Adapt the plan.** Change the path when evidence, constraints, or the goal changes.
- **Keep it portable.** Store durable state in ordinary files that can move between tools.

## What this system is not

- It is not a magic prompt that guarantees expertise.
- It is not a fixed roadmap that everyone must follow.
- It is not a replacement for qualified instructors, official course requirements, or professional supervision where those are needed.
- It is not proof of competence just because an AI says you are doing well.
- It is not tied to OpenCode, ChatGPT, Gemini, or any one model provider.

AI systems can make mistakes, cite weak sources, miss context, and generate convincing but incorrect material. Verify important information, use original sources, and keep a human decision-maker responsible for progress claims.

## Contributing ideas

Useful improvements include:

- Better templates for missions, plans, learning units, and evidence records.
- Examples of adapting the system to different subjects.
- Clearer workflows for moving between coding agents, chat assistants, and source notebooks.
- Improvements that reduce unnecessary process while making learning outcomes easier to verify.

When proposing a change, explain the learning problem it solves. Prefer small, reusable improvements over rules that only fit one person's plan.

---

#### Acknowledgements & Inspiration

[This project was inspired in part by Matt Pocock's "teach" skill, from his open-source repository](https://github.com/mattpocock/skills/tree/main/skills/productivity/teach)

- His Knowledge, Skills, and Wisdom learning philosophy, mission-driven teaching, retrieval practice, learning records, and reference-document approach influenced the foundation of this system.

- This project builds upon those ideas and adapts them into a broader, customizable learning framework designed to work with different subjects, learning goals, and AI tools.

- **Special thanks to Matt Pocock for sharing his work with the developer community.**
---

**Learn with a plan. Learn from real sources. Practise until you can do it. Keep the evidence.**
