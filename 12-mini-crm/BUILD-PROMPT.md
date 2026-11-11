# Build prompt — your own mini CRM

Purpose: the one prompt you paste into your AI coding tool in your empty `chapter-crm` folder. It describes the whole app: a small contact and event list for your chapter, stored in one SQLite file on your laptop, opened in your browser.
Time: 20 to 40 minutes the first time, most of it the AI tool writing and testing. You answer a few questions and say yes to file changes inside the folder.

How to use it: copy **everything inside the grey box** — from "You are helping me" to the last line — and paste it as one message.

- **A coding tool** (Claude Code, Codex, the Claude desktop app with Cowork, ChatGPT Work in the desktop app): open it in your `chapter-crm` folder first. It writes the files there and runs the self-test.
- **A chat tool in the browser** cannot build this app — it needs to run a small program on your laptop. Use a coding tool, or stay with your spreadsheet for now.

The prompt is in English on purpose: the code and the tests come out in English, and you can always ask your AI tool to explain any step in your own language.

Why it is this detailed: every requirement below is something you can see working — in the self-test, in your browser, or in the [`CHECKLIST.md`](CHECKLIST.md).
Tested in a reference build (Nov 2026, Claude Code, macOS, Node 26): about 10 minutes to build, self-test 56 passed and 0 failed; then checked by hand — no packages, only 127.0.0.1, no token → 401, a foreign website → refused, `../crm.db` → refused, the Excel export keeps `=` from running. The self-test shows whether it holds on your laptop; the number passed varies.

```text
You are helping me, a non-technical person, build a small app on my own laptop. Work only in the current folder.
Before each step, tell me in one or two plain sentences what you are about to do, and wait for my yes before you
create or change a file. Never use sudo or admin rights, never install anything, never run npm, never download
anything, never add a package.json with dependencies. Keep the code small and readable, with comments in plain
English.

GOAL
A local "mini CRM" for my YPO chapter. I am a Chapter Manager. The app keeps a list of people (members, spouses,
guests, prospects, speakers, partners), the chapter's events, and who was invited to, registered for or attended
which event. It stores everything in ONE SQLite file, crm.db, in this folder. I use it in my browser at a local
address. It never connects to the internet, never sends a message or an email, and never shares data with anyone.
Later I may add extras on top (a photo book, mailing drafts, WhatsApp links) - keep the code easy to extend.

0. CHECK FIRST
- Run `node --version`. I need Node.js 24 or newer (it has SQLite built in as node:sqlite). If Node is missing or
  older, stop and tell me to install the LTS version from https://nodejs.org/en/download, then wait for me.
- Find out whether I am on macOS or Windows and give every command for my system (PowerShell on Windows).
- Check whether this folder lies inside a cloud-synced folder (iCloud Drive, Desktop & Documents in iCloud,
  OneDrive, Google Drive, Dropbox). If it does, stop and tell me: "A database file can break when a sync app copies
  it while it is open. Please move this folder to a place on your laptop that is not synced, for example
  Documents/chapter-crm on a Mac without iCloud for Documents, or C:\Users\<you>\chapter-crm on Windows. Backups
  go into your chapter storage later." Then wait.
- If crm.db already exists here, never delete, overwrite or reset it while building or testing. Tests use their
  own temporary database.
- Never open, query, print or copy crm.db, crm.db-wal, crm.db-shm, backups/, exports/ or photos/ - not to check,
  not to debug, not now and not later in this folder. Never start server.js on this folder's data; test only with a
  temporary database. If you need to know what the data looks like, ask me to describe it without names.

1. TECH BASE - no dependencies at all
- Node.js only, with built-in modules: node:http, node:sqlite (DatabaseSync), node:fs, node:path, node:crypto,
  node:url. No npm packages, no frameworks, no CDN, no web fonts, no images from the internet.
- Files, exactly these:
    server.js          the local web server and the database access
    crm-core.js        pure logic, no database, no files, no network: validation, CSV parsing and writing,
                       duplicate check, text helpers - everything that can be tested
    public/index.html  the whole user interface (plain HTML, CSS, JavaScript in one file)
    self-test.js       runs the tests with `node self-test.js` and prints "N passed, 0 failed"
    start-mac.command  double-click start on macOS
    start-windows.bat  double-click start on Windows
    README-app.md      a one-page note for me: start, stop, backup, where the data is
  Folders the app creates when needed: photos/, backups/, exports/.
- The start files: change into the app folder, run `node server.js`, and open the browser at the address the
  server prints. The window that opens stays open while the app runs; closing it stops the app. On macOS, after
  creating start-mac.command, tell me to run `chmod +x start-mac.command` once, and explain that the first double-
  click may need right-click > Open because the file is not from the App Store.

2. SAFETY - hard rules
- The server listens on 127.0.0.1 only, port 8765 (if busy, try 8766 to 8770 and print the one it uses). Never
  0.0.0.0, never another network interface.
- Every request: reject it unless the Host header is 127.0.0.1:<port> or localhost:<port>. Every POST, PUT and
  DELETE: reject it unless the Origin header is missing or equals http://127.0.0.1:<port> or
  http://localhost:<port>. This keeps other websites in the same browser from talking to the app.
- At start, create a random token (node:crypto, 32 bytes, hex), print the full address with ?t=<token> and open
  exactly that address. index.html sends the token in a header X-CRM-Token with every API call; the server answers
  401 without it. The token lives only in memory and changes with every start.
- All SQL with prepared statements and ? placeholders. Never build SQL from user text.
- The page never inserts user text as HTML: use textContent, never innerHTML with data.
- Response headers on every page: Content-Security-Policy "default-src 'self'; img-src 'self' data:;
  style-src 'self' 'unsafe-inline'; script-src 'self' 'unsafe-inline'; connect-src 'self'; frame-ancestors 'none'",
  X-Content-Type-Options nosniff, Referrer-Policy no-referrer.
- Serve only files from public/ and photos/, never anything else (no path traversal: resolve the path and check it
  stays inside the folder). /photos/ needs the token too (as ?t=<token> in the image address) and serves a file only
  when its person has photo_ok = 1.
- Photos: accept JPEG and PNG only, check the first bytes of the file (JPEG FF D8 FF, PNG 89 50 4E 47), at most
  5 MB, save under a new random file name in photos/ (crypto.randomBytes(16) as hex). Never keep the original file name.
- No code that sends anything: no email, no SMTP, no WhatsApp, no HTTP requests to other hosts, no analytics.
- Never run shell commands from the app, with one exception: at start, server.js may open the default browser once
  with its own local address and nothing else - macOS: execFile('open', [address]); Windows:
  execFile('explorer.exe', [address]). An environment variable CRM_NO_BROWSER=1 switches this off. Never use eval.

3. DATA - one SQLite file, crm.db
- Open crm.db with PRAGMA journal_mode=WAL, PRAGMA foreign_keys=ON, PRAGMA busy_timeout=5000 and
  PRAGMA secure_delete=ON. Create the tables if they do not exist.
  Keep a table meta(key, value) with schema_version = 1, so later extras can add columns safely.
- people: id, first_name, last_name, company, title, email, mobile, kind (member | spouse | guest | prospect |
  speaker | partner | other), chapter_role (free text, e.g. "Learning Officer"), member_since (year, optional),
  tags (comma-separated words), photo_file (random name or empty), photo_ok (0 or 1), photo_ok_date (the day I
  ticked it), notes, created_at, updated_at. first_name or last_name required. email optional but unique when present (compare lower-case,
  trimmed).
- events: id, name, date (YYYY-MM-DD), place, notes. name and date required.
- attendance: event_id, person_id, status (invited | registered | attended | declined | waitlist), unique per
  event and person, deleted together with the event or the person.
- Never add fields for birthdays, private addresses, health, family matters or anything about Forum. Under the
  notes field the page shows: "Chapter facts only. No Forum content - ever. Nothing a member told you in
  confidence."
- photo_ok: a photo is only shown and only used for extras (like a photo book) when photo_ok is 1. Ticking it
  stores today's date in photo_ok_date. Unticking asks "Delete the photo file too?" (default yes); if I say no, the
  file stays but is hidden everywhere. Deleting the person deletes the photo file too.
- Edits: every update sends the updated_at the page loaded; if the record changed meanwhile (another tab), refuse
  with "Changed in another window - please reload" instead of overwriting.

4. WHAT I CAN DO IN THE BROWSER - simple, large buttons, plain words
- People: a list with search (name, company, email, tags), filter by kind and by tag, sorted by last name.
  Add, edit, delete (delete asks "Delete <name>? This cannot be undone."). Upload or remove a photo.
- Events: a list sorted by date (next first), add, edit, delete. On an event: add people (search and tick),
  set each person's status, see counts per status.
- Import from CSV (for example an export from Excel or Google Sheets): I choose a file, the app shows the first
  10 rows and a mapping of my column names to the app's fields (it guesses: "First name", "Vorname", "E-Mail",
  "Email", "Mobile", "Handy", "Company", "Firma" ...). I confirm. Then it shows: N new, N updated (same email),
  N skipped (no name), and only after a second yes it writes them. Accept comma and semicolon separators, UTF-8
  with or without BOM, quoted fields with line breaks. Never map a column to notes automatically - I choose that by
  hand - and an import never replaces existing notes; it adds below them.
- Export to CSV: the current filtered list, with the columns I tick. Every text cell that starts with = + - @, a
  tab or a carriage return gets a leading apostrophe, so Excel never runs it as a formula. Save it only into
  exports/ with the date in the file name and show me the file name - no second copy in the browser's Downloads.
- Backup: one button "Backup now" writes a full copy with VACUUM INTO into backups/crm-YYYY-MM-DD-HHMM.db and
  shows the file name. The page reminds me once a week: "Last backup: <date>. Copy the newest backup and the
  photos/ folder into your chapter storage."
- A small "About" box: where crm.db lives, the number of people and events, the last backup.

5. TESTS - self-test.js
- Test crm-core.js thoroughly: CSV parsing (commas, semicolons, quotes, line breaks in quotes, BOM, empty lines),
  CSV writing with the formula guard, email normalisation and the duplicate rule, validation of each field,
  column-name guessing for English and German headers.
- Test the database part against a temporary file in the system temp folder - never against crm.db: create
  tables, add, update, unique email, attendance unique per event and person, delete cascades.
- Test the server: start it on a free port with a temporary database, check that a request without the token
  gets 401, a wrong Host header is rejected, a foreign Origin on POST is rejected, a path like /../crm.db is
  refused, and a normal add/list round trip works. Stop it again.
- Print one line per failed test and at the end "N passed, 0 failed". Exit code 1 if anything failed.
- Run `node self-test.js` yourself and fix everything until it shows 0 failed. Show me the last line.

6. FINISH
- Fill crm.db with nothing. Offer me to try the app with fictional data first: create a file
  sample-people.csv with 8 fictional people of a "Lakeside Chapter (fictional)", all with example.com email
  addresses - I import the CSV myself in the browser, so I learn how import works. Then tell me to add one
  fictional event by hand, "Holiday Dinner" on the next 12 December, and to register a few of the fictional
  people. Tell me to delete these fictional people before I add real ones.
- Write README-app.md in plain English, at most one page: how to start (double-click), how to stop (close the
  window), where the data is (crm.db - "this file is your chapter's contact list. Never copy or mail crm.db itself;
  hand over only a file from Backup now, together with photos/"), how to back up (button, then copy the newest
  file from backups/ and the photos/ folder into the chapter storage), that deleting a person does not reach
  backups already copied, and two rules: "No Forum content, ever." and "The AI tool that built this app never
  opens crm.db, backups/, exports/ or photos/."
- Then show me how to start the app, and wait until I tell you it opened in my browser.
```

After the build: tick the [`CHECKLIST.md`](CHECKLIST.md) before you put real names in. Extras on top: [`ADD-ONS.md`](ADD-ONS.md).
