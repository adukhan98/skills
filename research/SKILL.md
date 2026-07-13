---
name: research
description: Investigate a build or design decision using current high-trust sources and preserve the evidence. Use when a workflow depends on external documentation, APIs, standards, source code, papers, version-sensitive facts, comparisons, or delegated reading before a decision can be made.
---

# Research

Research must answer a decision, not collect links.

## Procedure

1. State the question, the decision it informs, scope, required freshness, and relevant project/dependency versions.
2. Inspect repository source, manifests, lockfiles, local documentation, and existing notes first.
3. Browse for external or current facts. Prefer official documentation, specifications, primary research, first-party APIs, and source repositories. Use community or secondary sources when the question is explicitly about lived practice or sentiment, and label that evidentiary role.
4. Split independent source lanes across subagents when parallel reading materially helps. Keep source selection, synthesis, and verification with the parent task.
5. Verify decision-critical claims against the cited source. Record direct links or stable permalinks, versions, dates, and limitations.
6. Separate verified facts, inference, recommendation, and unknowns. Do not present an inference as source fact.
7. When later workflow stages depend on the answer, save a Markdown note using the project's convention or `docs/research/YYYY-MM-DD-<slug>.md` with:
   - Question and decision
   - Executive answer
   - Verified findings
   - Project implications
   - Alternatives and trade-offs
   - Unknowns and limitations
   - Sources
8. For a one-off answer with no durable downstream use, answer inline unless the user asked for a file.
9. Link durable findings from the active brief, map, or spec. Surface any decision the evidence changes instead of silently rewriting it.

## Completion

Finish when the question has a source-backed answer, citations support every material factual claim, freshness/version limits are explicit, and remaining unknowns have owners or next steps.
