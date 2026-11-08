# 10 · Where my hours go — time by area

Purpose: see where your working time goes — member communication, events, officers and ExCo, region and global YPO, administration and the rest — as a by-product of the work your assistant already does with you.
Time: about 15 minutes to start (your areas and the two house rules); then a few seconds per task and a few minutes at the end of a day. The optional hours app takes 30 to 60 minutes to build the first time.
Level: 1 from day one — any paid AI tool. Level 2 lets the assistant save the lines itself. The app is optional (see [`../01-foundations/three-levels.md`](../01-foundations/three-levels.md)).

Tool facts: as of 22 Oct 2026. The hours app was tested in reference builds (Oct 2026): the self-test showed 0 failed and every check of the walk-through passed in Chrome. Your first build still takes 30 to 60 minutes; `0 failed` is the check, the number passed varies.

**Your numbers, for your own planning and for a conversation with your Chair about priorities and scope.** You decide which view you show; nothing goes to anyone automatically; no comparison with other chapters.

After each finished task, your assistant offers one short line with the area, the task and a suggestion for the minutes. You confirm or correct the minutes — only what you confirm counts.
At the end of the day the confirmed lines go into one file in **your own folder**. At the end of the month a report shows your hours by area and by event.
The hours log is yours ([`../05-officer-handover/what-stays-yours.md`](../05-officer-handover/what-stays-yours.md)); you decide what you share — usually the report, not the raw log — within the chapter's rules. If the chapter employs you, its own working-time records come first; this log is your personal view next to them, kept where the chapter's rules allow `[check your contract]`.

| File | What it is for |
|---|---|
| [`areas-template.txt`](areas-template.txt) | The default list of areas — your starting point for `areas.txt` |
| [`BUILD-PROMPT.md`](BUILD-PROMPT.md) | The one prompt for the optional hours app: three files, opened by double-click, no install |
| [`CHECKLIST.md`](CHECKLIST.md) | Ten ticks before you use the app for real |
| [`TROUBLESHOOTING.md`](TROUBLESHOOTING.md) | The usual bumps — folder, saving, import, Excel |

The prompts live in the library, group I: [23 Areas interview · 24 Hours line round-up · 25 Month report by area · 26 Workload assessment](../08-prompts/prompt-library.md#i--time-by-area).
The rules your assistant follows are house rules 19 and 20 in [`../02-your-assistant/template-folder/house-rules.md`](../02-your-assistant/template-folder/house-rules.md).

## The hours line

One line per finished task, always in this form — your assistant writes it, the app can read it, and you can read it too:

```text
HOURS · YYYY-MM-DD · <area> · <event folder or -> · <task in a few words, roles not names> · <minutes> min · suggested|confirmed
```

A line from the fictional Lakeside Chapter:

```text
HOURS · 2026-11-12 · Learning and chapter events · 2026-12-04_holiday-dinner · venue headcount to venue manager · 20 min · suggested
```

| Part | What goes in |
|---|---|
| `HOURS` | Marks the line, so it is easy to find and to paste |
| Date | The day you did the work, `YYYY-MM-DD` |
| Area | One area from your `areas.txt`, written exactly as there |
| Event | The event folder name from `03-events/`, or `-` when the task belongs to no event |
| Task | A few words, roles instead of names: *"reply to member question on guests"*, *"officer note"* |
| Minutes | Whole minutes, then `min` |
| Status | `suggested` when the assistant offers it, `confirmed` once you say the minutes are right. **Only `confirmed` counts** |

## The areas

The default list in [`areas-template.txt`](areas-template.txt) — prompt 23 turns it into your own:

| Area | What belongs here | Not here |
|---|---|---|
| Member communication | Newsletters, member mails and chats, being reachable | Event invitations → Learning and chapter events |
| Learning and chapter events | Planning, invitation, registration, on the day, follow-up, the learning calendar | Forum dates → Forum logistics |
| Forum logistics | Dates, rooms, the forum calendar, organising moderator training | Any Forum content |
| Membership lifecycle | Prospects, onboarding, renewals, roster, dues | |
| Officers ExCo and board | Meetings, minutes, officer training, the elect process and election, the handover at the start of the chapter year | |
| Game plan commitments and reporting | Commitment scorecard, charter, bylaws, strategic plan, forum data and reports in the Chapter Management Hub, reports to the region | |
| Region and global YPO | Regional meetings and calls, global communication, requests from the region or global YPO | Reporting → Game plan commitments and reporting |
| Finance and administration | Invoices, budget, contracts, tools, filing | |
| Knowledge base handover and own learning | Documentation, playbooks, Chapter Manager trainings | |

Travel is not an area: travel time goes to the area the trip is for.
Forum time is logged as activity only (*"dates coordinated"*, *"moderator training organised"*) — never with a forum name, a person or a topic, not even abbreviated.

## Three levels

| Level | How the hours line works | Setup |
|---|---|---|
| **1 · Chat project** | The assistant offers the line after each task and asks you to confirm. At the end of the day it lists your confirmed lines as one block; you paste it at the bottom of `hours.csv` (or into the app) | House rules 19 and 20, your areas — about 15 min |
| **2 · Living folder** | The same, and the assistant adds each confirmed line to `hours.csv` in your own folder itself | Your tool also gets access to your own hours folder |
| **Optional · your own hours app** (not a level) | A small page on your laptop: one button per area as a timer, an import box for the assistant's lines, today · week · month, a month report to print or save as PDF | Your AI tool builds it from [`BUILD-PROMPT.md`](BUILD-PROMPT.md) — a chat that hands you files is enough; no install, no account, no internet |

You can stay at Level 1 for good. The app only makes it more comfortable; it works with any level in [`three-levels.md`](../01-foundations/three-levels.md).

## Six steps — and one optional

### 1 · Make your hours folder (5 min)

In **your own** storage — your own OneDrive or Google Drive, or the Documents folder on your laptop — create a folder `my-work/hours/`.
If your OneDrive came with your chapter account, use Documents on your laptop instead.
Not inside the chapter folder (unless the chapter's rules say otherwise): your hours log is your personal analysis, and the chapter folder is shared with `chair@`.

Put two files into it:

- **`areas.txt`** — a copy of [`areas-template.txt`](areas-template.txt) for now; step 2 makes it your own.
- **`hours.csv`** — a text file with this one first line:

```text
date,start,minutes,area,event,task,source,status,entered_at,ref
```

Creating the files: in mode B your AI tool does it after your yes. By hand: Notepad (Windows) — *Save as type: All files*, *Encoding: UTF-8* — or TextEdit (Mac) — *Format → Make Plain Text* — then save under the exact name.
Using the app (step 7)? It creates both files for you when they are missing.

### 2 · Your own areas (10 min)

Run prompt **23 · Areas interview** from the [library](../08-prompts/prompt-library.md#23--areas-interview) in your daily project. Your assistant asks at most five questions —
your contract scope from `01-role-and-calendar`, your chapter facts, your own words — and gives you your `areas.txt`: about ten areas, each with a few keywords.
Save it in your hours folder. Upload it to your project at Level 1, so the assistant uses your areas.

### 3 · Two house rules in your `house-rules.md` (2 min)

House rule 19 (hours are yours, only confirmed hours count) and rule 20 (the hours line) are part of
[`../02-your-assistant/template-folder/house-rules.md`](../02-your-assistant/template-folder/house-rules.md) since 22 Oct 2026.
Copied your house rules before that? Copy the section *Game plan and hours* from that file into your own `house-rules.md`, in place of the old one.
Test in a fresh chat: *"What do you do after a finished task?"* — the answer names the hours line and that only confirmed minutes count.

### 4 · Your first hours line (1 min)

Do one real task with your assistant — a mail handoff, a checkpoint. At the end it offers the line with `suggested` and asks for your minutes.
Answer *"yes"* or with your own number (*"35"*). It repeats the line with your minutes and `confirmed`. Nothing else to do.
Not today? Say *"no hours today"* and it stops asking for this session.

### 5 · End of the day (2 min)

Run prompt **24 · Hours line round-up** at the end of every chat you worked in, or keep one chat per day. You get your confirmed lines twice: once as `HOURS ·` lines (for the app's import box) and once as rows for `hours.csv`. Without the app you only need the second block.
Level 1: open `hours.csv` in Notepad or TextEdit — not in Excel. Click at the very end of the file; if the cursor is not on an empty line, press Enter; then paste the rows and save. Level 2: the assistant has already added them.

### 6 · End of the month (5 min)

Run prompt **25 · Month report by area** with your `hours.csv`. You get your hours by area and by event, and the hours from your event comms logs listed separately, so nothing is counted twice.
Task texts stay out unless you ask for them. This report is what you share — with your Chair when you talk about priorities and scope, or with nobody: your choice.

### 7 · Optional: your own hours app (30–60 min the first time)

Open [`BUILD-PROMPT.md`](BUILD-PROMPT.md), copy the prompt into your AI tool and let it build three files into your hours folder: `hours.html`, `hours-core.js` and `self-test.html`.
A tool with folder access (Claude Code, Codex, the Claude desktop app with folder access, ChatGPT Work in the desktop app) writes them straight into the folder; a chat in the browser (Claude, ChatGPT) hands them to you as downloads, and you move them into `my-work/hours/`.
With ChatGPT Plus, the chat is the way; Codex only after Station 11.

1. **Open `self-test.html`** in **Chrome or Edge** — on a Mac: right-click → *Open With* → Google Chrome; on Windows: right-click → *Open with* → Microsoft Edge. It shows something like `60 passed, 0 failed`; **`0 failed`** is what counts. Any failed line? Copy the failing lines into your AI tool and ask it to fix the app until it shows `0 failed` — tools that cannot run code themselves (a chat) often need one such round.
2. **Open `hours.html`** the same way and click **Pick my hours folder** → choose `my-work/hours` → allow *edit* when the browser asks. You pick the folder again in each new session — one click.
3. Tick [`CHECKLIST.md`](CHECKLIST.md) once.

From then on: click an area to start its timer, click **Stop**, check the minutes, save — or paste the assistant's lines into the import box. Everything is written into `hours.csv` in your folder; the file is the truth.

## Where your hours live

| File | Where | Good to know |
|---|---|---|
| `hours.csv` | Your own folder, `my-work/hours/` | One row per confirmed entry. New rows go at the bottom; a change is a new correcting row, so your history stays readable. In the app, **Correct** and **Delete** add these rows for you and show each entry with its current minutes. Opens in Excel too |
| `areas.txt` | Same folder | One area per line, keywords after a colon. Change it whenever your work changes; old rows keep the area they had |
| The month report | Wherever you save it | Totals by area and by event — this is what you share |
| Event hours in `comms-log.md` | The chapter folder, in each event folder | As before: you write them, or confirm the assistant's suggestion. They feed the event debrief ([`../04-knowledge-base/event-lifecycle.md`](../04-knowledge-base/event-lifecycle.md) § 3) — the app and prompt 25 read them and never write there |

A change at Level 1 is one more row at the bottom. Five minutes less for the example line above, after it was saved with 20 minutes as the first row of your log — `ref` points to that row (its `entered_at`, or `row:1` for a row you pasted without one):

```text
2026-11-12,,-5,Learning and chapter events,2026-12-04_holiday-dinner,correction: venue headcount to venue manager,manual,correction,,row:1
```

Or ask your assistant for the correction row.

## For a conversation with your Chair

Four views help when you talk with your Chair about priorities and scope. Ask prompt 25 for the one you want to show:

- **Hours by area, month by month** across the chapter year (its start date is in `chapter-facts.md`).
- **Event work and base work:** rows with an event folder, and rows without one.
- **Planned and ad hoc** *(optional)*: start the task with *"ad hoc:"* when the work came in unplanned — asked by an officer, the region or a member. The line stays the same; use it only if it helps you.
- **Who asked** *(optional)*: start the task with *"for region:"* or *"for global:"* when the region or global YPO asked for the work — a form, a survey, a report, a training. Both can go together, *"ad hoc:"* first: *"ad hoc: for region: board data entry"*. Your assistant adds them only when you say so (house rule 20).

## When someone asks about your workload

Regions, working groups and Chairs sometimes ask Chapter Managers how much time each kind of work takes — training, event administration, surveys, reporting, short-notice requests.
Estimates from memory are hard to give. A few weeks of hours lines turn them into your own measured numbers — quicker to give and easier to discuss:

- **26 · Workload assessment** ([library, group I](../08-prompts/prompt-library.md#26--workload-assessment)) fills such a template from your `hours.csv` — hours per month for each activity, shown with the rows behind them. Benefit and improvement ideas stay yours: the assistant asks, it never rates for you.
- **27 · Request check** ([library, group E](../08-prompts/prompt-library.md#27--request-check)) sorts a new request in five minutes: what is asked, what your chapter folder already holds for it, in the order of the form's fields — what it will cost you, and a friendly reply that can offer a provisional answer when a deadline does not fit your chapter.
- **28 · Procedure change summary** ([library, group C](../08-prompts/prompt-library.md#28--procedure-change-summary)) turns new guidance into five lines — what changes, from when, which of your files to update — so your knowledge base stays the one place you look things up.

Same rule as always: your numbers, your folder, and you decide who sees them.

## Forum, and other people's time

> Forum is sacred. We use AI for Forum logistics only: dates, places, headcounts, costs, deadlines. Never for what is said in or around a Forum: topics, stories, notes, retreat conversations, anything shared in confidence, or any link between a name and a topic. If in doubt, leave it out.

For your hours: Forum work goes into **Forum logistics** with a neutral task — *venue booking*, *retreat travel*. The log holds your own time.

## Good to know

- **Chrome and Edge save straight into your folder.** Safari and Firefox open the same app with two buttons instead — **Open hours.csv** and **Download my log** — and a banner counts the entries not saved to file yet. The download has its own name, such as `hours-2026-11-12-1405.csv`: rename it to `hours.csv` yourself when you are sure it is the newest copy. On a Mac, install Chrome; treat Safari as a stopgap.
- **Use the app in one tab.** A second tab shows *"The app is already open in another tab"* and does not save — switch to the first one.
- **The app has no internet connection at all.** It is a page on your laptop; it reads and writes only the folder you pick, and reads your chapter folder only when you pick it for comms-log hours.
- **The assistant suggests; you decide.** A suggestion that is never confirmed never counts — not in the file, not in the report.
- **Excel opens `hours.csv`.** If everything lands in one column, see [`TROUBLESHOOTING.md`](TROUBLESHOOTING.md).
