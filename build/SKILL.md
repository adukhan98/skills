---
name: build
description: Implement ready tickets, then review and verify the completed work in the current codebase. Use when one or more implementation tickets are ready, when the user requests TDD-backed ticket delivery, or when existing code needs spec compliance and code-quality review.
---

# Build

Implement from an authoritative contract. Do not invent unresolved product behavior.

This skill owns both the build phase and the review phase.

## Build phase

1. Read the ready ticket, its referenced spec, and any relevant handoff. Identify acceptance criteria, exclusions, dependencies, and unresolved contradictions. Return a material product gap to `$shape` or `$spec`, then update the affected tickets before resuming.
2. Read repository instructions and inspect the relevant code, tests, current git status, baseline revision, and existing diff. Preserve unrelated user changes and active branch state.
3. Discover the project's actual feedback commands. Map each acceptance criterion to an implementation slice, seam or evidence method, and completion check.
4. Create or update a concise Codex plan for nontrivial work. Split only genuinely independent lanes across subagents; give each disjoint ownership and keep integration with the parent.
5. Implement one vertical slice at a time with small reviewable patches. Apply `$tdd` when behavior benefits from an automated loop. Use risk-proportionate checks for configuration, generated files, migrations, visual work, or mechanical changes.
6. Run focused checks after each slice. Keep unrelated refactoring out of scope; when a prerequisite refactor is necessary, make the change easy first while preserving behavior, then make the easy change.
7. Verify the real user surface. Run browser/UI checks for visible flows, safe migration checks for data changes, and build/type/lint/test commands that apply to this repository.

## Review phase

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

Report delivered behavior, key changed files, acceptance evidence, exact commands and results, review findings resolved, skipped checks, and remaining risks.

Mark the work complete only when every in-scope acceptance criterion is reviewed and verified. If progress cannot continue, report the work as blocked rather than complete and name the exact missing decision, dependency, or authority.
