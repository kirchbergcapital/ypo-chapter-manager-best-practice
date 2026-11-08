# Three levels

Purpose: help a Chapter Manager pick one of three setups — from a chat project in the browser to Claude Code in a local folder — and see what each gives and what it takes.
The house rules (`house-rules.md` at the top of the chapter folder, with the short core from [`../02-your-assistant/cm-assistant-instructions.md`](../02-your-assistant/cm-assistant-instructions.md) in your tool's instructions) and the folder structure stay the same at every level.
You can move up later without rewriting a single file.

Have the ChatGPT or Claude desktop app on your laptop? Start at Level 2 — the assistant saves its own work. Otherwise start at Level 1 in the browser this week, and move up when you notice yourself uploading the same files again and again.
Move to Level 3 only if you enjoy it. Most Chapter Managers run the role very well at Level 1 or 2.

Tool facts on this page: as of 21 Oct 2026, with sources. Menus move — `[verify]` marks what we could not confirm on the provider's own page.

## Choose first

| Your situation | Start here |
|---|---|
| You have the ChatGPT or Claude desktop app on your laptop | Level 2 — the assistant saves its own work from day one |
| You want something running this week, no install | Level 1 |
| You want to build your own small WhatsApp app and a folder that keeps itself tidy | Level 3 |
| Your laptop is locked down by someone else's IT | Level 1 on any browser; Level 2 later on a laptop you control |

## At a glance

| | Level 1 · Chat project | Level 2 · Living folder, connected | Level 3 · Claude Code in your folder |
|---|---|---|---|
| **Who it suits** | Every CM, day one | Day one with a desktop app; otherwise after a few weeks | CMs who like to tinker, or have a technical helper |
| **What it does** | Answers from your uploaded files, drafts mails and texts | Reads and writes your synced chapter folder; reaches your mail, Drive and Canva; works in your browser | Works directly in your local folder, keeps it tidy; builds your own small WhatsApp app with you |
| **Where it runs** | Browser only | Desktop app + browser | Desktop app or terminal |
| **Setup time** | 15 minutes | 30 minutes for app and folder; connectors later, 30 minutes each | An afternoon |
| **Needs** | A paid AI plan, the folder structure. No sync app — the browser is enough | A paid AI plan + the ChatGPT or Claude desktop app + your storage's desktop (sync) app; connectors optional | Level 2 (incl. the sync app) + Claude Pro, Max, Team or Enterprise |
| **You keep doing** | Copy and paste, upload changed files | Read, check, send | Read, check, send |

## Level 1 — A chat project (browser only)

**Who it suits.** Every Chapter Manager, from day one. No install, no sync app. Works on any laptop with a browser.

**What it does.** A project in your AI tool holds your house rules and your key files. Every chat inside it starts informed.
You paste a mail; it suggests the folder, a log line and a reply draft. You copy the result into your files.

**Setup (15 minutes)**

1. Create a project: Claude → Projects · ChatGPT → Projects · Copilot → Notebooks · Gemini → Gems → new Gem (the core goes into its instructions, the files into its knowledge). Menu names differ by product `[verify]`.
2. Paste the core from [`../02-your-assistant/cm-assistant-instructions.md`](../02-your-assistant/cm-assistant-instructions.md) into the project's instructions.
3. Upload `house-rules.md`, `chapter-facts.md`, `handover.md` and your bylaws. Claude takes files up to 30 MB each ([source](https://support.claude.com/en/articles/8241126)); ChatGPT takes 25 files per project on Go and Plus, 40 on Pro, Business, Enterprise and Edu ([source](https://help.openai.com/en/articles/10169521-projects-in-chatgpt)).
4. First prompt: *"List the files you can see. Read chapter-facts.md, then tell me in three lines what you know about my chapter."*

**What it takes.** Files do not update themselves. When `chapter-facts.md` changes, upload it again.
Treat the chat as the workbench and the folder as the record.

## Level 2 — A living folder, connected

**Who it suits.** A Chapter Manager who files mails every week and wants the assistant to save its own work.

**What it does.** The assistant reaches the places where your work already is:

| Connection | What you gain | Facts |
|---|---|---|
| **Your chapter folder** | The assistant reads and writes the synced folder on your laptop: files mails, appends log lines, updates `handover.md` | Claude Cowork: paid plans, desktop app for macOS and Windows; the app stays open while it works ([source](https://support.claude.com/en/articles/13345190)) · ChatGPT Work in the ChatGPT desktop app (which plans and systems `[verify]`): works with local files after you allow it; Work can use a project's context, but not in a project set to project-only memory ([source](https://help.openai.com/en/articles/6825453-chatgpt-release-notes)) |
| **Mail and calendar** | It reads a mail in your mailbox and leaves a draft reply there. You send | Gmail, Calendar, Drive for all Claude users ([source](https://support.claude.com/en/articles/10166901)) · Microsoft 365 for work accounts; on Team and Enterprise the Claude owner enables it and an admin switches on write tools ([source](https://support.claude.com/en/articles/15183774)). Details: [`../07-connectors-and-browser/email-connectors.md`](../07-connectors-and-browser/email-connectors.md) |
| **Canva** | Event visuals from your text, in your Canva account | [`../07-connectors-and-browser/canva.md`](../07-connectors-and-browser/canva.md) |
| **Your browser** | It reads portal pages you are logged into and turns them into tables | Claude in Chrome, paid plans ([source](https://support.claude.com/en/articles/12012173)). See [`../07-connectors-and-browser/browser-agent.md`](../07-connectors-and-browser/browser-agent.md) |

**Setup (30 minutes, plus connectors later)**

1. Install your storage's desktop app so the chapter folder is on your laptop — see [where-your-data-lives.md](where-your-data-lives.md).
2. Install the ChatGPT or Claude desktop app and open the chapter folder there (ChatGPT: Work · Claude: Cowork) `[verify the menu name]`.
3. Put the core from [`../02-your-assistant/cm-assistant-instructions.md`](../02-your-assistant/cm-assistant-instructions.md) into the project instructions or where the app keeps standing instructions `[verify the menu name]`; the app reads `house-rules.md` from the folder.
4. Connect your mailbox. Start with one connector; add the next when the first one runs.
5. Test: *"Add one line to 00-handover/log.md: today's date · setup · level 2 · folder connected · first mail handoff."* Open the file yourself and check the line is there.

**What it takes.** History is only as good as the append-only habit: logs get a new line, never an edit.
One person edits at a time. Every draft still waits for you.

## Level 3 — Claude Code in your folder

**Who it suits.** A Chapter Manager who enjoys the step, or has a technically confident helper. Never required.

**What it does.** Claude Code works directly in your local chapter folder: it files, renames, checks the log, rebuilds overviews
and keeps the structure clean. `CLAUDE.md` in the folder loads at every start and points to `house-rules.md`.
Here you can also build your own small WhatsApp app with Claude Code — it reads your chats, summarises them and drafts replies;
sending is optional and needs your OK for every single message.
See [`../09-whatsapp-app-build-guide/`](../09-whatsapp-app-build-guide/) and [`../03-communication/whatsapp.md`](../03-communication/whatsapp.md).

**Plan.** Claude Pro, Max, Team or Enterprise — not Free ([source](https://code.claude.com/docs/en/setup)).

**The way without a terminal.** The Claude desktop app offers Claude Code with a normal window ([source](https://code.claude.com/docs/en/setup)).
Open the app, switch to Claude Code, pick the chapter folder `[verify the menu name]`. That is the whole install.

**Install in the terminal** (source: [code.claude.com/docs/en/setup](https://code.claude.com/docs/en/setup))

| System | Command |
|---|---|
| macOS (13 or newer) | `curl -fsSL https://claude.ai/install.sh \| bash` — or `brew install --cask claude-code` |
| Windows | `irm https://claude.ai/install.ps1 \| iex` (PowerShell) — or `winget install Anthropic.ClaudeCode`. No admin rights needed |

**First session (10 minutes)**

1. Open a terminal in the chapter folder and type `claude`.
2. Check that `CLAUDE.md` and `house-rules.md` are in the folder (both come with the template).
3. Prompt: *"Read CLAUDE.md, house-rules.md, 00-handover/handover.md and 02-chapter-knowledge/chapter-facts.md. Append one line to 00-handover/log.md: today's date · setup · level 3 · Claude Code opened the folder · next step. Show me the line."*
4. Open `log.md` yourself and confirm.

**Optional: a private repository.** Put the folder under git (private) and every change to the knowledge base and logs
stays visible for the next Chapter Manager. Useful, not necessary — the synced chapter storage remains the chapter's copy.

**What it takes.** An afternoon to set up. Everything else stays as simple as at Level 2: one laptop, one folder, you send.

## Moving up

The files do not change. Level 2 is the Level 1 folder with an assistant that can save. Level 3 is the same folder with Claude Code.
The same `house-rules.md` at every level; only where the core sits changes.

When a chat grows long, checkpoint: *"Checkpoint now. Refresh 00-handover/handover.md: what is set up, open items (each with what 'done' looks like), paths touched. Then stop."*
Open a new chat that reads the handover first. A fresh chat with a crisp handover beats a long tired one.

## What stays true at every level

- Your own files are the truth. Mails, chats and PDFs are sources.
- Read before answer. What the assistant could not open is `UNCHECKED`.
- Drafts only. You send — mail and WhatsApp alike.
- A stand-in or the next officer can continue from the folder, not from a pile of chats.
