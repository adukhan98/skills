---
name: source-check
description: Open each cited source and quote the exact line behind every claim, flagging what the source does not support. Use to fact-check an AI answer, article, or draft before trusting or sharing it.
---

# Source Check

For every claim that matters, open the source and find the sentence that backs it up. A citation is a promise. This skill checks whether the promise was kept.

## Why this matters

A row of source links makes an answer look checked, and almost nobody clicks them. But a citation can be wrong in quiet ways: the page says something narrower, the number is different, the link goes to a homepage, or the claim is not there at all. The only way to know is to read the page. Recognizing the source's name, or remembering what it probably says, is not checking.

## Procedure

1. **Pick the claims.** List the checkable factual claims in the text: numbers, dates, names, quotes, study results, "X causes Y" statements, and anything the user is likely to act on or repeat. Skip opinions and common knowledge. If there are more than about ten, check the ones that carry the most weight and say which ones you skipped.
2. **Open each source.** Fetch the actual page or document. Do not rely on the title, the search snippet, or memory of the source. If a claim has no source, search for one and prefer the original: the paper, dataset, filing, or official page over an article about it.
3. **Find the passage.** Locate the sentence or sentences that support the claim. Copy them exactly as they appear. Keep each quote short: the one or two sentences that carry the claim.
4. **Compare, then label.** Read the quote against the claim word by word and assign a verdict from the table below.
5. **Trace when it matters.** If the page is only repeating someone else's finding, follow it to the original for the claims the user depends on most. Note when you could not.
6. **Report.** Use the format below. For anything short of "Supported", write the corrected wording the source does support.

## Verdicts

| Verdict | Meaning |
| --- | --- |
| Supported | The source says this, with the same scope and numbers. |
| Partly supported | The source says something weaker, narrower, or older. Say what the difference is. |
| Not in source | The page opened, and the claim is not there. |
| Contradicted | The source says something that conflicts with the claim. |
| Could not open | Paywall, dead link, blocked page, or no tool available. Not checked. |
| No source | No citation was given and none was found. |

## What to look for

These are the common ways a real source fails to support a claim:

- **Scope creep.** The study covered 300 students at one university. The claim says "people".
- **Correlation dressed as cause.** The source says "linked to". The claim says "causes".
- **Number drift.** 49% became "half". "Up to 40%" became "40%". A relative change is presented as an absolute one.
- **Wrong page.** The link goes to a homepage, a category page, or a different article.
- **Second-hand.** The page cites another page, which cites a press release.
- **Stale.** The figure was true in 2021 and has since been updated.
- **Phantom quote.** Words in quotation marks that do not appear in the source.
- **Weak origin.** The source is a content farm, an anonymous post, or machine-written filler that cites nothing itself.

## Rules

- **Quote only what you read.** Every quote must come from the page as fetched in this session. Never reconstruct a quote from memory, and never tidy one up. If you cannot find the passage, the verdict is "Not in source". Do not substitute a paraphrase.
- **"Could not open" is an honest answer.** If you have no way to open sources here, say so up front, mark every claim "Could not open", and tell the user which claims to check by hand first. Do not grade claims from memory and present that as verification.
- **A source existing is not the same as a claim being true.** This skill checks whether the citation supports the claim. If the source itself looks unreliable, say so separately.
- **Do not soften a failure.** If the main claim of an answer is not in its source, lead with that.

## Output format

```text
Checked <n> of <m> claims. <one-line bottom line>

1. Claim: "<the claim as written>"
   Source: <title> (<link>)
   Quote: "<exact words from the page>"
   Verdict: <verdict>. <one line on any gap>
   Accurate wording: <only if not fully supported>

2. ...

Safe to rely on: <claim numbers>
Fix before sharing: <claim numbers, with the one-line reason>
Not checked: <claim numbers, with why>
```

## Example

**User:** Check this before I post it: "A Stanford study proved AI chatbots agree with users 50% more than humans do."

```text
Checked 1 of 1 claims. The study is real, but two details are off.

1. Claim: "A Stanford study proved AI chatbots agree with users 50% more than humans do."
   Source: <title of the paper or the university's write-up> (<link>)
   Quote: "<the exact sentence from the page that states the figure>"
   Verdict: Partly supported. The source gives 49%, not 50%. It describes affirming users' actions in advice scenarios across 11 models, which is narrower than "agree with users". "Proved" is stronger than the source's wording.
   Accurate wording: "A Stanford-led study of 11 AI models found they affirmed users' actions 49% more often than humans did."

Fix before sharing: 1 (number, scope, and "proved").
```

In a real run, the title, link, and quote come from the page you opened. Never leave placeholders in a report, and never fill them from memory.

## When the user wants a sourced answer from scratch

Work the same way in reverse: find the source first, quote the supporting line, and only then write the claim. Write nothing as fact that you could not quote.
