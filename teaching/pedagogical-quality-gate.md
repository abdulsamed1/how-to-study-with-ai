---
purpose: Separates instructional quality review from technical correctness review.
read_when: Before accepting a lesson or revising a teaching interaction.
depends_on:
  - pedagogical-principles.md
  - head-first-lesson-blueprint.md
  - ../governance/source-policy.md
  - ../governance/evidence-policy.md
---

# Pedagogical quality gate

Run this gate independently of the content quality gate. A technically correct lesson
can still fail to teach; an engaging lesson can still contain unsafe or false claims.

## Quality improvement criteria

These criteria improve a passing lesson but do not compensate for a hard invariant
failure.

1. Does the opening problem matter to the stated learner outcome?
2. Is there a purposeful curiosity or prediction opportunity?
3. Does the explanation move from intuitive to technical at a usable pace?
4. Are examples, analogies, and visuals accurate, bounded, and useful?
5. Is information density appropriate for the learner's current knowledge?
6. Are misconceptions treated diagnostically rather than punitively?
7. Does the interaction adapt to the learner's response?
8. Does the lesson revisit the original problem and expose a limitation?
9. Is there an immediate retrieval opportunity and a justified future review hook?
10. When practice is required, does the one practice task test transfer rather than copying?
11. Does each required interaction checkpoint stop and wait for the learner's actual
    response before the mentor continues?
12. Does the lesson align with one objective, two-concept limit, journey owner, and
    mastery evidence?
13. Does the tone remain precise, accessible, and non-theatrical?

## Acceptance procedure

1. Determine which criteria apply. A direct factual answer may not require the full
   four-part lesson; a lesson unit that does not require practice or transfer is not
   rejected for omitting those elements.
2. Evaluate hard instructional invariants before improvement criteria.
3. List each violation and the smallest correction.
4. Correct the lesson or request the required revision.
5. Re-evaluate the affected criteria.
6. Accept only when every applicable hard invariant is satisfied.

## Hard instructional invariants

A lesson fails this gate when it:

- introduces more than two new primary concepts;
- starts with a definition when the context requires problem-driven discovery;
- asks for meaningful learner input but continues without waiting when that input
  determines the next move;
- asks a diagnostic, prediction, or retrieval question and supplies its answer in
  the same response;
- attributes reasoning or understanding to the learner without an expressed answer;
- reveals a retrieval answer before the learner's attempt or repeats the answered
  prompt in the same response;
- uses a misleading or technically inaccurate analogy or visual;
- claims a four-part lesson while omitting an applicable part boundary;
- gives more than one practice task when exactly one is required;
- omits required transfer assessment;
- claims mastery without the supporting learner evidence required by the journey.

These are context-sensitive. Direct-answer requests may bypass discovery and pauses.
Simple factual questions may use a shorter response. Content correctness and source
integrity remain separate hard requirements under the content quality gate; engaging
presentation cannot compensate for inaccurate teaching.

## Failure conditions and correction

- **Definition-first without a learner need:** replace the opening with a problem or
  explicit reference response.
- **Reveal before reasoning:** insert one useful prediction or explain why it is not
  appropriate for this learner.
- **Too much novelty:** remove concepts, defer internals, or return to a concrete case.
- **Decorative or opaque visual:** simplify, label, explain, or remove it.
- **Analogy treated as identity:** state the useful mapping and its limitation.
- **Generic correction:** diagnose the assumption and choose a contrastive intervention.
- **Coverage mistaken for mastery:** add retrieval, changed-scenario transfer, and an
  evidence record.
- **Rigid discovery barrier:** answer directly when requested or when scaffolding no
  longer produces useful reasoning.
- **Checkpoint violation:** remove the unrevealed answer and end at the question;
  continue only after the learner responds, unless the direct-answer exception
  applies.

## Two quality dimensions

**Content Quality Gate:** source integrity, technical correctness, security, evidence,
and explicit uncertainty.

**Pedagogical Quality Gate:** relevance, progression, clarity, interaction, cognitive
load, representation, feedback, retrieval, transfer, and objective alignment.

Do not collapse these dimensions into an invented numerical score.
