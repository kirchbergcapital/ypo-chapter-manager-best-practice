# 04 · Knowledge base

> Build the chapter's knowledge in one folder of plain files — bylaws, guidelines, FAQ, event playbooks, learnings — and keep it true with a few small habits, so your assistant answers from your facts and the next officer finds them.

## What this is

How to fill `02-chapter-knowledge` (the folder from [`../02-your-assistant/folder-structure.md`](../02-your-assistant/folder-structure.md)) and how to keep it right.
No database, no new app. Markdown files in the chapter's cloud storage — from Level 2 on also synced to your laptop.
Every prompt works the same with OneDrive: where a prompt says "Drive", read your cloud storage — Google Drive or OneDrive.

## Why it matters

The same questions come back every year: "What do our bylaws say about guests?", "How did we run the summer event?", "Who approves this spend?".
Each answer costs you time — and when an officer changes, the answers walk out of the door.
A knowledge base turns each answer into a file. Your assistant quotes it. A stand-in or the next officer reads it.

## What's inside

| File | What it gives you | Use it when |
| --- | --- | --- |
| [`knowledge-base.md`](knowledge-base.md) | What goes in, why Markdown, one truth, where it lives (cloud; synced to your laptop from Level 2 on) | Setting it up — the first weeks |
| [`keeping-it-true.md`](keeping-it-true.md) | Sources vs. truth, the [verify] marks, append-only logs, the monthly 20-minute check, learnings after each event, how to settle contradictions | Every month and after every event |
| [`event-lifecycle.md`](event-lifecycle.md) | One event folder with eight files, the steps from T-90 to T+14 with a prompt for each, and how to make event hours visible | From the first idea for an event to the archive |

## How to use it with your AI

**1. Start the knowledge base**

```
Read 04-knowledge-base/knowledge-base.md and 02-chapter-knowledge/chapter-facts.md.
List the files our knowledge base should have, which ones exist, and which are missing.
Suggest the three to build first, starting with what I answer most often.
```

**2. Add the bylaws**

```
Turn the attached bylaws into Markdown for 02-chapter-knowledge.
Keep every heading and section number, add page numbers in brackets, change no wording.
Mark anything unreadable [verify]. Write the source file and its date at the top.
```

**3. After an event**

```
Event done: {{EVENT}}. My notes: {{NOTES}}
Append dated lines to 02-chapter-knowledge/learnings-{{ROLE}}.md: what worked · what did not · what we change.
Propose playbook edits. Give me one log line.
```

**4. Once a month**

Use the monthly-check prompt in [`keeping-it-true.md`](keeping-it-true.md).

## Time needed

A planning guide, not a measured study.

| Step | Time |
| --- | --- |
| Bylaws as Markdown, checked against the PDF | About 30 minutes |
| First `FAQ.md` with five questions | About 20 minutes |
| One event playbook from a past event folder | About 30 minutes |
| Learnings after an event | 5 minutes |
| Monthly check | 20 minutes |

Before this: [`../02-your-assistant/README.md`](../02-your-assistant/README.md). Next: [`../05-officer-handover/handover-checklist.md`](../05-officer-handover/handover-checklist.md).

*Patterns from chapter practice. Not official YPO material.*
