---
name: build
description: Implement and verify a defined feature, fix, specification, or ticket in the current codebase. Use when the user explicitly wants code changed or a settled slice delivered end to end, including proportional testing, independent review, and clear verification evidence.
---

# Build

Implement from an authoritative contract. Do not invent unresolved product behavior.

## Procedure

1. Read the spec, ticket, brief, or handoff and identify acceptance criteria, exclusions, dependencies, and unresolved contradictions. Route a material product gap back to `$shape` or `$spec`.
2. Read repository instructions and inspect the relevant code, tests, current git status, baseline revision, and existing diff. Preserve unrelated user changes and active branch state.
3. Discover the project's actual feedback commands. Map each acceptance criterion to an implementation slice, seam or evidence method, and completion check.
4. Create or update a concise Codex plan for nontrivial work. Split only genuinely independent lanes across subagents; give each disjoint ownership and keep integration with the parent.
5. Implement one vertical slice at a time with small reviewable patches. Apply `$tdd` when behavior benefits from an automated loop. Use risk-proportionate checks for configuration, generated files, migrations, visual work, or mechanical changes.
6. Run focused checks after each slice. Keep unrelated refactoring out of scope; when a prerequisite refactor is necessary, make the change easy first while preserving behavior, then make the easy change.
7. Verify the real user surface. Run browser/UI checks for visible flows, safe migration checks for data changes, and build/type/lint/test commands that apply to this repository.
8. Review the complete diff on two independent axes:
   - **Spec** - missing, partial, incorrect, or unrequested behavior.
   - **Quality and safety** - repository standards, correctness, security, maintainability, debug residue, secrets, and unrelated edits.
   For material diffs, use separate subagents when available so one axis does not bias the other.
9. Fix blocking findings and rerun every affected check. Repeat until no blocking finding remains.
10. Run final proportional verification, including `git diff --check` in a Git repository. State every skipped or unavailable check and why.
11. Update each source artifact through its defined lifecycle and attach acceptance evidence. Do not invent a status that the artifact contract does not define.

## Multiple tickets

Work the unblocked frontier. Assign one bounded ticket per agent task, avoid parallel edits to the same files or stateful migrations, integrate returned work, and verify the combined result before starting dependent tickets.

## External state

Do not commit, push, close external issues, publish, deploy, or mutate production systems unless the user explicitly requests that action. If asked to commit in a dirty tree, include only in-scope changes.

## Completion

Report delivered behavior, key changed files, acceptance evidence, exact commands and results, review findings resolved, skipped checks, and remaining risks. The work is complete only when every in-scope acceptance criterion is verified or explicitly blocked.
