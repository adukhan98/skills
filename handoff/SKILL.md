---
name: handoff
description: Capture active work in a concise, durable continuation document for another Codex task or agent. Use when work must pause, branch, move to a fresh context, transfer ownership, or preserve exact repository and verification state without duplicating existing artifacts.
---

# Handoff

Create a continuation record that lets the next agent act without reconstructing settled work.

## Procedure

1. Inspect the actual workspace state: repository instructions, git status and diff, recent commits, active plan or goal, source artifacts, verification output, and any live or returned subagent ownership. Do not rely on conversation memory alone.
2. Use the project's handoff convention. Otherwise save `work/handoffs/YYYY-MM-DD-<slug>.md`.
3. Reference specs, maps, research, prototypes, tickets, ADRs, commits, diffs, and generated artifacts by path or URL. Do not restate their full contents.
4. Redact credentials, tokens, personal data, private URLs, and sensitive values. Name a secret store or environment variable instead of recording the secret.
5. Tailor the handoff to the next task the user named. Do not mark an active goal complete merely because the task is moving.
6. When the user names an existing Codex task as the recipient and native task handoff is available, use it after refreshing the document. Do not create a new task unless the user explicitly asks for one.

## Document contract

Include:

- Objective and completion criteria
- Current status: done, in progress, and next
- Decisions and rationale
- Constraints, non-goals, and assumptions
- Source-of-truth paths and URLs
- Changed files, branch, baseline, and dirty-tree state
- Commands run, exact results, failures, and skipped checks
- Active plan or goal and subagent ownership
- Blockers and risks
- Exact first action for the next agent
- Suggested skills
- Redaction note

## Completion

Read the finished handoff once against the current workspace. Correct stale paths, missing ownership, ambiguous status, or unsafe data. Return the absolute file path and a one-line description of the next action.
