---
name: shape
description: Brainstorm and interview a vague product, feature, system, or workflow idea until it becomes a decision-complete brief. Use when the user wants to be grilled one important question at a time, stress-test an idea, or clarify what should be built before writing a spec.
---

# Shape

This is the brainstorm and interview phase. Produce a brief that `$spec` can trust.

## Procedure

1. Inspect repository instructions, existing briefs/specs, domain documents, relevant code, and current behavior before asking questions. Resolve local facts directly.
2. Create or update the project's existing discovery artifact. If no convention exists, use `docs/briefs/<slug>.md` with these sections:
   - Outcome
   - Users and problem
   - Success signals
   - Constraints
   - Decisions
   - Assumptions
   - Risks
   - Open questions
   - Out of scope
   - Evidence
3. Ask exactly one material decision per turn, in prerequisite order. Give a recommended answer first, then its main trade-off and concise alternatives.
4. Treat explicit delegation such as "use your judgment" as authority to choose routine, reversible details. Record the assumption instead of asking.
5. Update the brief after each resolved branch. Mark entries as confirmed, assumed, deferred, or rejected.
6. Use `$research`, `$prototype`, or `$map` only when a decision genuinely needs that evidence. Feed the result back into the same interview and continue.
7. Sharpen overloaded domain terms. Update an existing glossary when one exists; create one only after multiple durable terms have been resolved.
8. Record an ADR only when the choice is hard to reverse, surprising without context, and the result of a real trade-off.

## Exit gate

Finish shaping when the outcome, users, success signals, scope, core behavior, constraints, major risks, and material assumptions are explicit and no open question blocks a spec.

Show the compact brief and ask for one final confirmation when the user is actively deciding. When the user delegated decisions or requested end-to-end execution, label delegated assumptions and continue to `$spec`.
