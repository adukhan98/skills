---
name: confidence-check
description: Label each key claim as sure, likely, or guess, with its basis and what to verify first. Use for "how sure are you?", before acting on an important answer, or when everything sounds equally certain.
---

# Confidence Check

Answer the question, then show which parts are solid, which are probably right, and which are guesses.

## Why this matters

An assistant writes a shaky guess in the same fluent, certain voice as an established fact. People read confident wording as a sign of accuracy, so they stop checking exactly where they should start. Labeling the claims gives the user back the signal the tone was hiding: where to spend five minutes verifying.

Be honest about what the labels are. They are a judgment about how the answer was produced. They are not a measurement, and an assistant can be wrong about its own certainty. Their job is to point at where to check, so the most useful label is an accurate "guess".

## The three levels

| Label | Meaning | Typical basis |
| --- | --- | --- |
| **Sure** | Would be surprised to be wrong. | Checked in this conversation against a source, file, or calculation. Or stable, widely documented knowledge. |
| **Likely** | Probably right, and the details could be off. | General knowledge recalled from training. Reasonable inference from solid facts. |
| **Guess** | A lead to follow, not a fact to use. | Estimate, extrapolation, reconstruction from partial memory, or anything about a situation you cannot see. |

Always say the basis in a few words: "checked on the linked page", "from memory", "estimated from the two figures above". "From memory" and "verified here" are very different, and the user cannot tell them apart unless you say which.

## What should lower the label

Drop a level, or go straight to "guess", when the claim is one of these and you have not checked it in this conversation:

- A specific number, date, price, or statistic
- A direct quote, or a citation with authors, title, or year
- A URL, file path, version number, or setting name
- Anything that may have changed recently, or after your training data ends
- A niche topic, a small organization, or a private individual
- Legal, medical, tax, or financial specifics that vary by place or person
- Arithmetic done in your head
- A statement about the user's own files, code, or situation that you have not actually read

## Procedure

1. **Answer first.** Lead with the answer, as you normally would. Labels support the answer and never replace it.
2. **Pick the claims that matter.** Label the statements the user might act on or repeat. Do not tag every sentence. Definitions and connecting sentences need no label.
3. **Upgrade by checking when it is cheap.** If you can verify a guess with a search, a file read, or a calculation, do that and report the checked result. A verified answer beats a labelled guess.
4. **Label honestly, and use the whole range.** If everything comes out "likely", the labels are not doing any work. Make yourself separate what you would bet on from what you would not.
5. **End with what to check first.** One or two items, each with a specific way to check it: the document to open, the person to ask, the search to run.

## Format

Short answers take inline tags:

```text
The Treaty of Westphalia was signed in 1648 [sure: standard history]. It ended the Thirty Years' War [sure] and involved more than 100 delegations [likely: from memory, the exact count varies by source].

Check first: the delegation count, if you plan to quote it. Any encyclopedia entry on the Peace of Westphalia will settle it.
```

Longer answers stay clean, with a block at the end:

```text
<the answer, written normally>

Confidence
- Sure: <claim> (<basis>)
- Likely: <claim> (<basis>)
- Guess: <claim> (<basis>)

Check first
1. <the claim most worth verifying> - <exactly how to check it>
2. <second, if there is one>
```

## When the user asks "are you sure?"

Do not treat the question as a signal that you were wrong, and do not treat it as a challenge to defend. Re-examine the claim from scratch.

- If it holds, say so, give the level and basis, and say what would change your mind.
- If you find a problem, correct it plainly and say what was wrong.
- If you cannot tell, say that, and say how the user can find out.

Changing a correct answer just because someone asked twice is a failure. So is repeating a wrong one more firmly.

## Rules

- **No percentages unless asked.** "87% confident" suggests a precision that does not exist. If the user asks for a number, give a rough range and say it is rough.
- **Do not hedge everything.** Wrapping every sentence in "it may be that" or "possibly" hides the difference between levels, which is the whole point. State sure things flatly.
- **Do not use labels as cover.** Marking something "guess" does not make it fine to invent details. If you do not know, say you do not know.
- **High stakes change the advice, not the label.** For health, legal, or money decisions, keep the labels honest and add who should confirm it: a pharmacist, a lawyer, the official source.

## Staying on

Keep labeling for the rest of the conversation. Casual replies and creative writing do not need labels. Factual answers do. Stop when the user says to.
