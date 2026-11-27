# Routines — work that runs while you are away

Five prompts (41–45) for work that comes back every day, week or month, and how to let your AI run them on a schedule.
**As of 19 Nov 2026** — menus move; where a button name may have changed, it says `[verify]`.

> **The rule that makes this work:** start with your house rules. Turn a task into a routine when you have explained it twice — and when the prompt has run by hand two or three times without a correction.

## 1 · Five rules for every routine

1. **Drafts only.** A routine never sends. Mails wait in your drafts, files wait in the folder — you read and send.
2. **House rules first.** Every run starts by reading `house-rules.md`, so the draft sounds like you.
3. **Unsure goes on top.** Anything the routine was not sure of — an owner, a date, a name it could not match — sits in a short note at the very top of the draft, for you to check before sending.
4. **One log line per run** in `00-handover/log.md`: date, routine, what it produced.
5. **Read the first three days of drafts in full.** After that, a quick look is enough. When you correct a draft, your assistant suggests a dated rule for `house-rules.md` (house rule 13); add it once you agree — the same mistake does not come back.

**On the tool list first.** Every connector a routine uses (mail, calendar, a task tool) is on your chapter's tool list — Part B of the [AI use one-pager](../06-chapter-rules/ai-use-one-pager.md). Forum content never goes into a routine.

## 2 · Where the data comes from

A routine only sees what is connected or saved. If the data is not there, the best AI cannot use it.

| Data | How the routine gets it |
|---|---|
| Mail, calendar, meeting transcripts | A connector to the chapter's Microsoft 365 or Google account ([`../07-connectors-and-browser/email-connectors.md`](../07-connectors-and-browser/email-connectors.md)) — or the file saved into the event folder |
| Event platform (registrations, surveys) | Download the export into the event folder first. A live question — "am I registered?" — needs the browser agent ([`../07-connectors-and-browser/browser-agent.md`](../07-connectors-and-browser/browser-agent.md)). Exports from YPO's own systems are YPO data — see [*YPO data or chapter data?*](../01-foundations/where-your-data-lives.md#ypo-data-or-chapter-data) |
| Pipeline, contacts | `04-members-and-prospects/pipeline.md` (prompt 31) or your mini CRM (Station 13) |
| Bank | A statement export you download yourself. The AI never signs in to a bank |

**Already have a task tool** (ClickUp, Planner, Asana, Monday)? Keep it, and connect it if it is on your tool list. **No tool yet?** You do not need to buy one: `pipeline.md` or your mini CRM is enough, and the routine turns it into the report the officers read.

**Before the first run,** ask your AI: *"Can you read my chapter folder and save a draft in my mailbox?"* If it cannot save drafts there, the drafts go into `06-communication/drafts/` instead — that works too.

## 3 · Setting up a schedule

**Start by hand.** Every prompt below works when you paste it — on Monday morning, after a call. That is how every routine starts, in any tool.

**Claude** ([source](https://support.claude.com/en/articles/13854387-schedule-recurring-tasks-in-claude-cowork)) — all paid plans:
1. In the Claude desktop app: **Scheduled** in the left sidebar → **New task** → *Create with Claude* (describe it in your words) or *Set up manually*.
2. Give it a name, paste the prompt, choose how often: hourly, daily, weekly, on weekdays, or manually.
3. **Choose your chapter folder** (the field *Which folder Claude should work in*). All five routines here read it. Where offered, *Require this computer* then switches on: the task runs only while your computer is awake and the Claude app is open. Save.
4. **Where it runs depends on your plan.** Tasks without a folder run in the cloud, also while your computer sleeps or the app is closed. On Pro, Max and Ultra — and on Team and Enterprise with Cowork in the cloud turned on — tasks you create on your computer move to the cloud automatically, and *Require this computer* is offered only to organizations with computer access turned on. A cloud task can run while your computer is off, but it reaches a folder on that computer only while the Claude app is open `[verify]`. So check the first run: if it could not read your chapter folder, keep running the prompt by hand for now.
5. A connector set to *Always ask* may wait for you or skip that step — check the first run.

**ChatGPT** — scheduling there is still changing:
1. In the ChatGPT desktop app, choose **Work**, describe what should happen and when, and check what it proposes `[verify]`. A task that works with files on your laptop runs only while the laptop and the app are on `[verify]`.
2. You find it again under **Scheduled** `[verify]`; if the desktop app does not show it, use chatgpt.com.
3. Unsure? Ask your AI to walk you through it, with a screenshot of what you see. ([source](https://help.openai.com/en/articles/20001275-chatgpt-work-and-codex))

## 4 · Prompts you already have that make good routines

| Prompt | Good rhythm |
|---|---|
| 3 · Minutes → action items | after each chapter meeting |
| 22 · Weekly officer note | weekly |
| 34 · Renewal follow-up list | weekly in renewal season |
| 40 · Incoming work sweep | every morning |

Numbers 1–40 are in [`prompt-library.md`](prompt-library.md).

---

## 5 · The routine prompts

### 41 · Meeting summary drafts after a chapter call
**Purpose:** after a chapter call, a summary with actions waits in your drafts. **When:** twice a day as a routine, or after one call by hand.
**Reads:** transcripts of chapter calls you organised — through the connector, or a transcript you saved into the event folder (a transcript from YPO's Zoom: see [*YPO data or chapter data?*](../01-foundations/where-your-data-lives.md#ypo-data-or-chapter-data)) · `chapter-facts.md` (who holds which role) · `house-rules.md`.
```text
Read house-rules.md. Find the chapter calls I organised since the last run that have a transcript and no summary yet.
Skip any Forum meeting. For each call, draft one email to the officers and staff on the invite:
- three to six lines: what we discussed and what we decided;
- actions as a list: what, owner (name and role), due date. Where no date was agreed, suggest one and mark it (suggested).
At the very top, for me only: anything you were not sure of - an unclear owner, a name you could not match -
and anyone else on the invite (speakers, guests, members), for me to decide whether they get it.
Use my greeting, layout and sign-off from the house rules. Save each draft; send nothing.
Add one line per call to 00-handover/log.md.
```
**Result file:** one draft per call in your mailbox, or `06-communication/drafts/YYYY-MM-DD_summary_{{CALL}}.md`.
**Your check:** every action has an owner and a date; you remove the note at the top before sending.

### 42 · Weekly pipeline report
**Purpose:** the officers see where every applicant stands — without asking you. **When:** every Monday morning.
**Reads:** `04-members-and-prospects/pipeline.md` (prompt 31) or the mini CRM export · the membership goal in `02-chapter-knowledge/game-plan.md`, if it is there.
```text
Read 04-members-and-prospects/pipeline.md and the membership goal in 02-chapter-knowledge/game-plan.md.
Write a one-page report:
1) Actual against the goal - if no goal is written down, say [verify] - and how many rows sit at each stage.
2) One row per person, from the columns of pipeline.md: initials, type, stage, next step, due, owner (role).
3) A short note only where a case needs background.
Initials only, as in pipeline.md. No home address, no health or family details.
Save it as 07-reporting/YYYY-MM-DD_pipeline-report.md and draft a short email with it to the Membership Officer and the Chair,
plus any other membership roles listed in chapter-facts.md. Send nothing. Anything the file does not state: [verify].
```
**Result file:** `07-reporting/YYYY-MM-DD_pipeline-report.md` · a draft email.
**Your check:** the numbers per stage add up to the rows in `pipeline.md`.

### 43 · Applicant brief before the interview
**Purpose:** the officer meeting a prospect has one page two days before. **When:** on request, or as a routine: *"Find prospect meetings in my calendar two days from now and take the initials from the title."*
**Only if** your Membership Officer wants briefs with public background — agree it once.
**Reads:** the prospect's row in `pipeline.md` · what the prospect supplied, in `04-members-and-prospects/`.
```text
Read the row for {{INITIALS}} in 04-members-and-prospects/pipeline.md and what the prospect supplied in that folder.
Write a one-page brief for {{OFFICER_ROLE}}, who meets them on {{DATE}}:
1) Type, stage, source and history so far - from our files only.
2) Public business background, in a separate section headed "Public, unverified": the company and the person's business role
   from the company website, press and their professional profile - each point with its source link.
   Nothing about family, health, politics, religion or private social media.
3) Three to five questions worth asking.
Nothing from a Forum. Save it as 04-members-and-prospects/YYYY-MM-DD_brief_{{initials}}.md (initials in lower case)
and draft a short email to the officer. Send nothing.
```
**Result file:** `04-members-and-prospects/YYYY-MM-DD_brief_{{initials}}.md` · a draft email.
**Your check:** the public section is marked unverified and every point has a link.

### 44 · Event feedback one-pager for the Board
**Purpose:** one page the Board can read in two minutes. **When:** when the survey closes.
**Reads:** the survey export (CSV or Excel) you saved in `03-events/{{EVENT_FOLDER}}/`. Good to know: an export from YPO's event platform is YPO data ([*YPO data or chapter data?*](../01-foundations/where-your-data-lives.md#ypo-data-or-chapter-data)); your own chapter survey is chapter data.
```text
Read the survey export in 03-events/{{EVENT_FOLDER}}/.
Write one page for the Board: overall score, response rate (responses / attendees), the three to five themes that came up most,
up to three short quotes word for word, and ideas worth keeping for the next event.
Respondents stay anonymous: no names, no details that point to one person.
Save it as 03-events/{{EVENT_FOLDER}}/feedback-summary.md and add the ideas to debrief.md in the same folder. Send nothing.
```
**Result file:** `03-events/{{EVENT_FOLDER}}/feedback-summary.md`.
**Your check:** the response rate matches the export; no quote names anyone.

### 45 · Payment check and reminder drafts
**Purpose:** which invoices are paid, which are open — and the reminders ready. **When:** once a month, after you download the bank statement.
**Only if** your chapter sends its own invoices and your Finance Officer agrees. The reminders go to the Finance Officer to approve — or out in their name, if your chapter prefers.
**Reads:** the bank statement export you saved in `05-finance/` · your invoice list (`05-finance/invoices.csv` or the folder of invoices).
```text
Read the bank statement export {{FILE}} and the invoice list in 05-finance/.
Match each payment to an invoice (amount, name, invoice number in the reference). Make three lists:
paid · still open · unclear (a payment you cannot match, or a match you are not sure of).
For each open invoice, draft a short, friendly reminder, one per person, with the invoice number.
Save the lists as 05-finance/YYYY-MM_payment-check.md. Send nothing; change no invoice.
```
**Result file:** `05-finance/YYYY-MM_payment-check.md` · reminder drafts for the Finance Officer.
**Your check:** three matches checked by hand against the bank; every "unclear" line is yours to decide.

---

*Community resource by a YPO member, not an official YPO resource. Share a routine of your own: see "Share a prompt" in [`prompt-library.md`](prompt-library.md#share-a-prompt).*
