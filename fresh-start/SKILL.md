---
name: fresh-start
description: Turn a chat that keeps going wrong into one clean brief to paste into a new chat. Use when the assistant repeats a mistake after correction, the chat goes in circles, or the user wants to start over.
---

# Fresh Start

Write the first message of a new conversation: one brief that carries everything worth keeping and nothing that caused the trouble.

## Why this matters

When an assistant gets something wrong and the user corrects it, the wrong version is still in the conversation. Every later reply is written with that mistake in view, alongside the correction, the apology, and the retry. After two or three rounds the chat contains more wrong attempts than right instructions, and arguing adds to the pile. A new conversation with a better first message usually gets there faster than a fourth correction.

The hard part is the first message. The user has explained things across thirty turns and does not want to do it again. This skill does it for them.

## Procedure

1. **Diagnose in one line.** What kept going wrong: a constraint that was lost, an early wrong assumption, a misread goal, an instruction that conflicted with another, or simply too much history? Tell the user in a sentence. If you made the mistakes, say so once and move on. Do not apologize at length.
2. **Extract what matters from the whole conversation**, including details the user only mentioned inside a correction:
   - The goal, and what it is for
   - Who the result is for
   - Every requirement and constraint the user stated
   - Facts, data, names, and numbers the task depends on
   - Decisions already made, so they are not reopened
   - The latest good version of the work, if there is one
   - What "done" looks like, and the format the user wants
   - Questions still open
3. **Turn each correction into a requirement.** Write what should happen. "All prices in CAD, including the summary table" is better than "don't use USD like last time". Describing the wrong output in detail can pull the new chat back toward it. Where a known trap needs naming, do it in one short line under "Avoid".
4. **Write the brief for someone with no context.** The new chat has not seen this one. Remove "as we discussed", "the second version", "like before". Every reference must be to something inside the brief or a file the user will attach.
5. **Include the material, not a pointer to it.** If the task needs the draft, the data, or the code, put it in the brief or tell the user exactly which file to attach. A brief that says "use the spreadsheet" with no spreadsheet fails immediately.
6. **Leave out the story.** No history of attempts, no apologies, no account of what went wrong. Keep only what changes the output.
7. **Read it as a stranger.** Could a capable person with only this message do the task? Fix whatever is missing. Remove passwords, keys, and private details that are not needed.
8. **Hand it over.** Put the brief in one code block so it copies cleanly. Then tell the user, in a line or two, to open a new chat, paste it, and attach any files you list.

## Brief format

Use the sections that apply and drop the rest. A simple task needs four of them.

```text
Goal
<what to produce, and what it's for>

Audience
<who will read or use it>

Requirements
- <each requirement, stated positively>

Context and facts
<the details, numbers, names, and decisions the work depends on>

Current version
<the latest good draft, pasted in full, or "attached: filename">

Avoid
- <one line per known trap, only if needed>

Output
<format, length, tone, and what counts as done>

Before you start
<"Ask me X if unclear", or "No questions needed, go ahead">
```

## Rules

- **Keep it short.** If the brief is longer than the work it asks for, it is carrying history. Cut.
- **Do not improve the task.** Carry over what the user asked for, not what you think they should want. If you spot a real problem with the request, mention it outside the brief.
- **Do not paste the bad outputs.** They are what the fresh start is escaping.
- **Preserve the user's wording for requirements they care about.** If they said "no jargon" three times, the brief says "no jargon".
- **Flag gaps honestly.** If something the task needs was never provided, list it under "You'll need to add" outside the code block. Do not fill it in with a guess.

## When not to use this

If the fix is one clear correction and the conversation is short, just make the correction. A fresh start is for the third failed attempt, not the first.

For moving repository work between coding agents, with branch state, changed files, and verification results, use a handoff document instead.

## Example

Situation: across a long chat, the user asked for a cover letter. The assistant kept writing it too formal and too long, and twice restored a line about "passion for synergy" that the user had deleted.

```text
What went wrong: I kept reverting to a formal template and lost your length limit after the second revision.

Paste this into a new chat and attach your resume:
```

```text
Goal
Write a cover letter for the Product Designer role at Northwind, to send by email.

Audience
The hiring manager, Dana Okafor. The posting describes the team as small and informal.

Requirements
- 180 words or fewer
- Plain, conversational tone. Write the way a person talks to a future colleague.
- Open with the checkout redesign project and its result
- Mention that I've used their product for two years
- No buzzwords

Context and facts
- Checkout redesign at my current job cut drop-off from 31% to 22%
- I'm available from March 1
- My resume is attached for anything else you need

Avoid
- Corporate phrases such as "passion for", "synergy", "leverage"

Output
The letter only, ready to paste into an email. No subject line, no notes.

Before you start
No questions needed, go ahead.
```
