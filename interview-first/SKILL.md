---
name: interview-first
description: Ask a few sharp questions before starting a task, then do it using the answers. Use for "interview me" or "ask me questions first", or when a short, vague request needs a tailored result.
---

# Interview First

Before doing substantial work, ask only the questions whose answers would change the result. Then do the work.

## Why this matters

Most requests arrive as one line, because a chat box invites one line. The assistant fills every gap with the most average assumption available, and the result is a generic answer the user then has to correct piece by piece. A few good questions up front cost the user thirty seconds and replace three rounds of revision.

There is a second benefit. Answering the questions often clears up the user's own thinking. Sometimes they solve the problem while explaining it.

## Procedure

1. **Use what you already have.** Read the conversation, attached files, and anything you know about the user. Do not ask for something that is already there or that you can look up.
2. **List the unknowns, then keep only the ones that matter.** For each gap, ask: would a different answer change what I produce? If not, pick a sensible default and move on. Keep the questions where a wrong guess means redoing the work.
3. **Ask in one batch.** Up to five questions, most important first. Fewer is better. If two will do, ask two. People answer one short list. They abandon a slow drip of single questions.
4. **Make each question easy to answer.** Give options or a default, so the user can reply in a few words or just say "defaults".
5. **Wait.** Do not start the task in the same message. Half-doing the work with guesses defeats the purpose.
6. **Confirm in two or three lines.** After they answer, restate the brief as you now understand it, including any defaults you chose for questions they skipped.
7. **Do the whole task.** Use their answers visibly. If they said the reader is a busy executive, the first line should show it.

## What makes a good question

- **Specific.** "Who's reading this: your manager, a client, or the whole team?" beats "Who is the audience?"
- **Answerable in a few words.** If answering it takes an essay, split it or offer options.
- **About them, not about the topic.** Ask for what only the user knows: their goal, their situation, their constraints, their taste. Do not ask them things you should know or can find.
- **Comes with a default.** "How long? I'd aim for about 150 words unless you say otherwise."

Draw from these when they are unknown and would change the output:

- **Purpose.** What is this for? What should happen after someone reads or uses it?
- **Audience.** Who is it for, and what do they already know or believe?
- **Situation.** The background facts only the user has: numbers, history, relationships, stakes.
- **Constraints.** Length, deadline, budget, tools, tone, things that must be included or left out.
- **Quality bar.** What would make this great? Is there an example they like?
- **History.** What have they already tried, and what did not work?

Never ask all of these. Pick the few that matter for this task.

## Format

```text
A few quick questions so this fits you. Answer in a few words, or say "defaults" and I'll go with the choices in brackets.

1. <question> [default: <choice>]
2. <question> (a) <option> (b) <option> (c) <option> [default: b]
3. <question> [default: <choice>]
```

## Example

**User:** write me a bio

```text
A few quick questions so this fits you. Answer in a few words, or say "defaults" and I'll go with the choices in brackets.

1. Where is it going? (a) LinkedIn (b) your website (c) a speaker or event page (d) a social profile [default: a]
2. What do you do, and what's the one thing you most want to be known for?
3. What should a reader do after reading it: hire you, follow you, book you to speak, something else? [default: get in touch about work]
4. First person ("I help...") or third person ("Sam helps...")? [default: first person]
```

Question 2 has no default because only the user knows the answer. That is fine. Do not invent one.

**User:** website. I'm a wedding photographer in Lisbon, known for unposed documentary style. want inquiries. first person

```text
Got it: a first-person bio for your website, for couples deciding who to hire, built around your unposed documentary style, ending on an invitation to inquire. I'll keep it to about 100 words.

<the bio>
```

## Edge cases

- **The user says "just do it" or ignores the questions.** Go ahead with your defaults. List the assumptions you made in one line at the top so they can correct any of them.
- **An answer opens a real fork.** One follow-up round is fine when an answer reveals a decision you could not have anticipated. Do not run a third.
- **Answers contradict each other.** Point it out briefly and ask which one wins. "Under 100 words" and "cover all six projects" cannot both hold.
- **The request is already detailed.** Skip the interview. If the user gave you what you need, asking anyway is a delay.
- **Quick or factual requests.** Just answer. "What's the capital of Portugal?" does not need an interview.
- **Urgent requests.** If the user is clearly in a hurry, ask one question at most, or proceed on defaults and say which.

## Staying on

When the user turns this on as a standing mode ("always ask me first"), apply it to every substantial task for the rest of the conversation, and keep skipping it for quick ones.
