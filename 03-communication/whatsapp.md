# WhatsApp — read faster, answer better, send yourself

Purpose: turn busy WhatsApp chats into a summary, a list of open questions and one-to-one reply drafts — in two stages, from "works today" to "runs on your laptop".
Time: 10 minutes a week at stage 1; building your own app for stage 2 takes one to two hours the first time, with your AI tool (the build itself takes minutes).

Tool facts: as of 21 Oct 2026, with sources; `[verify]` where we could not confirm on the provider's page.

**Your number, your chats.** You work with members from your own WhatsApp number. The chats stay on your phone and stay yours —
see [`../05-officer-handover/what-stays-yours.md`](../05-officer-handover/what-stays-yours.md).
What the chapter needs to keep — who comes, what was decided, what changed — goes from the chat into the chapter folder as a short summary:
**export → summary → file.** That way the chapter's memory is complete, and your phone stays your own.

## Forum stays out

> Forum is sacred. We use AI for Forum logistics only: dates, places, headcounts, costs, deadlines. Never for what is said in or around a Forum: topics, stories, notes, retreat conversations, anything shared in confidence, or any link between a name and a topic. If in doubt, leave it out.

For WhatsApp that means:

- **Forum groups, and any chat with Forum content, are never exported, uploaded or summarised.**
- **A mixed chat** — logistics and Forum in one thread — is not exported either. Type the logistics (date, place, headcount) into the event file by hand.
- **Forum content in an export by accident?** Delete the export. Do not summarise it.
- The prompt below starts with a stop line for this, and so does prompt 12 in the library.

## The two WhatsApp stages

The WhatsApp stages are not the kit's Levels 1–3: stage 1 works at any level; stage 2 needs an AI tool that can write and run code on your laptop (Level 3).

| Stage | What | Setup | Good for |
|---|---|---|---|
| **1 · Chat export** | WhatsApp's own "Export chat" → a text file → your assistant | None | Every CM, today |
| **2 · Your own small WhatsApp app** | You build it with your AI tool, following [`09-whatsapp-app-build-guide`](../09-whatsapp-app-build-guide/): it reads the chats you choose, summarises them and drafts replies | One to two hours the first time, Level 3 | CMs with many active groups |

At every stage: **the assistant reads and drafts. You decide what goes out — one message at a time**, from your phone or, with the optional send step of your own app, after you confirm that one message.

## Stage 1 — Export chat (official, works today)

1. In WhatsApp, open the chat → menu → **More → Export chat** → *without media* `[verify: menu path differs on iPhone and Android]`.
2. Keep the export outside the chapter folder — on your phone, or in your laptop's Downloads folder — named `YYYY-MM-DD_chat-name_topic.txt`, e.g. `2026-11-14_event-group_holiday-dinner.txt`. The chapter folder gets only the summary (below).
3. Upload it to your AI project (Level 1) or give your assistant the file (Level 2), and use this prompt:

```
Stop and tell me if the chat contains Forum content; do not summarise it.
Read the WhatsApp export {{FILE}} from {{DATE_FROM}} onwards.
1) Who confirmed, who declined, who has not answered — for {{EVENT}}. Names exactly as in chapter-facts.md
   or the event attendee list; if a name only appears as a phone number, write "unknown number", never guess.
2) Open questions that need my answer, each with the date it was asked.
3) Anything that changes a fact (date, venue, cost) — show it, do not update files yet.
4) One-to-one reply drafts for the open questions, short, in the language of each person. I send them myself.
5) A short summary for the event folder: RSVPs, decisions, changed facts — each with the date of the message.
6) One log line for 00-handover/log.md.
```

Save the summary in the event folder (`03-events/{{EVENT_FOLDER}}/YYYY-MM-DD_whatsapp-summary.md`). That file is what the chapter keeps; the chat stays on your phone, and you can delete the export afterwards.
The summary is a decision record: RSVPs, decisions, changed facts, each with its date. Names appear only with a role or an RSVP — never next to a topic.

**What good looks like:** a three-column attendance table, a short list of open questions, a few drafts of two or three lines each, and a summary of five lines or fewer for the event folder.
A fictional export to practise with: [`../examples/whatsapp-export-event-group.txt`](../examples/whatsapp-export-event-group.txt).

**Group posts:** if one message should go to the whole event group, ask for one group post — you post it yourself in the group.

## Stage 2 — Build your own small WhatsApp app with your AI tool

[`../09-whatsapp-app-build-guide/`](../09-whatsapp-app-build-guide/) is a build guide, not a ready-made program. You give its build prompt to your AI tool
(Level 3, see [`../01-foundations/three-levels.md`](../01-foundations/three-levels.md)), and together you build a small app that runs on your laptop.
It connects the way WhatsApp Web does, **reads** the chats you choose, **summarises** them and **drafts replies**, and saves its exports as Markdown files in its own folder on your laptop, outside the chapter folder.
Your assistant reads such a file exactly like a stage-1 export; only the summary goes into the event folder. Sending is an **optional** step you can add later: the app then sends one message only after you have confirmed that one message. WhatsApp can restrict a number that uses an unofficial client, and your chapter's or YPO's WhatsApp rules apply to both stages — where messages may not leave a group, that group is not exported.

The app uses Baileys, an open-source library that is not affiliated with WhatsApp; its own README discourages bulk or automated messaging
([npm: baileys](https://www.npmjs.com/package/baileys)).

WhatsApp's [messaging guidelines](https://www.whatsapp.com/legal/messaging-guidelines) (last updated 23 Sep 2026) ask users not to
"use unofficial clients, bulk messaging, auto-messaging, auto-dialing, or automation to harm WhatsApp or our users". The build guide keeps your app far from that line:
it reads at your own pace, drafts, and sends — if you add sending at all — only the single message you have just confirmed. The full rules for Europe: WhatsApp's [terms for the European Region](https://www.whatsapp.com/legal/terms-of-service-eea).

### Good habits

| Habit | Why it helps |
|---|---|
| **You confirm every send** | The app reads, summarises and drafts. If you add sending, each message goes out only after you confirm that one message — no bulk, no schedules, no automatic replies |
| **Personal pace** | Export a few chats when you sit down to work — not every minute, not all chats |
| **Keep what the chapter needs in the chapter folder** | Summarise decisions and RSVPs from WhatsApp into the event file — the chat itself stays on your phone |
| **Leave out what is not yours to read** | Forum groups, chats with Forum content and private conversations are never exported |

## A group charter — pin it in every group you run

A group runs more smoothly when everyone knows what it is for. Post this as the first message of each group you set up, pin it,
and keep a copy in `06-communication/templates/`. Adapt the purpose line; keep the rest.

```text
{{GROUP_NAME}} — what this group is for

Purpose: {{e.g. logistics for the holiday dinner — times, places, quick questions}}.
Everyone here said yes before being added. Know someone who should join? Ask them first, then tell me.
Your phone number is visible to everyone in this group.
Please share no sensitive documents here — no ID copies, contracts or bank details.
Decisions and payments go by mail, so the chapter has them on file. This chat is for the quick things.
Questions about the group: {{YOUR_NAME}}, Chapter Manager.
```

**Ask, then add.** Before you add someone, send a short one-to-one message — *"May I add you to the {{EVENT}} group?"* — and add the people who say yes.
Your assistant can draft these one-to-ones from the RSVP list; you send them.

## Your weekly 10 minutes

| Step | Time |
|---|---|
| Export the 2–3 active event groups (stage 1) or let your own app read them (stage 2) | 3 min |
| Summary + open questions + drafts with the prompt above; summary into the event folder | 4 min |
| Send the drafts (from your phone, or confirm each one in your app), add the log line | 3 min |

Ready-made prompt: "Chat-export summary" in [`../08-prompts/prompt-library.md`](../08-prompts/prompt-library.md).

**Asks hidden in chats** — a form to fill, a deadline, a request from an officer: the weekly *Incoming work sweep* (prompt 40) takes the exports you choose, together with your mail, and offers rows for your incoming work list. Same rules: your choice of chats, never a Forum group, exports outside the chapter folder.
