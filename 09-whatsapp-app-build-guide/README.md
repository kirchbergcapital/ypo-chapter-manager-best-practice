# 09 · Build your own WhatsApp app — a guide, not a program

Purpose: build a small app on your own laptop, together with your AI tool, so your assistant can read the WhatsApp chats you choose, summarise them and draft your replies.
Time: the build itself took **about 10 minutes** in our test. Plan **one to two hours the first time**, including installing Node and linking your phone. After that, a few minutes whenever you use it.
Level: 3 — an AI tool that can write and run code in a folder on your laptop (see [`../01-foundations/three-levels.md`](../01-foundations/three-levels.md)).

Tool facts: as of 21 Oct 2026, with sources; `[verify]` where we could not confirm on the provider's page.

**This folder contains no code.** It contains a build prompt. You paste it into your AI tool, and the tool builds the app on your laptop,
for your own WhatsApp number. The app runs on your own laptop, for your own number —
like the rest of your own tools (see [`../05-officer-handover/what-stays-yours.md`](../05-officer-handover/what-stays-yours.md)).

| File | What it is for |
|---|---|
| [`BUILD-PROMPT.md`](BUILD-PROMPT.md) | The one prompt you copy into your AI tool. It describes the whole app |
| [`CHECKLIST.md`](CHECKLIST.md) | Ten ticks before you use the app for real |
| [`OPTIONAL-SEND.md`](OPTIONAL-SEND.md) | A second prompt, for later, if you want to send one confirmed message at a time from the app |
| [`TROUBLESHOOTING.md`](TROUBLESHOOTING.md) | QR code expired, logged out, Windows quirks and other bumps |

No code at all, ever? WhatsApp's own **"Export chat"** does the same job one chat at a time: stage 1 in
[`../03-communication/whatsapp.md`](../03-communication/whatsapp.md).

## What your app can do — and what it can't

| It can | It can't (in the version the build prompt describes) |
|---|---|
| Link to **your own** WhatsApp as a linked device, by QR code, the way WhatsApp Web does | Send anything: no messages, reactions, blue ticks, "typing …" or "online" — sending is an optional add-on you decide on later |
| Save new messages while it runs, plus the recent history WhatsApp shares when you link — except chats on your never-export list (Forum): their messages are never written to disk | Read messages that arrived while your laptop was off, unless they came with that history |
| List your chats with name and last activity | Download photos, voice messages or documents — they appear as `[image]`, `[voice message]`, `[document: agenda.pdf]` |
| Export **one chat you name exactly**, for the last N days (7 unless you say otherwise), as a Markdown file | Export all chats at once, guess which chat you meant, or export a chat whose name contains "forum" |
| Keep everything on your laptop | Upload anything anywhere — the only connection is the one to WhatsApp |

Your assistant then reads the exported file exactly like a stage-1 export: summary, open questions, one-to-one reply drafts.

## What you need

| | |
|---|---|
| **Laptop** | macOS 13 or newer, or Windows 10/11 (the requirements of Claude Code; [code.claude.com/docs/en/setup](https://code.claude.com/docs/en/setup)) |
| **Phone** | Your phone with WhatsApp on **your own number** |
| **Paid AI plan** | Claude Pro or Max (Claude Code is not in the free plan), or a comparable paid plan with a coding tool |
| **Node.js** | Free. Download the **LTS** version from [nodejs.org/en/download](https://nodejs.org/en/download) — macOS: the *macOS Installer (.pkg)*; Windows: the *Windows Installer (.msi)*. Double-click, next, next, done. Check in *Terminal* (macOS) or *PowerShell* (Windows): `node --version` should show `v20` or higher |
| **Git** | Free, and **needed for this app**, because the WhatsApp library fetches one part from GitHub while it installs (the setup guides list Git as optional — for this app it is not). Check: `git --version`. macOS: if a window offers to install the *command line developer tools*, click **Install** (a few minutes). Windows: install *Git for Windows* from [git-scm.com/downloads/win](https://git-scm.com/downloads/win) — optional for Claude Code itself, but it also gives Claude Code its Bash tool ([setup](https://code.claude.com/docs/en/setup)). Step by step: § 5 *Git* in [`../setup/macos.md`](../setup/macos.md) · [`../setup/windows.md`](../setup/windows.md) |
| **Claude Code** | In the terminal: macOS `curl -fsSL https://claude.ai/install.sh \| bash` · Windows PowerShell `irm https://claude.ai/install.ps1 \| iex` (no admin rights needed). Or use the **Claude desktop app**, which offers Claude Code with a window instead of the terminal ([setup](https://code.claude.com/docs/en/setup)). Check: `claude --version` |

New to the terminal? [`../setup/macos.md`](../setup/macos.md) and [`../setup/windows.md`](../setup/windows.md) walk you through opening it, installing Node and Claude Code, and the first login.

Other AI tools that can write and run code in a folder on your laptop can follow the same build prompt; the steps and the checklist stay the same.
This guide shows Claude Code because the kit's Level 3 uses it.

**Using ChatGPT?** Codex, included in ChatGPT Plus ([source](https://help.openai.com/en/articles/11369540)), can run the same build prompt in your `whatsapp-app` folder,
and it reads `AGENTS.md` files ([source](https://developers.openai.com/codex/guides/agents-md)). How to install it: OpenAI's own page `[verify]`.

## Six steps

### 1 · Make a folder for the app (2 min)

Open *Terminal* (macOS: Spotlight `Cmd Space`, type "Terminal") or *PowerShell* (Windows: Start menu, type "PowerShell").
Make the folder in your **home folder**, not inside a cloud-synced folder (iCloud Drive, OneDrive, Google Drive, Dropbox): the app keeps your WhatsApp
login keys there, and they work like a password.

- **macOS** (Terminal): `mkdir ~/whatsapp-app` then `cd ~/whatsapp-app`
- **Windows** (PowerShell): `mkdir $HOME\whatsapp-app` then `cd $HOME\whatsapp-app`

The app folder is separate from your chapter folder — and stays separate: the app's saved messages (`data`) and its exports never go into the chapter folder,
and your chapter assistant never works in this folder. Claude Code works here only to build and fix the app; the build prompt tells it never to open `auth`, `data` or `exports`.
Exports land in the app's own `exports` folder (step 6).

### 2 · Open Claude Code in that folder and paste the build prompt (5 min)

In the same window, type `claude` and press Enter (or, in the desktop app, open Claude Code and choose the `whatsapp-app` folder).

- **First start:** a browser window opens to log in with your Claude account (Pro or Max). Log in, then come back to the terminal.
- **"Do you trust the files in this folder?"** Yes — it is your own, empty folder.

Open [`BUILD-PROMPT.md`](BUILD-PROMPT.md), copy the whole prompt and paste it in.
Details and screenshots for the login: [`../setup/macos.md`](../setup/macos.md) · [`../setup/windows.md`](../setup/windows.md).

### 3 · Let it build the app (about 10–30 min)

Claude Code checks Node and Git, installs the library version the prompt names, writes the app and its tests, and runs the tests until they pass.
It asks before it runs a command. Read the one line, then:

| Say **yes** to | Say **no** to |
|---|---|
| `npm install`, `npm test`, creating and changing files **inside this folder** | Anything that opens a port, downloads something else, installs outside the folder, needs `sudo` or admin rights, or opens or prints what is in `./auth`, `./data` or `./exports` |

Not sure? Ask *"What does this command do, in one sentence?"* before you answer.
You do not need to understand the code. At the end `npm test` shows a short summary — something like `tests 66 · pass 66 · fail 0`. The numbers may differ; **`fail 0`** is what counts.

### 4 · Link your phone — in a terminal window (5 min)

The QR code is a one-time login code, so the app shows it **only in a terminal window**, never in Claude's chat.

1. Open a **new** *Terminal* or *PowerShell* window, go to the folder (`cd ~/whatsapp-app` or `cd $HOME\whatsapp-app`) and type `npm run link`.
2. On your phone: **WhatsApp → Settings → Linked devices → Link a device**, and scan the QR code.
3. Under **Linked devices** a new entry appears for the laptop. Note its name and today's date, so you can later log out the right one.
4. Leave the window open for a minute or two while your recent chats arrive. It keeps listening; **Ctrl-C** stops it.

The QR code did not work twice? Use WhatsApp's own "Export chat" (stage 1 in [`../03-communication/whatsapp.md`](../03-communication/whatsapp.md)) for now — it does the same job one chat at a time — and look at [`TROUBLESHOOTING.md`](TROUBLESHOOTING.md) when you have a quiet moment.

From the second time on, use `npm run listen` instead of `link` — it reuses the saved login. Claude Code walks you through linking step by step; the build prompt ends by asking it to.

### 5 · Test with "Message yourself" (5 min)

1. Keep the window from step 4 open — `link` is already listening, so **do not start `listen` as well**. On your phone, send yourself a message:
   in WhatsApp, start a new chat and pick **your own name** at the top (marked *You* or *Message yourself*). Write *"Test one"*.
2. In a **second** terminal window in the same folder: `npm run chats` — your own chat is listed as *Me (message yourself)*.
3. `npm run export -- --chat "Me" --days 1` — the app prints the path of a new file in the `exports` folder; open it, your message is there.
   `Me` always means your own chat, in any language your WhatsApp uses.
4. Run the same export again. You get a second file ending in `-2.md`: the app never overwrites.

Then go through [`CHECKLIST.md`](CHECKLIST.md) once.

### 6 · Export one real chat and let your assistant summarise it (5 min)

First `npm run chats -- --search dinner` to see the exact chat name. The app exports only when the name matches **exactly**; otherwise it lists up to 10 names and stops, so you copy the right one.

**The export stays in the app folder.** It lands in the app's own `exports` folder, on this laptop, not synced to any cloud.
Do not export into your chapter folder: the chapter folder is shared with `chair@` and synced, and the chat itself is yours, not the chapter's
([`../05-officer-handover/what-stays-yours.md`](../05-officer-handover/what-stays-yours.md)).

```
npm run export -- --chat "Holiday dinner" --days 14
```

Then open your assistant — the one you use for chapter work — and upload or drag in that one export file, with the prompt from
[`../03-communication/whatsapp.md`](../03-communication/whatsapp.md) — it starts with a stop line for Forum content:
*"Read the WhatsApp export I just uploaded, summarise what's open and draft my replies. I send them myself."*

**Only the summary goes into the chapter folder**, in the event folder: `03-events/YYYY-MM-DD_event-name/YYYY-MM-DD_whatsapp-summary.md`.
That is what the chapter keeps. The chat stays on your phone, the export in the app folder — delete the export once the summary is filed.

## Where your data lives — and its copies

| Folder | What it holds | Good to know |
|---|---|---|
| `whatsapp-app/auth` | Your WhatsApp login keys | Works like a password. Stays on this laptop |
| `whatsapp-app/data` | The messages the app saved, as plain text | It holds the chats the app saw — **except** chats whose name contains a word from `never-export.txt` (Forum): their messages are never written here. A message deleted for everyone after it was saved stays in this file; exports show it as `[deleted for everyone]`. Not for any AI tool: the app reads it, you do not hand it to an assistant |
| `whatsapp-app/exports` | Your exports | One chat at a time, for your assistant to read. Delete each one once its summary is in the event folder |

**Backups copy these folders too.** Time Machine (macOS) and File History (Windows) back up your home folder, including `auth` and `data`. Keep FileVault (macOS) or BitLocker / device encryption (Windows) switched on and choose an encrypted backup — or exclude the `whatsapp-app` folder from the backup. Both take a minute in the settings.

## Removing it again

1. **On your phone:** WhatsApp → Settings → **Linked devices** → tap the laptop entry you noted in step 4 → **Log out**. From this moment the app cannot read anything new.
2. **On your laptop:** delete the `whatsapp-app` folder by hand (Finder or File Explorer → Trash, then empty the Trash). That removes the login keys and the saved messages.
3. Exports you saved elsewhere stay where you saved them, and older backups keep their copy — delete them by hand if you no longer need them.

`npm run unlink` prints these steps for you. The app itself never deletes files or folders — you stay the one who decides what goes.

## WhatsApp's rules and good habits

The app connects as an unofficial client, and WhatsApp's [messaging guidelines](https://www.whatsapp.com/legal/messaging-guidelines) name unofficial clients, bulk messaging and automation
among the things they act against — the app as built here stays close to normal personal use: it reads and you draft, at your own pace, on your own number.

Two more things decide. **Your chapter's and YPO's own WhatsApp rules:** where messages may not leave a group, export that group neither with the app nor with *Export chat*. **WhatsApp itself:** it can restrict a number that uses an unofficial client — nobody can rule that out. If your number matters for the chapter, stay with stage 1, WhatsApp's own *Export chat* ([`../03-communication/whatsapp.md`](../03-communication/whatsapp.md)).

| Habit | Why it helps |
|---|---|
| **Read and draft** | Your assistant summarises and drafts; you send from your phone — or, if you add the optional send step, one confirmed message at a time |
| **Personal pace** | Export a few chats when you sit down to work, not every minute, not every chat |
| **No bulk** | No mass messages, no lists of recipients, no schedules — the chapter rule *"A human sends"* ([`../06-chapter-rules/ai-use-one-pager.md`](../06-chapter-rules/ai-use-one-pager.md)) |
| **Only what is yours to read** | Your own chats for your chapter work; Forum stays out (below) |

## Honest limits

- **Your laptop has to run.** New messages reach the app only while `npm run listen` (or `link`) is open on a laptop that is awake and online.
  Messages from the time in between arrive only if WhatsApp includes them in its history — it usually does not.
- **History at linking is limited.** When you link, WhatsApp shares recent history, not your whole archive `[verify: how much depends on WhatsApp]`.
- **Some senders have no name.** WhatsApp sometimes shares only an internal id instead of a number; the app then writes *Unknown (lid)* rather than guessing.
- **Linked devices can be logged out.** WhatsApp may log out linked devices when your phone has not been used for a longer while `[verify]`. Then link again (see [`TROUBLESHOOTING.md`](TROUBLESHOOTING.md)).
- **Delivered, not read.** Like WhatsApp Web, the library confirms delivery (grey double ticks) and announces the laptop as "offline" when it connects. It does not send blue ticks.
- **WhatsApp changes its web protocol from time to time.** The build prompt pins the library to version 6.7.24, the stable version this guide was tested with (Oct 2026). If linking stops working one day, ask Claude Code to check for a newer **stable** version and run the tests again.
- **The library is open source and not affiliated with WhatsApp** ([npm: baileys](https://www.npmjs.com/package/baileys)); the app should work for personal use as described, but nobody can promise it will keep working.

## Forum stays out

> Forum is sacred. We use AI for Forum logistics only: dates, places, headcounts, costs, deadlines. Never for what is said in or around a Forum: topics, stories, notes, retreat conversations, anything shared in confidence, or any link between a name and a topic. If in doubt, leave it out.

For the app that means: **Forum chats are never exported.** The build prompt makes the app refuse any chat whose name contains "forum"
(you can add more words to `never-export.txt`). The check goes by the chat's **name only**: a Forum chat with a different name, or one renamed later, is not detected —
add a word from its name to `never-export.txt`, or simply never export it.
Messages of a chat on the list are **not saved** at all — not in `./data`, not anywhere. A word you add later stops new saving from then on;
what was saved before stays in `./data` (the app never edits that file) — to remove it, stop the app, delete the `data` folder by hand and start `npm run listen` again.
