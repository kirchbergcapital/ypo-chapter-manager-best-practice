# Build prompt — your own read-only WhatsApp app

Purpose: the one prompt you paste into Claude Code (or a comparable AI coding tool) in your empty `whatsapp-app` folder. It describes the whole app.
Time: about 10 minutes of building and testing in our test run — allow up to half an hour. You answer a few questions and say yes to commands inside the folder (README step 3).

How to use it: copy **everything inside the grey box** — from "You are helping me" to the last line — and paste it as one message.
The prompt is in English on purpose: the code, the tests and the app's README come out in English, and you can always ask Claude Code to explain any step in your own language.

Why it is this detailed: an earlier reference build of this app went through three rounds of independent code review, and a test build with an
earlier version of this prompt (Oct 2026: about 10 minutes, every test passing, no sending calls in the code) showed where a tool could still
take a wrong turn — for example which library version to pick. Every requirement below answers one of those findings.

```text
You are helping me, a non-technical person, build a small app on my own laptop. Work only in the current folder.
Before each step, tell me in one or two plain sentences what you are about to do. Ask me before you install
anything outside this folder. Never use sudo or admin rights, never open a port, never download anything except
through npm install. Keep the code small and readable, with comments in plain English.

GOAL
A small command-line app that links to MY OWN WhatsApp as a linked device (the way WhatsApp Web does), using the
open-source library Baileys. It saves incoming messages on this laptop, lists my chats, and exports one chat I name
as a Markdown file. My AI assistant then reads that file, summarises it and drafts replies; I send every reply
myself. This version sends nothing of its own - no messages, reactions, read receipts or presence; only the
protocol traffic the library itself sends, like WhatsApp Web (section 5).
Forum stays out at the door: messages of chats on the never-export list (Forum) are never written to disk.
The saved messages in ./data are for the app only: you, the AI tool, never open, read, search or print ./auth,
./data or ./exports - not now and not later - and my chapter folder never contains them. Exports stay in this app
folder; only a summary ever goes into my chapter folder, and I file that myself.

0. CHECK FIRST
- Run `node --version`. I need Node.js 20 or newer. If it is missing or older, stop and tell me to install the LTS
  version from https://nodejs.org/en/download, then wait for me.
- Run `git --version`. npm needs git once, because Baileys fetches one dependency (libsignal) from GitHub. If git
  is missing, stop and tell me how to get it: on macOS, accept the offer to install the command line developer
  tools; on Windows, install Git for Windows from https://git-scm.com/downloads/win. Then wait for me.
- Find out whether I am on macOS or Windows and give every command for my system (PowerShell on Windows).
- Check whether this folder lies inside a cloud-synced folder (iCloud Drive, Desktop & Documents in iCloud,
  OneDrive, Google Drive, Dropbox). If it does, stop and tell me: the login keys this app stores work like a
  password and must stay on this laptop only.

1. TECH BASE
- Node.js with ES modules ("type": "module" in package.json), plain JavaScript, no TypeScript, no build step.
- Baileys version: install EXACTLY 6.7.24 - the stable version this guide was tested with (Oct 2026).
  Do not choose a version yourself. Do not use 6.17.x: that number is an old, mis-numbered release from March 2025.
  Do not use 7.x release candidates, even though npm's "latest" tag points to one.
- Direct dependencies, each pinned to an EXACT version in package.json (no ^, no ~), and keep package-lock.json:
  baileys 6.7.24; pino (the logger Baileys expects, set to level "silent") at the exact version npm resolves for
  Baileys 6.7.24 - read it from package-lock.json (9.14.0 on 21 Oct 2026); qrcode-terminal 0.12.0 (draws the QR
  code). No other direct dependencies. npm will also pull in Baileys' own dependencies (among them sharp, and
  libsignal from GitHub via git); that is expected. Tests use only Node's built-in test runner.
- After installing, show me the three exact versions from package.json in one line.
- Use the real API of Baileys 6.7.24: read its README and type definitions in node_modules (connection.update with
  the qr field, useMultiFileAuthState, DisconnectReason, Browsers, the messaging-history.set event). Do not rely on
  memory of other versions.
- If `npm install` fails, explain it in plain words and stop. Do not switch to another Baileys version on your own.

2. COMMANDS (npm scripts)
- npm run link     connect, show the QR code in the terminal, store the login keys in ./auth, then keep listening
                   like `listen`.
- npm run listen   connect with the stored keys and save incoming messages to ./data until I press Ctrl-C.
                   If ./auth holds no saved login yet (no creds.json), stop at once, without connecting, with
                   "No saved login yet - run npm run link first." listen never shows a QR code.
- npm run chats    offline. List chats from ./data: name, last activity, number of messages. Optional
                   `-- --search <text>`. Never print message text.
- npm run export -- --chat "<name>" [--days N] [--out <folder>]
                   offline. Export ONE chat as Markdown (details in section 6). --days: 1 to 365, default 7.
                   --out: default ./exports in the app folder.
- npm run unlink   offline. Print the steps to remove the link and the data (section 5). It changes nothing.
- npm test         run all tests with `node --test`.
On any error: a short, friendly English sentence and a non-zero exit code; stack traces only with --debug.
No command ever asks me a question or waits for input.

3. CONNECTION (link and listen)
- Socket options: markOnlineOnConnect: false (written as the literal false); syncFullHistory: false; a standard
  desktop browser preset from Baileys' Browsers for my operating system; logger = pino({ level: 'silent' }).
  Ignore status updates, channels/newsletters and broadcast lists.
- QR code: draw it only when process.stdout.isTTY is true. `link` checks this at the very start, before it takes
  the lock or connects: if stdout is not a terminal, it prints "Run this in a terminal window - the QR code is a
  one-time login code and is only shown there." and exits. Show at most 3 QR codes per run, then stop
  with the hint to run `npm run link` again.
- Draw the QR code with qrcode-terminal's callback form - generate(qr, { small: true }, callback) - and write the
  string it hands to the callback with process.stdout.write. Do not let qrcode-terminal print by itself: it uses
  console.log, which is muted during the connection, so the code would never appear. Never print the raw QR string.
- Mute the console: right before the connection starts, replace console.log, info, warn, error and debug with
  functions that do nothing (the encryption library underneath can print session keys); restore them when the run
  ends. The app's own status lines go to process.stderr.write. Never print or log the contents of ./auth, keys,
  tokens or the QR string.
- After linking succeeds, print one line: the device name passed to WhatsApp (from the Browsers preset) and the
  time, and say "Note this - it is how you find this laptop under WhatsApp -> Linked devices."
- Reconnect: right after pairing WhatsApp asks for one restart (restartRequired) - do it once, at once; it does not
  count as an attempt. After any other drop: up to 8 reconnect attempts, with growing pauses (2 s, 4 s, 8 s ... at
  most 60 s). The counter resets to 0 after a connection has stayed open for 10 minutes. After 8 failed attempts,
  stop with a clear message.
- Logged out by WhatsApp: stop. Do NOT delete anything. Print: "WhatsApp logged this laptop out. To link again,
  delete the folder ./auth by hand, then run npm run link."
- Connection replaced: stop and say that another session took over.
- Never-export filter BEFORE anything is written: keep in memory the chat ids whose name contains a word from
  never-export.txt (case-insensitive; the names come from the history, chats/contacts events or groupMetadata).
  If a group's name is not known yet when its message arrives, call groupMetadata for it once (a read) before
  writing. For such a chat write NOTHING to disk - no message, edit or delete line in messages.jsonl, no line in
  chats.jsonl or contacts.jsonl. Re-read never-export.txt at the start of every link/listen run.
- Save from BOTH events: messaging-history.set (the history WhatsApp sends when I link, with chats, contacts and
  messages) and messages.upsert (new messages). Also messages.update (edits, deleted-for-everyone), and chat and
  contact names as WhatsApp shares them (chats.upsert/update, contacts.upsert/update). You may call
  groupFetchAllParticipating once after connecting to learn group names - that is a read.
- When connected, record my own chat: append to chats.jsonl the linked account's own chat id(s) - phone-number
  form and, if WhatsApp provides it, the @lid form - with "self": true.
- Lock: link and listen create ./data/app.lock exclusively (open flag 'wx'), holding the process id, the start
  time and a random token, written in a single write. If the file exists: when that process is still running, or
  the file is empty or incomplete, refuse with "The app is already running in another window." When that process
  is no longer running, refuse too and print exactly which file to delete by hand. Never decide by the file's age.
  chats, export and unlink do not need the lock.

4. DATA (./auth, ./data and ./exports on this laptop only)
- Create ./auth, ./data and ./exports with mode 0o700 (owner only). ./data holds messages.jsonl, chats.jsonl and
  contacts.jsonl: one JSON object per line - never anything from a chat on the never-export list (section 3).
- Create never-export.txt in the app folder, one word per line, pre-filled with "forum" (used in sections 3 and 6).
- Keep the AI tool out of the data: write a CLAUDE.md and an AGENTS.md in the app folder, each saying in plain
  words "Never open, read, search or print ./auth, ./data or ./exports. Work only on the code, the tests and the
  README." Also write .claude/settings.json with permissions.deny for Read(./auth/**), Read(./data/**) and
  Read(./exports/**). Say in the README that these are a second lock for the AI tool, not a proof.
- Append only these fields. Never write the raw message object, mediaKey, media URLs or direct paths, file
  hashes, thumbnails, or anything from ./auth.
  messages.jsonl: id, chatId, timestamp, senderId, senderName (if WhatsApp shares one), fromMe, text or media
  marker, kind ("message", "edit" or "delete") and, for edits and deletes, the id of the message they change.
  chats.jsonl: chatId, name, isGroup, self (only for my own chat), timestamp.
  contacts.jsonl: id, address-book name, profile name.
- Media becomes a marker only: [image], [video], [voice message], [document: <file name>], [sticker], [location],
  [contact card]. Never download media.
- Before appending, if the file does not end with a newline, write a newline first. Never rewrite, repair,
  truncate, reorder or de-duplicate a file on disk. Apply edits, deletions and duplicates in memory when reading:
  the latest edit wins and is marked "(edited)"; a message deleted for everyone shows "[deleted for everyone]"
  (its earlier line stays in messages.jsonl - say so in the README).
- When reading, skip every line that is not a valid JSON object (null included), count them and print only
  "Skipped N unreadable lines (content not shown)."
- Refuse to run, and say why, if ./auth, ./data or any data file is a symbolic link (check with lstat).
- The app's own code never deletes, repairs or truncates any file or folder. The one exception: at the end of its
  own run it removes the lock file it created - only if the file still carries this run's token. (Inside ./auth
  the library manages its own key files; that is expected.)
- .gitignore: /auth/, /data/, /exports/, /node_modules/, .DS_Store.
- --out (section 6) is for a folder on this laptop only; the README recommends the default ./exports and says
  never to export into the chapter folder or any cloud-synced folder.

5. NOTHING IS SENT - hard rule for this version
- The code must never call sendMessage, relayMessage, sendReceipt, sendReceipts, readMessages, sendPresenceUpdate,
  presenceSubscribe, chatModify, star, any group function other than groupFetchAllParticipating and groupMetadata,
  any updateProfile..., updateBlockStatus, any privacy or settings update, query, sendNode, or the raw websocket.
  So: no messages, reactions, read receipts (blue ticks), typing state, "online" presence, group or profile changes.
- No other network access: no fetch, http, https, net, dgram, child_process, eval, telemetry, analytics or update
  checks. The only connection is the one Baileys opens to WhatsApp. If you think another one is needed (for
  example to look up the current WhatsApp Web version), explain why and ask me first.
- Do not patch the library. Explain honestly in the README that, like WhatsApp Web, the library itself sends
  protocol traffic: delivery receipts (grey double ticks), history-sync receipts, acknowledgements and an
  "unavailable" (offline) presence when it connects.
- unlink prints these steps and nothing else: 1) On your phone: WhatsApp -> Settings -> Linked devices -> tap this
  laptop -> Log out. 2) Delete the folder ./auth by hand - or the whole app folder - in Finder or File Explorer.
  3) Exports stay where you saved them; delete them by hand if you no longer need them.

6. EXPORT
- --chat matching, case-insensitive: export only when exactly ONE chat name matches the text exactly. In every
  other case (no exact match, or several chats with that exact name) print up to 10 chat names that contain the
  text, each with its last activity, say "Use one of these names exactly.", and exit. Never prompt, never pick
  a chat on my behalf, never export more than one chat per run.
- "Me" is reserved: --chat "Me" (any case) matches only my own chat - the chat(s) marked "self": true - and never
  a chat by its name. chats shows it as "Me (message yourself)".
- Forum stays out: refuse to export any chat whose name contains one of the words in never-export.txt (case-insensitive) and say: "This looks like a Forum
  chat. Forum content stays out."
- --out: default ./exports. Create the folder if it is missing (mode 0o700). If the --out folder itself is a
  symbolic link, refuse and print its real path, so I can use that instead.
- File name: YYYY-MM-DD_<slug>-<6 hex characters from a hash of the chat id>.md. The slug keeps only a-z, 0-9 and
  hyphens, at most 40 characters, so no chat name can create a path.
- Create the file exclusively (open flag 'wx'). Never overwrite and never follow a link: if the name exists, try
  -2, -3 ... up to -99, then stop with a message.
- Content: a header with the chat name, the period (from and to dates), the export time and the line
  "Source, not truth - exported read-only."; then one line per message: "YYYY-MM-DD HH:MM · Name: text" in local
  time, continuation lines of multi-line messages indented.
- Names: the address-book name if WhatsApp shares it, otherwise the profile name, otherwise the phone number. A
  sender whose id ends in @lid and who has no name shows as "Unknown (lid)" - never print the lid number itself.
- At the end, print the full path of the file.

7. TESTS (node --test, fictional data only)
- Fixtures in test/fixtures: a fictional "Lakeside Chapter (fictional)" with made-up names and numbers that start
  with +00. No real data anywhere.
- Every test works in a temporary folder under os.tmpdir() and never touches ./auth, ./data or ./exports.
- Cover at least: argument parsing (--days default 7, range 1 to 365; --out default ./exports); chat matching (no
  match, one exact match, a name that only contains the text, two chats with the same exact name - only one exact
  match exports, and nothing ever prompts); "Me" matches only the self chat, not "Megan" or "Meeting"; the Forum
  refusal; the --days window; file names and slugs; no overwrite (second export gets -2); refusing a symbolic-link
  --out folder and a symbolic-link data file (on Windows, skip with a clear note if creating links is not
  permitted); skipping unreadable and null lines; appending after a last line without newline; edits and
  deletions applied ("(edited)", "[deleted for everyone]"); stored lines contain only the listed fields, even when
  the incoming fixture message carries mediaKey, a URL and file hashes; a chat named "Lakeside Forum (fictional)"
  writes nothing to messages.jsonl, chats.jsonl or contacts.jsonl - neither from history, nor from new messages,
  nor from edits or deletes, and also when its group name only arrives via groupMetadata; history from messaging-history.set and new
  messages from messages.upsert both end up in messages.jsonl; "Unknown (lid)" for an unnamed @lid sender; listen
  without saved login stops with "run npm run link first"; the lock (second run refused; dead process refused with
  the delete-by-hand message; own lock removed only with the matching token); no QR code when stdout is not a
  terminal; the QR code is written via process.stdout.write while the console is muted; reconnect counting with
  fake timers (at most 8 attempts after a drop, the pairing restart not counted, the counter reset after 10 minutes
  open); a run against a mock socket on which every sending function is a spy that must never be called; and a
  tripwire test - with "tripwire" in its name - that scans src/ for the forbidden names and imports from
  section 5, also written as strings. Call that scan what it is: a tripwire, not a proof.

8. README.md (for me, a non-technical user)
Plain English: what the app does and does not do; the commands (with the defaults --days 7 and --out ./exports);
where the data lives (./auth works like a password, ./data holds messages - never those of chats on the
never-export list - ./exports holds exports, all on this laptop, none of it for the chapter folder); that a word
added to never-export.txt later stops saving from then on, while earlier lines stay until I delete ./data by hand;
that CLAUDE.md, AGENTS.md and .claude/settings.json keep the AI tool out of ./auth, ./data and ./exports; that a message deleted for everyone stays in messages.jsonl; that
backups (Time Machine, File History) copy these folders; how to stop it (Ctrl-C); which name the laptop shows under
WhatsApp -> Linked devices; how to unlink and remove everything by hand; what goes over the wire (the honest list
from section 5); known limits: new messages arrive only while link or listen runs on an awake laptop; do not run
listen while link is still running; history at linking is limited; the never-export check goes by chat name only;
WhatsApp may log out linked devices after the phone has been unused for a while; WhatsApp changes its web protocol
from time to time, so a newer stable library version may be needed one day.

9. FINISH
- Run npm test and fix until every test passes. Then show me the test summary (tests, pass, fail) and the list
  of files, one line each.
- Do not run `npm run link` yourself: it needs my phone and a real terminal window.

When done, show me how to run the test, then walk me through `npm run link` step by step.
```

Next: link your phone (step 4 in the [README](README.md)), then tick [`CHECKLIST.md`](CHECKLIST.md).
Want to send one confirmed message at a time from the app later? That is [`OPTIONAL-SEND.md`](OPTIONAL-SEND.md) — your choice, not a step.
