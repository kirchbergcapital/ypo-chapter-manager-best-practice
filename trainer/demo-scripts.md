# Demo scripts

Purpose: the four live demos and the 1-minute outlook in the order they appear in the workshop — each with script, preparation, risk and fallback, so they survive questions and tool hiccups.

Order in the 120-minute plan ([format-guide.md](format-guide.md)):

| Demo | Block | Minutes | Shows |
|---|---|---|---|
| D4a | KNOW | 4 (min 23–27) | Assistant answers a bylaws question from the room with a source — and says UNCHECKED when it can't |
| D1 | REACH | 6 (min 54–60) | Email handoff in the desktop app: mail → file name → log line → draft, all three saved into the folder by the assistant, not sent |
| D2 | REACH | 5 (min 60–65) | WhatsApp, stage 1: chat export → summary saved in the event folder → one-to-one drafts |
| D4b | PERSIST | 4 (min 84–88) | The new Learning Officer asks in the first person; a brief from the folder that ends with an UNCHECKED gap |
| Outlook | Show & outlook | 1 (min 114–115) | One 60-second video: your own WhatsApp app (D2 stage 2), browser agent on the mock portal (D3), Canva — no live demo |

## Ground rules for every demo

| Rule | Why it helps |
|---|---|
| **Fictional data only on the projector** — the fictional chapter in [../examples/](../examples/), your demo accounts, your test chats | You can show everything without a second thought, and the room can copy it tonight |
| **A demo account, not your own** — a separate demo task and demo folder, and fictional senders | Your real inbox and chats never appear on screen by accident |
| **Never show a real member portal on the projector** — the browser demo runs on the local mock portal in [demo-assets/mock-portal/](demo-assets/mock-portal/README.md) | Same reason; plus you avoid live log-ins in front of a room |
| **The assistant drafts; you never press send** — say it out loud each time | It is the habit you want them to copy |
| **Close each demo with:** "This is in the kit — try it tonight." | Moves the room from watching to doing |

### The desktop set-up — the same for every demo

The workshop runs in the **desktop app** — ChatGPT (Work) or Claude (Cowork), whichever you use; the room has both. The point of every demo: the room **sees the file appear in the folder**.

| Point | How |
|---|---|
| Demo folder | One folder on your laptop, e.g. `Lakeside-Demo`, with the fictional chapter folder inside (template folder + the files from [../examples/](../examples/) + `house-rules.md`). Open it in the desktop app and allow access on T-1, so no permission prompt appears in front of the room |
| Demo task | A task in the desktop app with the demo folder, the core from [../02-your-assistant/cm-assistant-instructions.md](../02-your-assistant/cm-assistant-instructions.md) as its first message — the same way the room works in Lab A. A project that loads the core by itself is fine if you rehearsed it `[verify the menu name]`; in ChatGPT keep its memory at the default — project-only memory switches off Work |
| Projector | App on the left half, Finder (Mac) or File Explorer (Windows) with the demo folder on the right half. Point at the right half when a file appears |
| Fallback | The browser project with the same files uploaded, then screenshots — say it plainly: *"Same assistant, I save the file myself here."* |

### Interruption rule

- **A question during a demo:** answer in one sentence or write it on the parking-lot sheet ([format-guide.md § Parking lot](format-guide.md#parking-lot-and-yes-and)) — "great, it goes on the wall". Finish the demo first.
- **The tool fails:** give it **60 seconds** — one retry, nothing more. Then switch to the backup (screenshots or the 30–45-second video), say "this is what it looks like, it's in the kit", and move on. Never debug in front of the room.
- **Slow response:** talk through what the assistant is doing while you wait; if it passes 60 seconds, treat it as a failure.
- **The demo runs long:** cut the debrief question, not the next lab.

### Backups

Keep a folder `demo-backups/` **on your own laptop** (it is not part of the kit): for each demo 3–4 screenshots and one 30–45-second screen recording, made during your rehearsal on T-1. Also keep the backups on a USB stick or offline in case the Wi-Fi fails.

---

## D4a — Bylaws question (KNOW block)

**Purpose:** the assistant answers from the chapter's own files, names the source — and admits when the files don't say.

**Setup (before the session)**
- The demo task and demo folder from *The desktop set-up* above, with the core and [`house-rules.md`](../02-your-assistant/template-folder/house-rules.md) filled in for the fictional chapter.
- Files in the demo folder, visible on the right half of the projector: the fictional bylaws excerpt in `02-chapter-knowledge/` and [../examples/chapter-facts.md](../examples/chapter-facts.md). Point at the bylaws file while the assistant quotes it.
- The question comes from the room. Still pick **two questions** in advance as a backup: one the bylaws excerpt answers clearly, one it does not touch. Read the excerpt yourself first, so you know at a glance whether the room's question is covered.

**Script**

| Step | You say / do | What the room sees |
|---|---|---|
| 1 | Ask the room: "How often a year do you get a bylaws question?" Then: "Give me one you get every year." Type it, in their words: | |
| | `What do our bylaws say about {{THE ROOM'S QUESTION}}? Quote the passage and name the file. If the files do not cover it, say UNCHECKED.` | Answer + quoted passage + file name — or UNCHECKED |
| 2 | Run your prepared question for the other outcome: if the room's question was answered, ask the one the files don't cover; if it was UNCHECKED, ask the one they do. | |
| | `What do our bylaws say about {{PREPARED QUESTION}}?` | The other outcome |
| 3 | "The UNCHECKED answer is the one that makes this safe to use." | |
| 4 | 45 seconds: `Save this answer and its source as demo-answer.md in the demo folder.` Point at the file as it appears: "You ask, the assistant saves, you check." | The first file appears — before Lab A |

**Debrief question:** "Which question do you answer most often that should be answered from a file?"

**Preparation:** run both questions on T-1. If the assistant invents an answer to question 2, tighten the house rules (rules 2 and 11) and run again — that is a good story to tell, too.
**Risk:** the assistant answers question 2 from general knowledge about YPO instead of saying UNCHECKED.
**Fallback:** show the screenshots; say "if yours guesses, the house rules are the fix — here is the line". Point to [../04-knowledge-base/keeping-it-true.md](../04-knowledge-base/keeping-it-true.md).

---

## D1 — Email handoff (REACH block)

**Purpose:** one email, handled the new way: right folder, file name, log line, reply draft — and nobody sends but the CM.

**Setup (before the session)**
- **The demo mail** as a short text, ready to paste — from the fictional examples in [../examples/](../examples/), e.g. a speaker confirmation with one date and one open question. Show it in a demo inbox if you have one; reading the mailbox directly needs a mail connector — that is Station 9, not today ([../07-connectors-and-browser/email-connectors.md](../07-connectors-and-browser/email-connectors.md)).
- Sender in the mail: a fictional name, e.g. "Learning Officer, Lakeside Chapter (fictional)". Do not rename a real sender.
- **Demo folder and project** from *The desktop set-up* above.
- If you like the effect: send the same mail to your demo inbox from your phone 10 minutes before the block, and copy it from there.

**Script**

| Step | You say / do | What the room sees |
|---|---|---|
| 1 | "A mail from our Learning Officer just came in." Show it (demo inbox, or the text file) | The fictional mail |
| 2 | In the desktop app, in the demo task — the kit's one email-handoff prompt, with the mail pasted below it: | |
| | `New email below. 1) Say which folder it belongs in and give a file name with its extension (YYYY-MM-DD_sender-role_topic.md). 2) Give me one log line for 00-handover/log.md. 3) Draft a reply in my voice; mark every fact without a source as [verify]. I send it myself.` | Folder + file name, log line, draft with [verify] marks |
| 3 | Type: `Save all three now.` Allow the action if the app asks. Point at the right half while the files appear | The mail in `06-communication/inbox-filed/`, the new line at the bottom of `00-handover/log.md`, the draft in `06-communication/drafts/` — saved by the assistant |
| 4 | Open the draft from the folder. **Do not send.** "I would read it, change one word, and send it myself — from Outlook or Gmail." | Draft, unsent |

**Debrief question:** "Which three mails a week would you hand over like this?"

**Preparation:** rehearse with exactly this mail on T-1, in the same app, folder and project; allow folder access then, not in front of the room.
**Risk:** a permission prompt; a slow response; it drafts but does not save.
**Fallback:** say "Save all three now" once more; then switch to the browser project and save the three texts yourself — the room sees the same result, one step slower. The room does exactly this flow in Lab B, with the one-paste [Lab B practice pack](../02-your-assistant/lab-b-practice-pack.md).

---

## D2 — WhatsApp (REACH block)

**Purpose:** the WhatsApp chaos of an event — who is coming, who isn't, what was asked — turned into a summary and one-to-one drafts. The CM sends by hand.

**Stage 1, live:** WhatsApp's own *Export chat* (without media) of a test chat → a `.txt` file → read by the assistant in the desktop app. The small app a Chapter Manager builds with their AI tool (WhatsApp stage 2, Level 3) is part of the [outlook](#outlook--three-glimpses-in-one-minute) — a 1-minute glimpse or video, not built here.

**Setup (before the session)**
- A **test group** with fictional content, on your own number, with one willing colleague, named e.g. "Wine Dinner — Lakeside (fictional)", with 10–15 messages: two accept, one declines, one asks about parking, one asks to bring a partner. Or simply use the fictional export [../examples/whatsapp-export-event-group.txt](../examples/whatsapp-export-event-group.txt), which tells the same Wine Dinner story as the other Lakeside files.
- Export it to your demo laptop and keep the `.txt` on the desktop — **not** in the chapter folder. You attach it to the message in the desktop app. The chapter folder only ever gets the summary, in the event folder: `03-events/YYYY-MM-DD_wine-dinner/YYYY-MM-DD_whatsapp-summary.md`.

**Script**

| Step | You say / do | What the room sees |
|---|---|---|
| 1 | "A dozen messages, one dinner. Who is actually coming?" Show the export file | The raw chat |
| 2 | Attach the export file in the desktop app (drag it in), then: `Stop and tell me if the chat contains Forum content. Read the WhatsApp export I just attached. Give me a table: who confirmed, who declined, open questions (with who asked). Then draft one short one-to-one reply for each open question. I send them myself, one by one. Last, a summary of five lines or fewer for the event folder.` | Table + individual drafts + a short summary |
| 3 | "The assistant reads and drafts. You send — one person at a time." | — |
| 4 | Type: `Save the summary as 03-events/YYYY-MM-DD_wine-dinner/YYYY-MM-DD_whatsapp-summary.md.` Point at the right half when it appears. "The chapter keeps the summary. The chat and the export stay with you, outside the chapter folder." | The summary in the event folder, saved by the assistant |

**Debrief question:** "Which chat would you export first?"

**Optional, 30 seconds — the phone question.** Someone will ask about the iPhone. Hold up your phone with the same app and account: *"Ordinary chats and drafts work on your phone — read a message, ask for a reply draft, on the go. Today's folder task stays on the laptop, where the folder lives."* Then put the phone down. No live typing on the phone; never suggest the phone files into the folder.

**Preparation:** check the export works on the phone/desktop you use; menu names of the export differ by device ([verify] in [../03-communication/whatsapp.md](../03-communication/whatsapp.md)). Keep names in the test chat fictional.
**Risk:** export menu not where you expect it; the room asks "can it send for me?".
**Fallback:** the prepared export file from your laptop (or the fictional one in [../examples/](../examples/)). On "can it send?": "It could — and your number is your main channel, so you keep sending in your hands. That's the design."

---

## D4b — Handover brief (PERSIST block)

**Purpose:** a new officer gets a useful one-page brief in a minute — because the CM's folder holds the year. And where the folder is silent, the brief says so. The demo is asked in the first person, by the new Learning Officer, so it sets up "Chairs rotate" a few minutes later.

**Setup (before the session)**
- The demo task and demo folder (*The desktop set-up* above), with the fictional files in place and visible on the right half of the projector — point at each source file as the brief cites it: [../examples/handover.md](../examples/handover.md), [../examples/chapter-facts.md](../examples/chapter-facts.md), a commitments calendar made from the template in [../05-officer-handover/commitments-calendar.md](../05-officer-handover/commitments-calendar.md) and filled with fictional dates, marked "(fictional)", and a short fictional learnings file if available.
- The officer briefing template: [../05-officer-handover/officer-briefing-template.md](../05-officer-handover/officer-briefing-template.md).

**Script**

| Step | You say / do | What the room sees |
|---|---|---|
| 1 | "It's 1 July. I am the new Learning Officer — and I type my own question." | |
| 2 | `It's 1 July and I am the new Learning Officer. Write me a handover brief, one page maximum, using officer-briefing-template.md and only our files: chapter-facts.md, handover.md, the commitments calendar. Tell me what is open right now and what "done" looks like for each item, with the source file. Then answer my last question: who is confirmed as speaker for the Spring Retreat? If no file says it, write UNCHECKED.` | A structured brief with sources and [verify] marks — ending with UNCHECKED for the speaker |
| 3 | Point at the last line: "That gap is the most useful line on the page: it is now a to-do, not a surprise in July." | — |
| 4 | "I check the dates, then the chair sends it — from the chair@ address, so it stays with the role." | — |

**Debrief question:** "Which officer in your chapter changes next — and what would they need on page one?"

**Bridge to "Chairs rotate"** ([format-guide.md § Block 5](format-guide.md#block-5--persist-80106--question-3)): the checkpoint prompt starts before anyone moves; the "what stays yours" sentence and the one-pager pointer come before the switch; then the announcement: *"You stay with the laptop. The person who moves is the new officer on 1 July — ask only what these files can answer."* If only the Lakeside file is on a laptop, say it openly: *"This shows the method, not your chapter."*

**Preparation:** run it on T-1; check the deadlines it quotes against the calendar file.
**Risk:** the brief invents a deadline or a name not in the files — for example a Spring Retreat speaker.
**Fallback:** screenshots; or turn the slip into the lesson: "this is why rule 8 says: check numbers and dates against the file before they go out." Check on T-1 that no file in your demo folder names a Spring Retreat speaker; if yours does, pick another gap.

---

## Outlook — three glimpses in one minute

**Purpose:** show what Levels 2 and 3 can add — without a live demo, without set-up questions. One 60-second video (about 20 seconds per glimpse) at min 114–115. Details are in the kit; nobody needs them this month.

| Glimpse | What the room sees | Kit |
|---|---|---|
| Your own WhatsApp app (D2 stage 2) | A small app, built with an AI tool from the build guide, exports the fictional test chat into its own folder on the laptop — not the chapter folder. The assistant reads that export, drafts the replies and files only the summary in the event folder. Sending, if added, needs a confirmation for every single message | [../09-whatsapp-app-build-guide/](../09-whatsapp-app-build-guide/) |
| Browser agent (D3) | An agent reads the next three events from the **mock** member portal into a table | [demo-assets/mock-portal/](demo-assets/mock-portal/README.md) · [../07-connectors-and-browser/browser-agent.md](../07-connectors-and-browser/browser-agent.md) |
| Canva | Text from the event file, design from Canva | [../07-connectors-and-browser/canva.md](../07-connectors-and-browser/canva.md) |

**How to make the video (T-7):** record the three steps below on your demo laptop, then cut each to about 20 seconds — 60 seconds in total — fictional data only. Say the one line per glimpse live while it plays.
**Risk:** the room wants to try it now. **Answer:** "It's in the kit — after your first month with the desktop app."
**Stop mark:** min 115. If the show in pairs ran long, cut the outlook to one sentence. The outlook is the first thing you cut — before the walk-through, never "Chairs rotate".

### Your own WhatsApp app (D2 stage 2)

**Setup (for the recording):** build the app once on your demo laptop with [../09-whatsapp-app-build-guide/](../09-whatsapp-app-build-guide/), linked on your own number and reading only the fictional test group from D2. Record the app exporting the test group into its own `exports` folder, the assistant reading that file, and the summary landing in the event folder (`03-events/…/YYYY-MM-DD_whatsapp-summary.md`). A screenshot of its output is enough (about 20 seconds in the video).
**Line while it plays:** "You build this yourself with your AI tool, in an afternoon. The app reads and exports; your assistant summarises and drafts. If you add sending, it sends one message — only after you confirm that one."

### D3 — Browser agent on the mock portal

**Purpose:** a look at Level 2/3 — an AI agent that works in the browser for you, reading the next three events from a member portal into a table.

**Setup (before the session)**
- The **mock portal** in this folder: [demo-assets/mock-portal/](demo-assets/mock-portal/README.md) — a few static HTML pages of a fictional "Lakeside Chapter" member portal (dashboard, events, members, documents), every page marked as a fictional demo. No server, no login, no scripts. Keep the folder together so the stylesheet loads, and open `index.html` from disk. Never the real portal.
- A browser agent you are comfortable with (for example Claude in Chrome, or the cloud browser in ChatGPT Work — as of 21 Oct 2026, with sources in [../07-connectors-and-browser/browser-agent.md](../07-connectors-and-browser/browser-agent.md)).
- The expected answers are in the [mock portal README](demo-assets/mock-portal/README.md) — check the agent's table against them before you keep a recording.

**Script (for the recording)**

| Step | You say / do | What the room sees |
|---|---|---|
| 1 | Open the mock portal's `index.html`. "Imagine this is the portal you check every Monday." | The fictional portal with its demo banner |
| 2 | `Go to the Events page. List the next three events with date, venue and registrations, soonest first, as a table. Do not click anything that changes data.` | The agent reads the page, the table appears |
| 3 | Optional second prompt: `Which event is closest to capacity, and what is its RSVP deadline?` | One event, one date — both match the README |
| 4 | "In real life it works in your own browser, where you are already logged in — you watch, it reads, you decide." | — |

**Preparation:** run it twice on T-7 on your demo laptop; compare the table with the README; keep the best 20 seconds. In the room only the video runs.
**Risk (while recording):** agent slow, extension blocked, agent wanders off the page — record again.

---

### Canva visual

**Purpose:** show that the same event file also feeds the graphics many CMs already make in Canva.

**Setup:** the fictional event file (e.g. the Wine Dinner playbook) and either a Canva connection in the assistant (availability as of 21 Oct 2026, with sources in [../07-connectors-and-browser/canva.md](../07-connectors-and-browser/canva.md)) or simply Canva open in the browser.

**Script (for the recording, about 20 seconds in the video):**
`From the event file, write the text for an invitation card: title, date, venue, one line on why to come, RSVP via the one channel. Maximum 25 words.` → paste into a Canva template (or let the connector create a design) → "Text from the file, design from Canva, your eye on both."

**Fallback:** a screenshot of a finished card.
