# Keeping it true

> A knowledge base is only useful while it is right. Four habits keep it right with little effort: sources feed the truth, open points are marked, logs only grow, and twenty minutes a month you check.

---

## 1 · Sources and truth

| | What it is | Examples | Rule |
| --- | --- | --- | --- |
| **Truth** | Your own files, kept current | `chapter-facts.md`, bylaws copy, `FAQ.md`, playbooks, learnings, `handover.md` | Edited in place the same day; every change gets a log line |
| **Sources** | What comes in from outside | Emails, WhatsApp exports, PDFs, exports from YPO tools, meeting notes | Saved unchanged with a date; cited when they change the truth |
| **History** | What happened and what was decided | `00-handover/log.md`, `00-handover/decisions.md` | Append-only |

The flow is always the same: **a source arrives → you or your assistant cite it → the truth is updated → one log line.**
An email that changes the venue does not "become" the truth. It is the reason the playbook changes.

## 2 · Marks that keep you honest

| Mark | Means | What to do |
| --- | --- | --- |
| `[verify]` | A fact the assistant could not source, or you were not sure of | Confirm with the owner, then replace the mark with the fact and its source |
| `[verify with Regional Manager]` | A rule question your files do not answer | Ask once; put the answer in `FAQ.md` with its source |
| `UNCHECKED` | A file could not be opened, or a reply has not come | Not fine, not failing — open. Check before anyone relies on it |
| `SOURCE MISSING` | A draft says something in a person's name without a file line or a message behind it | Find the source or take the line out before you send |

A mark is a tool, not a failure. It shows the next person exactly where the work is.

To see all of them at once:

```
List every [verify], UNCHECKED and SOURCE MISSING in the chapter folder.
For each: file, line, what is missing, and who could confirm it (role).
```

## 3 · Logs only grow

`log.md` and `decisions.md` are append-only. New lines go at the bottom. Nothing is rewritten.

A correction is a new line that points to the old one (fictional example):

```
2026-11-03 · holiday dinner · venue email · start time set to 19:00 · send invitation
2026-11-05 · holiday dinner · venue email 2026-11-05 · correction of 2026-11-03: start time 19:30 · update invitation draft
```

Why it matters: a year from now, a new Chair asks "why did we move the dinner?". The log answers in one line, with the source. Nobody has to remember.

`handover.md` is the one page you may rewrite. It shows the current state and points to the log for history.

## 4 · The monthly check — 20 minutes

Put a repeating 20-minute slot in your calendar, for example the first working Monday of the month.

| Min | Step |
| --- | --- |
| 0–5 | Run the prompt below |
| 5–15 | Decide each proposal: yes, no, or ask someone. Clear the [verify] marks you can clear right now |
| 15–20 | Let the assistant apply the yes-items, add log lines, and refresh `handover.md` |

```
Monthly check. Read 02-chapter-knowledge, 00-handover, and the log lines of the last 30 days.
1) List every [verify] and UNCHECKED, with who could clear it (role).
2) Officers, dates or events that changed in the log or in 06-communication / 07-reporting but not in chapter-facts.md. Cite both files.
3) Facts that appear in two files with different values. Cite both.
4) Files in the wrong folder, or names that break YYYY-MM-DD_topic.
5) Learnings lines from the last month that should change a playbook.
Propose every edit as a list. Change nothing until I say yes.
Then apply the approved edits, add one log line per change, and refresh 00-handover/handover.md.
```

## 5 · After every event: learnings

Within two days of each event, while it is fresh. It takes five minutes and it is the single best gift to next year's officers.
Working with the event template? The longer debrief with numbers and hours is prompt 18 — see [`event-lifecycle.md`](event-lifecycle.md).

```
Event done: {{EVENT}} on {{DATE}}. My notes: {{NOTES}}
(attendance, what members said, what went wrong, what to keep, costs against budget).
1) Append 3–7 dated lines to 02-chapter-knowledge/learnings-{{ROLE}}.md, each as: what worked · what did not · what we change next time.
2) Propose edits to the playbook for this event in 02-chapter-knowledge. Mark them as proposals.
3) Give me one log line for 00-handover/log.md.
4) Draft a thank-you to the host or speaker for me to send. Use no member's feedback by name.
```

Ask the officer who owned the event to add their own lines to their learnings file — or send you three bullet points and let the assistant append them.
When the role changes, the next officer reads that file first.

## 6 · When two sources disagree

It happens every month: the playbook says one thing, a new email says another. Settle it in five steps.

1. **Put both side by side**, each with its source and date. Your assistant does this when you ask: *"These two disagree. Show both with source and date."*
2. **Ask who owns the fact.** Newer is not automatically right. The source from the owner wins:

   | Kind of fact | Who owns it |
   | --- | --- |
   | Rules and bylaws | The current signed bylaws; YPO guidance from its official source, with its date |
   | How the chapter does things | The ExCo, through a line in `decisions.md` |
   | Event details | The venue's or supplier's latest written confirmation |
   | Who holds a role | The officer table in `chapter-facts.md`, confirmed by the Chair |
   | Money | The budget file and the invoice |

3. **Cannot tell?** Mark the fact `[verify]`, ask the owner in one short message (your assistant drafts it), and add an open item to `handover.md`.
4. **Decided?** Update the truth file, add a line to `decisions.md` if it was a decision, and a log line that names both sources.
5. **Fix the cause.** If the old value came from a playbook, update the playbook too, so it does not come back next year.

## 7 · At the officer change

If you kept these habits, the handover is the folder: `handover.md` on top, the logs for history, the learnings files for each role.
The checklist for the change itself: [`../05-officer-handover/handover-checklist.md`](../05-officer-handover/handover-checklist.md).

*Patterns from chapter practice. Not official YPO material.*
