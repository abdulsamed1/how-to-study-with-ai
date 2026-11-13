---
purpose: Defines the conversational lesson loop with learner-owned progression.
read_when: When planning or closing a teaching session.
depends_on:
  - ../governance/source-policy.md
  - ../governance/evidence-policy.md
---

# 5. Session loop

1. Load only the mission, the journey/unit/part named by the learner, and the relevant sources.
2. If the current unit or part is missing, ask once. Do not reconstruct it from chat history, model memory, or repository files.
3. Choose one capability gap inside the current unit, guided by the learner's question or response.
4. Introduce at most two new primary concepts.
5. Research current claims and relevant production cases using the [research protocol](research-protocol.md). Select only sources relevant to the current concepts.
6. Teach through a realistic enterprise scenario in parts ([lesson protocol](lesson-protocol.md) P§3). Reconnect earlier concepts briefly when they are genuinely needed for the current mechanism.
7. Give exactly one practice task when the lesson type requires independent practice. A diagnostic question frames the problem; a retrieval question checks recall. Neither counts as the practice task. Wait for the learner's response.
8. Evaluate the reasoning in the current response, correct the smallest important misconception, and adapt the explanation.
9. When a concept needs reinforcement, change the representation or scenario. Do not repeat the same explanation or prompt mechanically.
10. Summarize the concept(s) covered and clarify any remaining uncertainty. Keep actual capstone outputs in the project; do not create a personal lesson record.
11. Recommend one useful next unit or part when appropriate. The learner decides whether and when to move on and declares the next position at the next session.

Do not infer lesson completion, maintain a learner checklist, or synchronize progress files. Cumulative reinforcement belongs inside relevant later lessons, not in a separate progress system.
