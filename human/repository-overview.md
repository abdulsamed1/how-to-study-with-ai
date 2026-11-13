---
purpose: Explains the learning-system concept and repository documents for humans.
read_when: When a human needs the product or repository overview.
depends_on:
  - ../AGENTS.md
---

# Learn with intent. Let the learner own the path.

A portable, learner-led system for learning **any subject with AI**.

Turn an ambitious goal into a structured learning journey. Give your AI mentor a clear role, work from trusted sources, practise what you learn, and declare your own current learning position.

This repository is a reusable learning-system blueprint. It is not tied to one subject, one curriculum, or one AI provider. Use it for software engineering, mathematics, languages, university courses, professional certifications, career changes, research topics, or a personal project.

 > **The idea:** Your goal defines the destination. Your plan defines the path. Your sources ground the learning. AI helps you think and practise. You decide where you are in the plan; project artifacts show what the system actually does.

---

## The learning system

A good learning workflow is more than a prompt that asks an AI to “teach me”. It needs a small set of files that give the AI context, constraints, a curriculum, trusted material, and an honest record of progress.

~~~text
                   YOUR LEARNING GOAL
                           |
                           v
                     workspace/mission.md
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
       workspace/resources.md      AGENTS.md      real tasks
             |             |             |
             +-------------+-------------+
                           |
                           v
                  CURRENT LESSON / PRACTICE
             Learner declares the unit and part
                           |
                           v
                 ACTUAL PROJECT ARTIFACTS
                code, tests, ADRs, reports, runs
~~~

The files are plain Markdown. The repository stores the mission, curriculum, source rules, and real project artifacts. The learner's current unit is declared by the learner; it is not reconstructed from chat history or stored in a Git progress ledger.

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

The learning process separates exposure from application. Reading a chapter or giving an immediate correct answer is useful, but the learner owns decisions about what has been studied and when to move on. Real system claims must still be grounded in actual code, tests, reports, traces, deployments, or other project artifacts.

---

## The core files

You do not need to create every file on day one. Start with the core documents and add supporting files when the learning journey needs them.

| File | Responsibility | What belongs in it |
|---|---|---|
| **workspace/mission.md** | The destination | Why you are learning, observable outcomes, constraints, and out-of-scope topics |
| **AGENTS.md** | The mentor contract | How the AI should teach, research, challenge, assess, and behave |
| **Your plan / journey map** | The learning path | Topics, units, priorities, prerequisites, sources, practice, and exit criteria |
| **workspace/resources.md** | The source catalogue | Verified sources, sources to verify, and known coverage gaps |
| **teaching/session-protocol.md** | The operating procedures | Repeatable formats, tool setup, session workflow, and progress synchronization |

Supporting files can be added gradually:

| File or folder | Responsibility |
|---|---|
| **GLOSSARY.md** | Short definitions for terms you have learned to use correctly |
| **casebook/** | Verified real-world failures and the engineering lessons that can be transferred from them |
| **lessons/** | Reusable lesson material, when it is useful to keep a lesson outside the chat |
| **reference/** | Checklists, diagrams, decision tables, and concise reference sheets |
| **assets/** | Shared styles or components for saved learning materials |

### How the files work together

**workspace/mission.md — Define success before collecting content**

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

- Read the current mission, the unit named by the learner, and the relevant sources before teaching.
- Identify the next eligible topic from the plan. Respect prerequisites.
- Teach before testing. Do not turn every session into an unexplained quiz.
- Introduce a small number of concepts at a time.
- Explain the source of important claims and identify what could not be verified.
- Separate source-backed facts, recommendations, hypotheses, and practice scenarios.
- Evaluate reasoning and application, not just the final answer.
- Do not infer lesson completion or mastery from reading, AI output, memory, or chat history.
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

**workspace/resources.md — Keep the learning connected to real material**

Organize sources by their status:

- **Verified references:** opened and checked; suitable to support a claim.
- **References to verify:** useful leads that have not yet been checked.
- **Coverage gaps:** topics for which you do not yet have an adequate source.

Record the title, author or publisher, link, relevant chapter or section, and verification status when available. Prefer primary sources such as official documentation, specifications, standards, original papers, and first-party engineering reports. Use secondary explanations to help you understand, not to silently replace the source that establishes a technical fact.

**Learner-owned progress — No progress ledger**

The learner states the current journey, unit, and part at the start of each session. The mentor does not maintain a completion checklist or infer progress from chat history. It may give a next-unit recommendation, but the learner decides whether to move on.

Keep actual capstone artifacts in the project they belong to. Tests, implementation code, ADRs, evaluation reports, traces, deployment evidence, and measured outcomes support claims about the system; they are not a personal progress diary.

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
