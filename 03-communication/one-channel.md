# One channel to the Chapter Manager

Purpose: all requests from the ExCo reach you through one agreed channel, so you get one prioritised list instead of five competing ones.
Time: one conversation with your Chair, one friendly message to the officers.

## The problem, from your side of the desk

A familiar pattern across chapters: several officers each send their own requests — by mail, WhatsApp, a call in the evening.
Each request is reasonable. Together they collide, and nobody sees the whole list except you.
You end up setting the chapter's priorities without having been asked to.

## From both sides of the table

| | |
|---|---|
| **The chair's view** | A chair rarely sees how many requests reach the Chapter Manager in a week. One channel makes the load visible — and gives the chair the job of setting priorities, which is where that job belongs |
| **The regional view** | Across many chapters, the same lesson holds one level up: when regional mail goes to everyone on every channel, it gets lost. One main channel per audience works better |
| **What made it better** | One channel, one weekly list, one person who decides when two requests collide |

## What "one channel" means

| Element | Agreement |
|---|---|
| **The channel** | One place where ExCo requests reach the CM: a role mailbox (`manager@<chapter-domain>`), or one named thread. Best is a channel that leaves a record in the chapter folder, so the weekly list writes itself |
| **The gate** | Requests go via the Chair or a named person, who sends you a prioritised list |
| **The rhythm** | One list a week, at a fixed time. Urgent means: today, with a reason |
| **Collisions** | When two requests compete, the Chair decides — not you |

This is rule 1 of the operating guardrails in [`../06-chapter-rules/operating-guardrails.md`](../06-chapter-rules/operating-guardrails.md).
The guardrails cost no money; they ask for discipline. Your Chair can propose them at the next ExCo.

## How to introduce it — friendly, not as a complaint

**Step 1 — Talk to your Chair first (10 minutes).** Bring one example week: how many requests, how many channels.
Your assistant can count them from `00-handover/log.md`:

```
Read 00-handover/log.md for the last 4 weeks. Count the requests from officers by channel (mail, WhatsApp, call, other)
and by officer role. Show a small table and the two weeks with the most collisions. Roles only, no names.
```

**Step 2 — The Chair (or you, with the Chair's OK) sends one message to the officers:**

```text
Subject: How we work with {{CM_NAME}} this year

Dear all,

To make sure every request gets the attention it deserves, we are trying one simple rule this year:
please send requests for {{CM_NAME}} to {{CHANNEL — e.g. manager@chapter-domain}}, or to me.
Every {{WEEKDAY}} {{CM_NAME}} receives one prioritised list, and when two things compete, I decide.

Urgent things still work — just say why it is urgent.

Thank you — this gives all of us faster answers.
{{CHAIR_NAME}}
```

**Step 3 — Your weekly list (5 minutes with your assistant):**

```
Read the requests filed since {{LAST_WEEK_DATE}} in 06-communication/inbox-filed/ and the log.
Make one list: request · from (role) · due · effort (S/M/L) · conflicts with.
Sort by due date. Mark collisions for the Chair. Draft a short message to the Chair with the list. I send it.
```

**Step 4 — Keep it kind when someone forgets.** A one-line reply does it:
*"Thank you! I've added it to this week's list for {{CHANNEL}} — {{CHAIR_ROLE}} will confirm the priority."*

## The weekly officer note

One channel brings requests in. The weekly officer note sends one picture back out — once a week, for example on Friday, to all officers on the agreed channel:

| Part | What it says |
|---|---|
| **What went out** | Messages and invitations sent this week |
| **What was agreed** | Decisions, each with its line in `00-handover/decisions.md` |
| **What was paid** | Amounts, each with its receipt or invoice |
| **What went quiet** | Requests and threads still waiting for an answer, with the owner (role) |

Your assistant drafts it from the log, the decisions file and the receipts list — prompt 22 in [`../08-prompts/prompt-library.md`](../08-prompts/prompt-library.md).
You read it, change what needs changing, and send it. Officers stop asking "what did we decide?", and the note itself lands in the chapter folder.

## Members are different

One channel is for **requests from the ExCo**. Members can still reach you the way they like. For members, the habit is:
mail for what is binding (dates, payments, registrations), WhatsApp for what is short (reminders, quick questions).
Patterns for both: [message-templates.md](message-templates.md) · [whatsapp.md](whatsapp.md).

Next: [message-templates.md](message-templates.md).
