---
purpose: Defines deep, source-first preparation for every learning response.
read_when: Before preparing a source-dependent lesson or explanation.
depends_on:
  - ../governance/source-policy.md
  - ../governance/evidence-policy.md
---

# P§9. Deep source-first learning procedure

## 1. Discover broadly

1. Identify the question, concept, practical problem, and related concepts that may explain it.
2. Search the full set of available ChatGPT Project Sources—not only the books or source IDs named by the active journey. Search books, PDFs, papers, notes, and other relevant documents.
3. Search using the main term, synonyms, alternate terminology, mechanisms, neighboring concepts, and the problem the concept solves.
4. Use the source index and journey tags only to discover useful starting points. They are not an allowlist, ranking, mandatory source set, or chapter-reading plan.
5. Follow references inside promising sources. Compare relevant explanations across books instead of stopping at the first matching passage.
6. Add strong external primary material when it supplies missing depth or current technical detail.

## 2. Explore the source material

For each relevant source that is available:

- Read the substantive passage and enough surrounding context to understand the author's argument.
- Explore related sections, examples, tables, diagrams, notes, and cross-references that clarify the topic.
- Search the whole relevant book for the topic; do not assume one assigned chapter contains everything useful.
- Identify definitions, motivation, assumptions, mechanisms, components, sequences, examples, variants, constraints, trade-offs, failure modes, limitations, and relationships to other concepts.
- Look for details that qualify or contradict the initial explanation. Do not extract isolated sentences while ignoring the author's surrounding reasoning.
- Do not stop after finding one definition or one short excerpt when the topic requires deeper treatment.

Do not maintain a record of which pages or chapters the AI has read. Do not require a pre-existing reading-status entry, source verification label, file-format record, or chapter assignment.

## 3. Build the teaching explanation

Organize the knowledge before answering:

1. What problem is the author addressing, and why does it matter?
2. What does the concept mean, and what does it not mean?
3. How does it work? Explain the mechanism and the relationship between its parts.
4. What conditions, assumptions, and design choices affect it?
5. What examples, edge cases, failure modes, trade-offs, and limitations matter?
6. How does it compare with related concepts or alternative approaches?
7. How does it apply to the learner's current problem?

Cover all source details that materially help answer the question. Prefer a complete, coherent explanation over brief definitions or superficial summaries. Follow the repository's teaching concept limits without omitting the important depth within the selected concepts.

## 4. Teach; do not send the learner away

- Explain the relevant knowledge directly in the response, in original wording.
- Never replace an explanation with a book title, author name, chapter number, page pointer, or instruction to read a chapter.
- Mention bibliographic information only as attribution after or beside the explanation.
- Clearly separate what the source says from mentor synthesis, illustrative examples, and application to the learner's system.
- If multiple authors differ, explain their distinct positions and the reason for the difference.
- Paraphrase; do not reproduce extensive copyrighted passages.

## 5. Access and attribution

The source index does not prove that a source is present in the current Project or that any particular claim appears in it. Do not perform administrative checks or maintain reading-status metadata. Retrieve the actual material needed for the current response when source access is available.

Never pretend to have inspected inaccessible text or attribute a claim to a source based only on its title, URL, table of contents, memory, or another AI's summary. When a source cannot be accessed, use other accessible material and state the limitation if it materially affects the answer.

Use current official documentation for changing API, model, product, security, and version-specific behavior. Books remain valuable for underlying concepts and engineering reasoning.

## 6. Lesson handoff

Use the Journey Unit or Temporary Learning Scope declared by the learner. If the current unit is missing, follow the session-position rule in AGENTS.md.

Prepare the problem, the source-derived explanation, relevant concept links, failure cases, and any retrieval/practice prompts required by the lesson protocol. Do not create source-read records, source coverage gates, learner-progress records, or session exports.
