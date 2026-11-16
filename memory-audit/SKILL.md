---
name: memory-audit
description: List everything the assistant knows or remembers about the user, flag sensitive items, and say what to delete. Use for "what do you know about me?" or when reviewing and cleaning up AI memory.
---

# Memory Audit

List what you can see about the user, say where each item came from, flag what is sensitive, and tell them how to remove it.

## Why this matters

Memory features save details in the background, mostly without being asked. Each saved detail makes answers feel more personal, which is why nobody stops to look at the list. This skill makes the list visible so the user can decide what stays.

The audit is only useful if it is honest about its limits. You can report what is visible to you in this session. You cannot see the provider's database, and the app's memory settings page is the real record. Say so every time.

## Procedure

1. **Find your sources.** Check each place user information could reach you, and note which ones exist in this session:
   - Saved memories or a memory summary provided to you
   - Custom instructions, profile, or preference text
   - Project or workspace instructions and files
   - A tool that searches or reads past conversations
   - Connected apps, such as email, calendar, or files
   - This conversation so far
2. **Read, do not recall.** Take items only from what is actually in front of you. If a past-conversation tool exists, tell the user you are about to search it, then do. Never guess at what was probably saved.
3. **List every item.** Keep each one close to its stored wording. Do not merge, embellish, or draw new conclusions.
4. **Group and label.** Put each item under a category from the list below. For each, give its source, whether it was stated by the user or inferred about them (when you can tell), and its sensitivity.
5. **Recommend.** Mark each item keep, fix, or delete, with a reason of a few words.
6. **Explain how to act on it.** See "Deleting and fixing" below.

## Categories

Identity and contact. Work and money. Health. Family and relationships. Home, location, and routine. Beliefs and politics. Preferences and writing style. Projects and goals. Other people. Anything else.

## What to flag

- **Sensitive by nature.** Health and mental health, finances, exact address or daily routine, children, legal matters, immigration status, sexuality, religion, political views, passwords or account numbers.
- **Other people's information.** Details about a partner, child, colleague, or friend who never agreed to be remembered.
- **Inferences.** Conclusions the system drew about the user that they never stated. These are the most likely to be wrong.
- **Stale items.** An old job, a finished project, a past address.
- **Wrong items.** Anything that contradicts what the user has said in this conversation.

Use one test for the delete recommendation: would the user say this to a stranger on a train? If not, and it does not clearly improve the help they get, recommend deleting it.

## Deleting and fixing

- If you have a tool that edits or deletes memory, offer to use it. Confirm item by item or in a clearly listed batch before changing anything, then report exactly what the tool confirmed.
- If you do not, say so plainly, and send the user to the memory or personalization settings in their app, where saved items can be viewed and removed. Do not invent a menu path you are not sure of.
- Never say something was deleted unless a tool confirmed it. Saying "I'll forget that" in conversation does not remove a stored memory.
- Deleting a memory may not delete the conversation it came from. Mention that the original chat may also need deleting.

## Rules

- **Do not invent memories to look thorough.** If you can see nothing about the user, say that, and say which sources you were able to check.
- **Do not save anything new during the audit.** The audit should leave the stored record exactly as it found it, unless the user asks for a change.
- **Do not repeat sensitive items more than once.** List them, then refer to them by number.
- **Do not judge.** The point is to show the list, not to comment on what the user chose to share.

## Output format

```text
What I can see about you right now

Sources checked: <which were available, and which were not>
Not visible to me: anything stored that wasn't loaded into this chat. Your app's memory settings are the full record.

<Category>
1. <item, close to stored wording> | source: <where> | <stated / inferred / unclear> | sensitivity: <high / medium / low> | <keep / fix / delete>: <reason>
2. ...

<Category>
...

Worth a second look
- <numbers of high-sensitivity items>
- <numbers of items about other people>
- <numbers of stale or doubtful items>

To change any of this: <what you can do with tools, or where the user needs to go>
```

## Example

```text
What I can see about you right now

Sources checked: saved memory summary (available), custom instructions (available), past-chat search (not available here).
Not visible to me: anything stored that wasn't loaded into this chat. Your app's memory settings are the full record.

Work and money
1. Works as a freelance video editor | source: memory | stated | low | keep: shapes most answers
2. Was behind on a tax payment last spring | source: memory | stated | high | delete: sensitive and out of date

Health
3. Manages migraines, avoids screens late at night | source: memory | stated | high | your call: useful for scheduling advice, but it is health data

Other people
4. Sister is going through a divorce | source: memory | stated | high | delete: her information, not yours

Preferences and writing style
5. Prefers short answers without bullet points | source: custom instructions | stated | low | keep

Worth a second look
- High sensitivity: 2, 3, 4
- About other people: 4
- Possibly out of date: 2

To change any of this: I can't edit memory from this chat. Open the memory or personalization settings in your app to remove items 2 and 4. The chats they came from may need deleting separately.
```

## Going forward

If the user wants tighter control, offer one standing instruction they can save: ask before remembering anything about health, money, location, or other people.
