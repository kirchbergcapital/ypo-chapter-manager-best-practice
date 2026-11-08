Purpose: build your own Chapter Manager assistant in three short labs — in the workshop, or alone at your desk in about 40 minutes.
You leave with an assistant in your desktop app that follows your house rules, a chapter folder it keeps for you, a first short version of your chapter facts, and one email filed, logged and drafted.
The labs run in the **desktop app** — ChatGPT (Work) or Claude (Cowork), whichever you have; the assistant saves every file itself. No desktop app today? Every lab has a *Browser path*: the same steps, and you save the files yourself.

## Before you start

- **Your laptop, ready from the pre-workshop check** ([`../00-before-the-workshop/pre-workshop-selftest.md`](../00-before-the-workshop/pre-workshop-selftest.md)): the ChatGPT or Claude desktop app installed and signed in with a paid plan, training on your data switched off, and one working folder `CM-Workspace` inside your synced OneDrive or Google Drive — with this kit unzipped in `CM-Workspace/_kit`.
- The second prerequisite: chapter accounts in Microsoft 365 or Google Workspace for you and your Chair (`manager@`, `chair@`). Not there yet? Build in your own drive today and move the folder later — the request to your Chair is in [`../05-officer-handover/role-accounts.md`](../05-officer-handover/role-accounts.md).
- A phone works for chats and drafts on the go, not for building the folder.
- If the plan or the app is not ready on the day, work with your neighbour and set it up the same evening.

## At a glance

| Lab | Minutes | You build | In the workshop |
| --- | --- | --- | --- |
| A | 20 | Desktop task + core rules; the assistant builds your folder and saves a **short** `chapter-facts.md` that answers your yearly question | KNOW block |
| B | 12 | One fictional Lakeside email → filed → logged → reply drafted | REACH block |
| C | 4 in the workshop · 8 alone | A checkpoint in `handover.md` that a new chat can read | PERSIST block |

The full chapter-facts interview (8 questions, about 30 minutes) is your homework for tonight — the short version gets you through the labs.

Two words used in every check: **saved** = you can see the file in your folder · **drafted** = the text is in the chat, not yet a file.

---

## Lab A — Your assistant knows your chapter (20 min)

| Min | Step |
| --- | --- |
| 0–4 | **Open your working folder in the desktop app** — exactly as in your self-test: a new task with the folder `CM-Workspace` (ChatGPT: Work · Claude: Cowork `[verify the menu name]`). Allow access to `CM-Workspace` only; with Claude, keep the app open while it works. **Paste the core** from [`cm-assistant-instructions.md`](cm-assistant-instructions.md) (everything below the line) as your first message. If it asks for `house-rules.md`: "Not yet — the next prompt creates it." |
| 4–9 | **Let it build your chapter folder.** Send prompt 1, answer its questions and say yes. |
| 9–17 | **Your chapter facts, short version.** Send prompt 2 and answer six short questions from memory. Unsure? Say "verify". |
| 17–20 | **Test it.** Send prompt 3 with the question you brought. Then open `CM-Workspace` in Finder or File Explorer: your chapter folder and `chapter-facts.md` are there. |

**Prompt 1**
```
My chapter folder does not exist yet — set it up now, inside this folder (CM-Workspace). Ask me, one at a time, for anything you don't know yet: my name, my chapter, the chapter year (for example 2026–27). Suggest a folder name ending in -chapter and confirm it with me. Then copy _kit/02-your-assistant/template-folder there and replace the name, chapter and year placeholders in the copy. Never overwrite an existing folder; leave _kit unchanged. From now on, that folder is my chapter folder: every path in my house rules starts there. Show the saved path and the ten numbered folders, then stop. Send nothing.
```

**Prompt 2**
```
Read house-rules.md in my chapter folder. Then ask me these questions, one at a time: 1) chapter-year dates and the officer-change date; 2) the next standard event and its month; 3) the one channel officers use to reach me; 4) the role that approves spending; 5) where the bylaws and guidelines live; 6) the one question I answer every year when a new officer starts, and my short answer. "Verify" is a complete answer: write [verify] and move on. Show me the page, then save it as 02-chapter-knowledge/chapter-facts.md in my chapter folder, with today's date as "Last checked". Show the saved path, then stop.
```

**Prompt 3** — type your yearly question where it says so:
```
Read 02-chapter-knowledge/chapter-facts.md in my chapter folder now. Using only that file, answer: <your yearly question>. Quote the line you used and give the file path. If you cannot read the file, say UNCHECKED.
```

**Tonight, optional:** make it a project, so the core loads by itself in every new task — paste the core into the project instructions and add `CM-Workspace` to the project `[verify the menu name]`; in ChatGPT keep the memory setting at the default (project-only memory switches off Work). Until then, start a new task with the core as the first message.

**Browser path** (no desktop app today): create a project in the browser, paste the core and upload [`template-folder/house-rules.md`](template-folder/house-rules.md) with your name, chapter and year filled in. Then the folder: first the download test from Station 2 of the [AI guide](../AI-GUIDE.md) — your assistant hands you the whole chapter folder as one ZIP to unzip into your storage; if downloads fail, copy [`template-folder/`](template-folder/) yourself into `CM-Workspace` and rename it `<chapter>-chapter` ([`folder-structure.md`](folder-structure.md)); every file your assistant writes in the chat, you save with the box *Saving a file* in § 2 of the [AI guide](../AI-GUIDE.md). Ask prompt 2's six questions, save the page as `02-chapter-knowledge/chapter-facts.md`, upload it to the project and ask prompt 3. What is only **drafted** in the chat today is homework, not a failure.

The page your assistant writes in prompt 2 looks like this:

```markdown
# Chapter facts — {{CHAPTER}} (short version, Last checked: {{TODAY}})
- Chapter year: {{START}} to {{END}}; officers change on {{DATE}}
- Next standard event: {{EVENT}}, {{MONTH}}
- The one channel officers use to reach me: {{CHANNEL}}
- Who approves spending: {{ROLE}}
- Bylaws and guidelines live at: {{PLACE}}
- The question I answer every year for new officers: {{QUESTION}} — {{SHORT_ANSWER}}
```

A finished, fictional page to compare with: [`../examples/chapter-facts.md`](../examples/chapter-facts.md).

**Success check**
- [ ] The ten folders exist — in the chapter's storage, or for now in your own (the bridge).
- [ ] `02-chapter-knowledge/chapter-facts.md` is **saved** — you can see it in your folder (browser path: and uploaded to the project).
- [ ] Your assistant answers one question from it and names the file.

**Next step:** Lab B.

## Lab B — One email, handled the same way every time (12 min)

You practise on the fictional Lakeside Chapter, so the steps are copy, paste, file — and nothing real is at stake.
You play Jamie, its fictional Chapter Manager — the draft will be in Jamie's voice. Your assistant holds your own chapter facts, not Lakeside's — so expect [verify] marks in Jamie's draft; that is the assistant being honest, not failing.

| Min | Step |
| --- | --- |
| 0–2 | **Open the practice pack:** [`lab-b-practice-pack.md`](lab-b-practice-pack.md) — the prompt below, a late member question and the invented rules it needs, in one block. |
| 2–5 | **Paste the whole block** into your desktop task and send it. |
| 5–9 | **Let it save three things** — in the same task as Lab A. Type `Save all three now.` and say yes: the email in `06-communication/inbox-filed/` (name ending in `.md`), the log line at the bottom of `00-handover/log.md` with "practice" as topic, the reply draft in `06-communication/drafts/`. Open the folder and check. Browser path: you save the three texts yourself — the log line goes at the bottom of `log.md`, never in place of it. |
| 9–12 | **Read the draft.** It should cite the bylaws sections, promise no seat, and notice that Section 4.1 does not say whether partners pay like guests. Every [verify] is a fact the assistant could not source. You do not send in the lab. |

```
New email below, followed by our rules. 1) Say which folder it belongs in and give a file name with its extension (YYYY-MM-DD_sender-role_topic.md).
2) Give me one log line for 00-handover/log.md.
3) Draft a reply in my voice; answer only from the rules below and cite the section; mark every fact without a source as [verify]. I send it myself.
---
{{PASTE_EMAIL}}
---
{{PASTE_BYLAWS_EXCERPT}}
```

This is the kit's one email-handoff prompt — the same text is in [`../03-communication/email-handoff.md`](../03-communication/email-handoff.md) and prompt 11 of the [prompt library](../08-prompts/prompt-library.md). With a real mail that touches no rule, write `no rules needed` under the second `---`.

Browser path, no folder at hand? Ask your assistant: *"Create the Lakeside practice folder as one ZIP to download (examples + the ten empty folders)."*

**Success check**
- [ ] The email has a file name with `.md` and is **saved** in `06-communication/inbox-filed/`.
- [ ] One log line is **saved** at the bottom of `00-handover/log.md`.
- [ ] One reply is **saved** in `06-communication/drafts/` — it cites Sections 4.1 and 4.2, promises no seat, and is not sent.
- Only **drafted** in the chat so far? That is homework for tonight, not a failure.

Once your first real email is filed, move the practice files to `09-archive`.

**Next step:** Lab C. After the workshop: the same prompt with your own mail, then let the assistant read your mailbox directly and file without copy-paste — see [`../03-communication/email-handoff.md`](../03-communication/email-handoff.md) and [`../07-connectors-and-browser/email-connectors.md`](../07-connectors-and-browser/email-connectors.md).

## Lab C — Your memory survives a new chat (4 min in the workshop · 8 min alone)

In the workshop, Lab C is steps 1 and 2 in 4 minutes; the "Chairs rotate" round right after it is step 3, the proof. Alone, run all three steps in about 8 minutes.

Timings below are for working alone; in the workshop, steps 1–2 take 4 minutes.

| Min (alone) | Step |
| --- | --- |
| 0–3 | **Checkpoint.** Paste: `Checkpoint now. Refresh 00-handover/handover.md: what is set up, open items (each with what "done" looks like), paths touched. Then stop.` |
| 3–6 | **Check the file** `00-handover/handover.md` — the assistant saved it (browser path: save it yourself and upload it to the project). Add your open items from today — for example "run the full chapter-facts interview" and "move the folder into the chapter account". |
| 6–8 | **Prove it.** Start a **new** task with `CM-Workspace` and send the restart prompt below with the question *"What is open, and what does done look like?"* If it lists today's items, your memory now lives in the folder, not in the chat. |

**The restart prompt** — for every new task with `CM-Workspace`; it loads your house rules from the folder, so you do not paste the core again:
```
Read house-rules.md in the folder ending in -chapter here — not the one in _kit — and follow it. Then, from that same chapter folder, read 00-handover/handover.md and 02-chapter-knowledge/chapter-facts.md and answer only from them: <your question>
```

**Success check**
- [ ] `00-handover/handover.md` is **saved** — you can see it in your folder (browser path: and uploaded to the project).
- [ ] Each open item says what "done" looks like.
- [ ] A **new** chat lists today's open items, from the file.

**Next step:** the list *Tonight or this week* below.

**Debrief question:** What in this file could only you have written? That is your method — it goes with you.
The folder holds the chapter's facts, so a stand-in or the next officer can continue; your method stays yours — see [`../05-officer-handover/what-stays-yours.md`](../05-officer-handover/what-stays-yours.md).

---

## Success: three things you can show

1. **Your assistant answers a question from `chapter-facts.md`** — and names the file.
2. **The folder structure stands in the chapter's cloud storage** — or in yours, with "move to chapter account" as an open item in `handover.md`.
3. **One email is filed, logged and drafted** — saved in the folder; not sent. Only drafted in the chat? Homework for tonight.

In the workshop you show these three to your neighbour in pairs — 60 seconds each. Then everyone marks their own result on the wall poster — three dots: running today, or homework tonight. Nobody is checked.

## Plan B

| If | Then |
| --- | --- |
| Paid plan not ready on the day | Watch with your neighbour and follow every step on their screen. Set up your own plan the same evening and repeat the labs — about 40 minutes, the files stay the same. |
| The desktop app does not work today (no install rights, Work switched off in your workspace, iPad or Chromebook) | Take the *Browser path* in each lab: the assistant shows the text and the path, you save the file. Move to the desktop app later — [`../01-foundations/three-levels.md`](../01-foundations/three-levels.md). |
| The app asks for permission | Allow access to `CM-Workspace` only, and read what the app asks for. With Claude, keep the app open while it works. |
| No chapter cloud account yet | Build the folder in your own Drive or OneDrive today. Put "move to chapter account" in `handover.md`. [`../05-officer-handover/role-accounts.md`](../05-officer-handover/role-accounts.md) shows the ExCo request. |
| Your laptop blocks the AI tool | Use a private laptop today, or the browser path. Move the folder into the chapter account afterwards. |
| No laptop | Pair up. One types, both answer — then swap. |
| Wi-Fi is down | Use the files from the pre-workshop pack and a phone hotspot. The trainer runs the steps on the screen; you repeat them tonight. |
| Time runs short | Lab A with three lines of chapter facts: next standard event, the one channel, chapter year. The rest tonight. |

## Tonight or this week

- Run the full interview in [`chapter-facts-interview.md`](chapter-facts-interview.md) (about 30 minutes) and let it replace the short version. Clear one [verify].
- File your first real email with the Lab B prompt — the second time is quicker.
- Add your bylaws and one event playbook: [`../04-knowledge-base/knowledge-base.md`](../04-knowledge-base/knowledge-base.md).
- Take the AI-use one-pager to your Chair: [`../06-chapter-rules/ai-use-one-pager.md`](../06-chapter-rules/ai-use-one-pager.md).
