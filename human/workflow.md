---
purpose: Explains the human workflow for starting and maintaining a learning workspace.
read_when: When a human is starting or maintaining a workspace.
depends_on:
  - ../AGENTS.md
  - ../workspace/mission.md
---

# The repeatable learning loop

### The repeatable learning loop

**1. Define the goal.** Write the mission and identify the real outcome you want.

**2. Establish a baseline.** Identify what you already know, what you can demonstrate, and what is still unknown. Do not start from beginner material automatically.

**3. Build the journey.** Break the outcome into units with prerequisites, sources, practice, and exit evidence. Review the proposed plan before treating it as the curriculum.

**4. Verify the material.** Open the relevant source. Confirm that it supports the lesson and is appropriate for the version or subject you are studying.

**5. Learn one part at a time.** Ask the mentor to explain the next eligible concept using a concrete example. Ask questions before moving forward.

**6. Retrieve and practise.** Recall the concept without simply copying the explanation. Then solve a task or make a decision in a new scenario.

**7. Review the result.** Discuss what worked, what failed, and why. For AI-generated work, inspect and independently verify the result.

**8. Record evidence.** Update workspace/evidence.md only when the result supports a real claim. Record meaningful learning decisions and corrections when useful.

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

- Replace the contents of **workspace/mission.md** with your own outcome.
- Review **AGENTS.md** and replace the domain-specific mentor expectations with rules suitable for your subject.
- Replace **journeys/fde/journey-overview.md** with a plan for your chosen topic, or create a new file such as **python-journey-map.md**, **language-learning-plan.md**, or **cloud-certification-plan.md**.
- Rebuild **workspace/resources.md** around the sources that actually support your plan.
- Reset or rewrite **workspace/evidence.md** so it describes your own demonstrated ability, not someone else's.
- Keep **teaching/session-protocol.md** for reusable procedures, and adapt it only when your workflow requires a change.

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
1. A concise workspace/mission.md.
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
- Changes needed in workspace/evidence.md and workspace/resources.md.
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
