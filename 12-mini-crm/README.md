# 12 · Your own mini CRM — a guide, not a program

Purpose: build a small contact and event list for your chapter on your own laptop, together with your AI tool — people, events, who came — in one file on your laptop (an SQLite database). Then add what you need on top: a photo book, mailing drafts, WhatsApp links.
Time: 20 to 40 minutes to build the first time, most of it the AI tool writing and testing (about 10 minutes in our reference build, Nov 2026). Plan an hour including installing Node.js. After that, a few minutes whenever you use it.
Level: 3 — an AI tool that can write and run code in a folder on your laptop (see [`../01-foundations/three-levels.md`](../01-foundations/three-levels.md)).

**This folder contains no code.** It contains a build prompt. You paste it into your AI tool, and the tool builds the app on your laptop.
No account and no subscription. The finished app does not use the internet: it runs only on your laptop, in your browser, and stores everything in one file, `crm.db`.

| File | What it is for |
|---|---|
| [`BUILD-PROMPT.md`](BUILD-PROMPT.md) | The one prompt you copy into your AI tool. It describes the whole app |
| [`CHECKLIST.md`](CHECKLIST.md) | Ten ticks before you put real names in |
| [`ADD-ONS.md`](ADD-ONS.md) | Extras on top, one prompt each: photo book, mailing drafts, WhatsApp links, event check-in list |
| [`TROUBLESHOOTING.md`](TROUBLESHOOTING.md) | The usual bumps — Node, the start file, the browser, import |

No code at all? A spreadsheet in your chapter storage does most of this too. The mini CRM is for the day the spreadsheet has five tabs and nobody knows which one is right.

## What your app can do — and what it can't

| It can | It can't |
|---|---|
| Keep people — members, spouses, guests, prospects, speakers, partners — with company, role, email, mobile, tags and a photo | Send anything: no email, no WhatsApp, no message of any kind. Extras only prepare drafts; you send |
| Keep events and who was invited, registered, attended or declined | Connect to YPO Connect, CMH or any other system |
| Import a list from Excel or Google Sheets (CSV), with a preview before anything is saved | Be reached from another computer — it listens only on your own laptop |
| Export any filtered list as CSV, safe to open in Excel | Store birthdays, private addresses, health or Forum topics — the fields do not exist |
| Make a full backup with one button | Sync by itself — you copy the backup into the chapter storage |

## Which data goes in

**Whatever your chapter's AI document says** — the one-pager "AI use in our chapter" ([`../06-chapter-rules/ai-use-one-pager.md`](../06-chapter-rules/ai-use-one-pager.md)) that you prepare with your Chair and your ExCo adopts. Put the mini CRM on its tool list (Part B). After that, you are free to work — member lists, events, invitations, the photo book.

Two things the app does for you: a photo is only shown when *photo OK* is ticked, and there is no field for Forum content.

The file `crm.db` is the chapter's contact list, like the member list in Excel. At a handover, the newest backup goes to your successor ([`../05-officer-handover/handover-checklist.md`](../05-officer-handover/handover-checklist.md)).

## Step by step

1. **Node.js 24 or newer.** Your AI tool checks this for you in step 3. If it says Node.js is missing or too old, install the version marked *LTS* (recommended) — [`../setup/macos.md`](../setup/macos.md) § 3 or [`../setup/windows.md`](../setup/windows.md) § 3.
2. **One folder that is not synced.** Create `chapter-crm` directly in your user folder — the one with your name (Mac: Finder → *Go* → *Home*; Windows: File Explorer, type `%USERPROFILE%` in the address bar). Not on the Desktop, not in Documents, not in iCloud Drive, OneDrive, Google Drive or Dropbox. A sync app can break a database file while it is open. The backups go into the chapter storage later.
3. **Start your coding tool and choose `chapter-crm` as its folder** — the Claude desktop app with Cowork, ChatGPT Work, Claude Code or Codex ([`../setup/`](../setup/README.md)). Paste the prompt from [`BUILD-PROMPT.md`](BUILD-PROMPT.md). Say yes to files in this folder and to commands that start with `node`. Say no to a password, to `npm`, and to any other folder.
4. **Wait for the self-test.** The tool runs `node self-test.js` until it shows `0 failed` and shows you the last line.
5. **Start it.** Mac, the first time only: see the box in [`TROUBLESHOOTING.md`](TROUBLESHOOTING.md#starting). Double-click `start-mac.command` or `start-windows.bat`. A text window opens — **leave it open, it is the app**. Your browser opens the app.
6. **Practise with fictional people.** Import `sample-people.csv` — in the file window, open your user folder, then `chapter-crm` — add the fictional *Holiday Dinner* by hand, register a few people. Keep them for the checklist.
7. **Tick the checklist** — [`CHECKLIST.md`](CHECKLIST.md). Then delete the fictional people and the *Holiday Dinner*, and add your real list.
8. **Back up weekly.** *Backup now* → copy the newest folder from `backups/` into your chapter storage. It holds the list and the photos together.

To stop the app: close the text window that opened in step 5.

## With your assistant

Your assistant does not read `crm.db` — and neither does the coding tool that built the app: the build prompt and every add-on forbid it, and it tests with a temporary database. When it needs a list — the registered people for a name-badge draft, the speakers of the year for a thank-you note — export only the columns that task needs and give it that file.

Next: [`ADD-ONS.md`](ADD-ONS.md) — the photo book, mailing drafts and WhatsApp links, one prompt each.
