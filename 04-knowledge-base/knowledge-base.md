# Knowledge base

> What your chapter knows, in one folder, in plain files your assistant can read. So "how do we do X?" gets the same answer in March as in October — and a stand-in or the next officer finds it without calling you.

---

## 1 · What it is

Your knowledge base is the folder `02-chapter-knowledge` inside the chapter folder ([`../02-your-assistant/folder-structure.md`](../02-your-assistant/folder-structure.md)).
It holds what is **true and reusable**. Your assistant reads it before it answers. Everything else in the chapter folder — emails, exports, drafts — is a source that feeds it.

## 2 · What goes in

| File | What it holds | Starts from |
| --- | --- | --- |
| `chapter-facts.md` | The chapter on one page: year, officers, standard events, budget lines, channels, deadlines | [`../02-your-assistant/chapter-facts-interview.md`](../02-your-assistant/chapter-facts-interview.md) |
| `game-plan.md` | The chapter's goals from the Game Plan: metric, tracking source, owner (role), status, evidence. You track it; the chapter commits; the Chair owns delivery | The empty file in [`../02-your-assistant/template-folder/02-chapter-knowledge/game-plan.md`](../02-your-assistant/template-folder/02-chapter-knowledge/game-plan.md) · [`../05-officer-handover/game-plan-keeping.md`](../05-officer-handover/game-plan-keeping.md) |
| Bylaws | The chapter's bylaws: the original PDF **and** a Markdown copy with page numbers | The current signed version |
| Operating guidelines | How the chapter works in practice: who approves what, lead times, the one channel to the Chapter Manager | [`../06-chapter-rules/operating-guardrails.md`](../06-chapter-rules/operating-guardrails.md) |
| `FAQ.md` | Questions members and officers ask again and again — each with a short answer and its source | The last three questions you answered twice |
| Event playbooks | One file per standard event: timeline back from the date, venue and supplier notes, run sheet, checklist, budget line | Your best past event folder in `03-events` — the steps in [`event-lifecycle.md`](event-lifecycle.md) |
| Learnings, one file per role | `learnings-chapter-manager.md`, `learnings-learning-officer.md`, `learnings-membership-officer.md` … dated lines: what worked, what did not, what we change | The prompt in [`keeping-it-true.md`](keeping-it-true.md) after each event |
| Process playbooks | One file per recurring process you run every year, such as `process-board-registration.md` (incoming board registration, membership transfer, platform steps, a tool's how-to with dated workarounds) | Your own last run plus the official guidance |
| Platform field map | `platform-fields.md` — each screen field points at the chapter file that already holds the value | The first screen that asks — prompt 30 |

What stays in other folders: single emails (`06-communication`), exports (`07-reporting`), event working files (`03-events`), drafts.
What never goes in: passwords, members' private details (home addresses, ID or passport copies, health or family details), Forum content. The chapter's password manager, YPO Connect and the Forum itself are the right homes for those — the Forum rule in full: [`../02-your-assistant/folder-structure.md`](../02-your-assistant/folder-structure.md).

## 3 · Markdown, not a database

Write the knowledge base as Markdown files (`.md`): plain text with headings, lists and tables.

| Markdown files | A database or a new app |
| --- | --- |
| Every AI assistant reads them, at every level | Needs a connector, a licence, or an export |
| You read and edit them in any editor | Needs someone who knows the tool |
| They move with the folder at handover | Often tied to one person's login |
| A new tool next year reads the same files | A new tool next year means a migration |

Lists that look like tables — receipts, attendance — can be CSV files. Your assistant reads those too.

**Turning a PDF into Markdown.** Keep the original. Add a Markdown copy next to it:

```
Turn the attached {{DOCUMENT}} into Markdown for 02-chapter-knowledge.
Keep every heading and section number. Put the page number in brackets after each section, like (p. 4).
Change no wording. Mark anything you could not read as [verify].
At the top write: Source: {{FILE_NAME}}, version/date {{DATE}}, converted {{TODAY}}.
```

Then check three sections against the PDF yourself. If they match, the copy is good.

## 4 · One truth

Each fact lives in **one** file. Other files point to it.

- The date of the holiday dinner lives in `chapter-facts.md`. The playbook says "date: see chapter-facts.md".
- A rule lives in the bylaws copy. `FAQ.md` quotes it and names the section.
- Who holds a role lives in the officer table. Nowhere else.

Find the same fact in two places? Keep one, make the other a pointer. If the two disagree, [`keeping-it-true.md`](keeping-it-true.md) shows how to settle it.

## 5 · Where it lives: cloud, synced to your laptop from Level 2 on

**Recommendation:** keep the chapter folder in the chapter's cloud storage (Google Drive or OneDrive). At Level 1 that is all — you upload the key files to your AI project.
From Level 2 on, install the storage's desktop app so the same folder is synced to your laptop.

| Why cloud | Why also on the laptop |
| --- | --- |
| The chapter owns it, through a role account | Desktop AI apps (Level 2) open the folder directly — no uploading |
| Two admins, so nobody is the only key | Level 3 (Claude Code) works locally in the same folder |
| Backed up and shareable with officers | You work offline on a train; it syncs later |

At Level 1, you upload the key files (`chapter-facts.md`, `FAQ.md`, the bylaws copy, `handover.md`) into your AI project and refresh them when they change.
At Levels 2 and 3, the assistant reads and writes the synced folder itself. Same files, same structure — see [`../01-foundations/three-levels.md`](../01-foundations/three-levels.md) and [`../01-foundations/where-your-data-lives.md`](../01-foundations/where-your-data-lives.md).

One person edits a file at a time. Officers read; you and your assistant write.

## 6 · Asking it questions

```
{{QUESTION}}
Answer only from 02-chapter-knowledge. Quote file and section (and page for the bylaws).
If the files do not cover it, say so, write [verify with Regional Manager], and suggest where the answer should live once we have it.
```

When the answer is new and worth keeping, add it to `FAQ.md` with its source. Next time the question costs you nothing.

## 7 · From both seats

Patterns as chairs and regional officers tend to see them — no single chapter described.

| | Pattern |
| --- | --- |
| What worked | A reusable run sheet per event, kept and improved from year to year instead of rebuilt. |
| What did not | Three places to file things: a private inbox, a private drive, a WhatsApp chat. Every officer change started from zero. |
| What we improved | One chapter storage, one fixed structure, one file per fact. New officers read the folder before they ask. |


## 8 · Meetings: record them

Recording your chapter meetings — ExCo, officer calls, committee and planning calls — is the easiest way to keep what was said and decided.
YPO's Zoom records without extra tools; where your account also shows a transcript or an AI summary, keep that too `[verify for your account]`.

- **Say it at the start:** "We are recording; the notes will be taken from the recording." People know where the notes come from.
- **Save the source, keep the truth:** the transcript or summary goes with its date into `07-reporting/` or the event folder. Prompt 3 turns it into action items, a minutes draft and lines for `00-handover/decisions.md`.
- **Forum meetings are never recorded or transcribed.** Forum is sacred.
- Where your chapter or YPO has rules for recordings and AI notetakers, they apply.

## Prompts for your AI

- *"Read 02-chapter-knowledge. Which standard events in chapter-facts.md have no playbook yet? Draft an empty playbook for the next one, from its folder in 03-events."*
- *"Here are three emails with the same question {{PASTE}}. Write one FAQ.md entry with the answer from our files and the source. Mark anything not in our files [verify]."*
- *"List every fact that appears in more than one file in 02-chapter-knowledge. Propose which file keeps it and where a pointer goes. Change nothing yet."*

*Patterns from chapter practice. Not official YPO material.*
