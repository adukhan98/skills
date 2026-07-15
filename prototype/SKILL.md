---
name: prototype
description: Support shaping or specification with a disposable, runnable experiment that answers one design question. Use when a state model, business rule, data shape, interaction, or UI direction must be seen or run before the decision can be settled.
---

# Prototype

A prototype answers one question. It is not a smaller production feature.

## Procedure

1. Write the question, decision it will inform, assumptions, and observable verdict conditions before coding.
2. Inspect the host project's runtime, routing, design system, and task runner. Reuse them. If none exists, choose the lowest-dependency local runtime already available and record the choice; do not add a framework or package manager solely for the experiment.
3. Choose one branch:
   - For state, rules, data shape, or API behavior, read [references/logic.md](references/logic.md).
   - For layout, hierarchy, interaction, or visual direction, read [references/ui.md](references/ui.md).
4. Isolate the entire prototype from production writes, credentials, analytics, and deployment. Use in-memory state, fixtures, stubs, or clearly disposable local data.
5. Put isolated experiments under the project's prototype convention or `work/prototypes/<slug>/`. When real page context is essential, use a clearly named development-only surface and gate the whole prototype out of production.
6. Provide one command or URL to run it. Surface the relevant state or variant at all times.
7. Run the minimum build, type, lint, and smoke checks needed to prove the experiment works. Add automated tests only when the test itself is the experiment's measurement.
8. Record the verdict in `PROTOTYPE.md`: question, run command, evidence, observed result, chosen direction, rejected directions, reusable decisions, and cleanup status.
9. Feed the decision into the active brief, map, or spec, then return to the interrupted core phase. Do not jump past `$spec` or `$tickets`, and do not promote the prototype wholesale.

Do not create a branch, commit, tracker issue, deployment, or production mutation unless the user explicitly requests it.
