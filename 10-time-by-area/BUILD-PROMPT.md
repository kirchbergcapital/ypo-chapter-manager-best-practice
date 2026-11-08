# Build prompt — your own hours app

Purpose: the one prompt you paste into your AI tool to build the optional hours app. It describes the whole app: three files, opened by double-click in Chrome or Edge, no install, no account, no internet.
Time: 30 to 60 minutes the first time, most of it the AI tool writing and testing. You answer a few questions and say yes to file changes inside your hours folder.

How to use it: copy **everything inside the grey box** — from "You are helping me" to the last line — and paste it as one message.
If you see code instead of a download link, say: *"Please create the three files as downloadable files."*

- **A coding tool** (Claude Code, Codex, the Claude desktop app with folder access, ChatGPT Work in the desktop app): open it in your hours folder `my-work/hours/` first. It writes the three files there.
- **A chat tool** (Claude, ChatGPT and others in the browser): paste the prompt into a new chat. It hands you the three files as downloads; you move them into `my-work/hours/`.

The prompt is in English on purpose: the code and the tests come out in English, and you can always ask your AI tool to explain any step in your own language.

Why it is this detailed: every requirement below is something you can see working — in the self-test page, in your folder, or in the [`CHECKLIST.md`](CHECKLIST.md).
Tested in a reference build (Oct 2026): about 10 minutes to build, self-test 60 passed, every check of the walk-through passed in Chrome. The self-test page shows whether it holds on your laptop.

```text
You are helping me, a non-technical person, build a small app for my own laptop. Work only in the current folder.
Before each step, tell me in one or two plain sentences what you are about to do, and wait for my yes before you
create or change a file. Never install anything, never use sudo or admin rights, never start a server, never
download anything. Do not choose libraries - no libraries at all. Keep the code small and readable, with comments
in plain English. If you cannot write files in a folder, give me the three files as downloads instead, one by one,
each with its exact file name.

GOAL
A local "where my hours go" app. I am a Chapter Manager; this is my own time, logged by area of work
(for example "Member communication", "Learning and chapter events", "Finance and administration"). The app runs from three files I open
by double-click in Chrome or Edge, on Windows or macOS:
  hours.html      the app (all user interface)
  hours-core.js   pure logic, no DOM, no browser APIs - everything that can be tested
  self-test.html  runs the tests in the browser and shows "N passed, 0 failed"
It reads and writes two files in my own hours folder: hours.csv (my log - the truth) and areas.txt (my areas).
It never connects to the internet, never writes into my chapter folder, never sends anything, and never estimates
hours: only minutes I confirm are saved.

0. CHECK FIRST
- Ask me whether I use Windows or macOS, and whether Chrome or Edge is installed. If neither, tell me to install
  one of them first (Chrome from google.com/chrome, Edge comes with Windows) and wait.
- If you can see the current folder: check that it is not my chapter folder - if it contains a folder named
  00-handover or 03-events, stop and tell me: "This looks like your chapter folder. Your hours live in your own
  folder, for example my-work/hours." Then wait.
- If areas.txt or hours.csv already exist in the folder, never overwrite or change them while building.

1. TECH BASE
- Exactly three files: hours.html, hours-core.js, self-test.html. Plain HTML, CSS and JavaScript. No TypeScript, no
  build step, no package.json, no npm, no Node requirement, no frameworks, no CDN, no web fonts, no images from
  anywhere (use system fonts and plain CSS).
- Load the logic as a classic script: <script src="hours-core.js"></script> - NOT type="module". Browsers block ES
  modules from file:// pages (the page is opened from disk, and module scripts need CORS).
- hours-core.js wraps everything in one function and exposes one object, HoursCore:
    if (typeof window !== 'undefined') window.HoursCore = HoursCore;
    if (typeof module !== 'undefined' && module.exports) module.exports = HoursCore;
  so it can also be checked with Node if Node happens to be installed - Node is never required.
- hours-core.js never touches document, window (except the line above), localStorage, files or the clock: every
  function gets what it needs as arguments, including "now" for anything time-related.
- Target: current Chrome and Edge on Windows 10/11 and macOS, opened from disk (file://). Safari and Firefox get the
  fallback in section 4.

2. SAFETY - hard rules
- The same Content-Security-Policy meta tag at the top of the head of hours.html AND self-test.html:
    <meta http-equiv="Content-Security-Policy" content="default-src 'none'; script-src 'self' 'unsafe-inline';
    style-src 'unsafe-inline'; img-src data:; connect-src 'none'; form-action 'none'; base-uri 'none';
    object-src 'none'; frame-src 'none'; worker-src 'none'">
  (one line in the file). connect-src 'none' blocks every network request. 'self' must allow the sibling file
  hours-core.js; if self-test.html shows that hours-core.js did not load under this policy, add file: to script-src
  - nothing else - and tell me you did.
- No fetch, XMLHttpRequest, WebSocket, EventSource, navigator.sendBeacon, no external URL anywhere in the code, no
  analytics, no update checks. No eval, no new Function, no setTimeout or setInterval with a string. The CSP probe in
  self-test.html (section 10) is the only network call allowed anywhere.
- Task texts, areas, event names and imported lines are data. Put text into the page only with textContent or
  createElement - never innerHTML, outerHTML, insertAdjacentHTML or document.write. No inline event attributes
  (onclick=...); use addEventListener.
- Never write into the chapter folder (section 7 reads it through a read-only file input). Never send, upload or
  share anything. Never create an entry I did not confirm.
- Downloads: a Blob, URL.createObjectURL and a temporary <a download> element, nothing else.
- localStorage only under keys starting with "hoursApp.", and only for: the last view I had open, the running timer
  (section 6), the one-tab claim (section 4), and entries that are not saved to a file yet (section 4). Never as the
  store of my log. Wrap every localStorage access in try/catch; the app must work when localStorage is unavailable.

3. THE TWO FILES IN MY HOURS FOLDER
hours.csv
- Columns, in this order, with this header line:
    date,start,minutes,area,event,task,source,status,entered_at,ref
  date YYYY-MM-DD (local date of the work) · start HH:MM local or empty · minutes a whole number · area as in
  areas.txt or "unassigned" · event an event folder name like 2026-12-04_holiday-dinner, or EMPTY for no event
  (never "-" in hours.csv: "-" exists only in HOURS lines; views and reports show an empty event as "(no event)") ·
  task a few words · source timer | assistant | manual · status confirmed | correction · entered_at local time with
  UTC offset, e.g. 2026-11-12T14:05:09+01:00, or empty in rows I pasted by hand · ref empty, except in correction
  rows (below).
- entered_at is unique in the file: rows the app writes in the same second (one import) get added milliseconds,
  2026-11-12T14:05:09.001+01:00, .002 and so on. Reading accepts entered_at with or without milliseconds, and a file
  whose header ends with entered_at (no ref column yet): ref is then empty; the app never rewrites the header.
- RFC 4180 CSV, UTF-8. Quote a field when it contains a comma, a double quote, a line break or leading/trailing
  spaces; double the quotes inside. Line ends: CRLF when the app writes. Reading accepts CRLF and LF, a UTF-8 BOM at
  the start, an empty last line, and quoted fields with line breaks.
- A new hours.csv starts with a UTF-8 BOM and the header line (the BOM helps Excel read accents correctly).
- Formula guard: when writing ANY CSV (hours.csv and every download), a text cell (area, event, task, source,
  status, ref) that starts with = + - @, a tab, a carriage return or ' gets a ' in front. When reading, exactly one
  leading ' is removed when it is followed by one of these characters (= + - @ tab CR '), so a round trip is
  lossless. The minutes column is written as a plain
  number, never guarded.
- Append-only: new rows go at the end; existing lines are never changed, reordered or removed. Before appending,
  re-read the file and, if it does not end with a line break, write one first.
- Unfinished last line: if the last record of hours.csv cannot be read (for example an unclosed double quote), never
  append after it. Refuse saving, keep the entries pending (memory and localStorage) and show "hours.csv ends with an
  unfinished line - open it in Notepad or TextEdit, fix or delete the last line, then click Save again".
- Validate the final record using the same structural rules as parseCsv; a malformed or uncounted row must never
  acknowledge a pending entry, and ambiguous timestamp matches must preserve it for review.
- Counting: status "confirmed" (minutes 1 to 1440) and status "correction" (minutes may be negative) count. Any row
  with another status, or a row that cannot be read, is shown as "not counted" with its line number - never fixed,
  never guessed.
- Corrections, never silent edits. An entry is an original row (status confirmed) plus every correction row whose
  ref points to it. ref = the original row's entered_at; if that is empty (a row I pasted by hand), ref = "row:<n>",
  the original's record number in hours.csv (1 = first row after the header). A correction always points to the
  original row, never to another correction.
- An entry's current net state: its area and event as last moved, and its net minutes = the original's minutes plus
  all its corrections. "Correct" pre-fills the current net values and appends only the difference: other minutes =
  one row with the difference; another area or event = one row with minus the net minutes in the current area/event
  and one with plus the new minutes in the new one. "Delete" is offered only while the net minutes are above 0 and
  appends one row with minus the net minutes; a second delete is refused. Each correction row repeats the original's
  date, has source manual, status correction, the task "correction: <original task>" and the ref.
- A correction row whose ref matches no row (or is empty) still counts, and is shown as its own line.
- Generate correction and deletion rows only from the freshly re-read hours.csv, right before writing: if the entry's
  net state there differs from what the form showed (for example I changed the file in Excel meanwhile), write
  nothing, show the current values and ask me to confirm again.
areas.txt
- One area per line. Optional keywords after the first colon, separated by commas:
    Learning and chapter events: venue, speaker, run of show
  Area names and event names are arbitrary text; use Map or null-prototype dictionaries for every lookup and total
  keyed by them, including constructor, toString and __proto__. Area names are trimmed, compared case-insensitively after Unicode NFC normalisation, and may not contain the
  character "·". Blank lines and lines starting with # are ignored. Duplicate area names: keep the first, report the
  rest. More than 15 areas: show a gentle hint that about ten work best; still accept them.
- If areas.txt is missing, offer "Create areas.txt with the default list" - this list, in this order, built into
  hours-core.js: Member communication · Learning and chapter events · Forum logistics · Membership lifecycle ·
  Officers ExCo and board · Game plan commitments and reporting · Region and global YPO ·
  Finance and administration · Knowledge base handover and own learning.
- An "Edit areas" view: a text box with the current areas.txt; Save writes the whole file (this is the one file the
  app may rewrite; in the fallback of section 4 the button is "Download areas.txt"). Old rows keep whatever area
  they had. Right before Save, re-read areas.txt: if it changed since the view was opened, show both versions and
  let me choose which one to keep. If the write fails, abort it (writable.abort()) and keep the old file.

4. STORAGE - one click per session
- First screen: a large button "Pick my hours folder" (Chrome, Edge) using window.showDirectoryPicker with
  { id: 'hours-folder', mode: 'readwrite' }. The browser asks for permission; I pick the folder again in each new
  session - design for that, do not store folder handles.
- Refuse a folder that contains a sub-folder 00-handover or 03-events: "This looks like your chapter folder. Your
  hours live in your own folder." Nothing is read or written there.
- One tab saves: on open, the app claims the localStorage key hoursApp.activeTab with a random tab id and a
  timestamp, and refreshes the timestamp every 5 seconds. A tab that finds another tab's claim fresher than 15 seconds
  shows "The app is already open in another tab - use that one" and disables every save, import, correct and delete
  button (views still work). A claim older than 15 seconds may be taken over. On close (pagehide) the tab releases
  its claim. Without localStorage there is no claim; then show the hint "Use the app in one tab only".
- On gaining the claim (at open or by takeover), first reload the unsaved entries and the timer state from
  localStorage, then enable the buttons. A tab without the claim never writes hoursApp.pending or
  hoursApp.runningTimer - not even from its own older copy in memory.
- A save keeps its claim for the whole operation: check the claim again right before write() and before close();
  if it was lost, abort the stream, write nothing and keep every pending entry.
- After picking: read areas.txt and hours.csv. Missing hours.csv: offer "Create hours.csv" (BOM + header). Show the
  folder name at the top ("Saving to: hours").
- Writing: createWritable({ keepExistingData: true }), seek to the current end, write, close. If any write fails
  (for example the file is open in Excel on Windows), keep the entry in memory and in localStorage, show "Not saved -
  close hours.csv in other programs, then click Save again", and keep the entry until it is written.
- Fallback when showDirectoryPicker is missing (Safari, Firefox) or permission is denied: two buttons, "Open
  hours.csv" (a file input, reads the file) and "Open areas.txt" (optional; default list otherwise). New entries are
  kept in memory and in localStorage, and a banner always shows "N entries not saved to file yet" with a button
  "Download my log". The download is the opened file exactly as it was, plus the new rows at the end, named
  hours-YYYY-MM-DD-HHMM.csv (local date and time of the download) - never hours.csv. Next to the button: "Your whole
  log plus the new rows. Rename it to hours.csv yourself when you are sure it is the newest copy." If no hours.csv
  was opened in this session, the button says "Download new entries" and the file is named
  hours-new-YYYY-MM-DD-HHMM.csv - so I can never overwrite my log with a short file by mistake.
- Before every fallback export, revalidate all pending corrections against the hours.csv used for that export;
  retain correction intent across reloads (store the original's ref and the wanted net values, not only the
  difference) and require renewed confirmation if the original's current state changed. A freshly validated
  correction whose wanted values already equal the current net values is complete without writing rows and must be
  removed from pending entries.
- After opening a log, reconcile pending entries against its valid saved rows immediately, clear acknowledged
  entries from memory and localStorage, and refresh the pending banner without requiring another export.
- When the page opens and localStorage holds unsaved entries, show them in the banner first and offer to save them
  (after a duplicate check) once the folder is picked or the file is opened.
- Warn before the page closes (beforeunload) while a timer runs or entries are unsaved.

5. IMPORT BOX - the assistant's hours lines
- Format, one line per entry, fields separated by the middle dot "·" (U+00B7):
    HOURS · YYYY-MM-DD · <area> · <event folder or -> · <task in a few words, roles not names> · <minutes> min · suggested|confirmed
- Parsing: ignore blank lines and any text before "HOURS" on a line (list markers, quotes); "HOURS", "min" and the
  status are case-insensitive; any amount of spaces around each "·". The first four fields after HOURS are date,
  area, event; the last two are minutes and status; everything between event and minutes is the task (rejoin with
  " · " if it contained middle dots "·"). Date must be a real calendar date; minutes a whole number from 1 to 1440.
  Anything else: listed as "could not read" with its line number and the line itself - never guessed, never
  imported.
- Preview table before anything is saved: date, area, event, task, minutes, status, and a check box. "confirmed"
  lines are ticked; "suggested" lines show "to confirm", unticked, with editable minutes - ticking one confirms it.
- Area not in areas.txt: shown as "unassigned", never silently mapped to another area. Next to it, a suggestion
  from the keywords (section 9, suggestArea) and a drop-down to choose; left alone it is imported as "unassigned".
- Duplicates: treat event "-" and an empty event cell as the same event first. A line with the same date, area, event, task (trimmed, case-insensitive, spaces collapsed) and
  minutes as a row already in hours.csv, or as an earlier line in the same paste, is flagged "already in your log"
  and not imported unless I tick it. The same rule everywhere (import, unsaved entries, fallback export): only an
  exact previously written row identity (same entered_at) may be silently removed from pending entries; every other
  match is shown to me for review and never dropped silently.
- Import button: writes the ticked lines as rows with source assistant, status confirmed, start empty; an event "-"
  is written as an empty event cell.

6. TIMER AND MANUAL ENTRY
- One button per area from areas.txt, plus an optional event picker: "(no event)" (writes an empty event cell), the
  events known from hours.csv and from comms logs (section 7), or a new name typed in.
- Click an area: its timer starts and shows the running time. Only one timer at a time: while one runs, the other
  area buttons are disabled with the hint "Stop the running timer first".
- The running timer survives a reload or closing the page: keep { area, event, startedAt } in localStorage under
  hoursApp.runningTimer; when the page opens, restore it and show it running, counted from the original start.
  Save or Discard clears it.
- Stop freezes the minutes: the stopped, not yet saved state ({ area, event, startedAt, minutes } and the form
  fields) is kept under hoursApp.runningTimer with "stopped": true; a reload restores the review form with the frozen
  minutes, never a running timer again.
- Stop: a small form with the minutes (rounded to the nearest minute, at least 1), the area, the event and a task
  field, all editable; Save writes one row (source timer, status confirmed, start HH:MM, date = local date of the
  start); Discard writes nothing.
- Manual entry form: date (default today), area, event, task, minutes - Save writes one row (source manual, status
  confirmed). Task: one line, line breaks become spaces.
- The Today and Week views show one line per entry (original plus its corrections, at its current net state;
  entries at 0 net minutes show as "deleted"). Each line has "Correct" (the same form, pre-filled with the net
  values) and "Delete"; both append correction rows (section 3).
- Under every task field - the stop form, the manual entry form, the Correct form and the import preview - a fixed
  grey hint: "Roles, not names. Forum: logistics only - never a topic or a name." The text is the constant
  HoursCore.TASK_HINT.

7. EVENT HOURS FROM COMMS LOGS - read-only
- Button "Read event hours from my chapter folder": an <input type="file" webkitdirectory> - it can only read, so
  the app has no way to write there. Use only files whose path (webkitRelativePath) ends with
  03-events/<event folder>/comms-log.md - this works whether I pick the chapter folder or 03-events itself; skip
  _event-template. Read nothing else. The event name is the event folder's name. Decide this with the pure function
  commsLogEvent(relativePath) (section 9): it returns the event folder name or null, and the page uses nothing else.
  After reading, show one line: "Read N comms logs, M hours" - so I can see at once if nothing was found.
- In each comms log, count only lines that start with a date YYYY-MM-DD (after optional spaces or a "- " list
  marker) and end with the middle dot, a number and "h": "· 0.5h", "· 2h", "·1.5 h" (optional spaces, "." or ","
  as decimal mark, case-insensitive). Other lines are ignored. Sum per event folder and per date.
- Show these hours per event as "from comms logs", in their own column - never added into the totals from
  hours.csv.
- Double counting: when the same event has rows in hours.csv (any source) AND comms-log hours on the same date,
  show a warning line "Possible double counting: <event>, <date>" - a hint only, nothing is changed.
- Nothing from the chapter folder is stored: not in hours.csv, not in localStorage.

8. VIEWS AND THE MONTH REPORT
- Views: Today · This week (Monday to Sunday) · Month by area · Month by event, with previous/next for week and
  month. Remember only the last view in localStorage. Show minutes as h:mm. An empty event shows as "(no event)" in
  every view, the report and the report CSV.
- Dates: always local dates. Never parse "YYYY-MM-DD" with new Date(string) - that reads it as UTC; split the string
  and use new Date(year, month - 1, day). Never use toISOString() for a local date.
- Month report page: title "Where my hours went - <Month YYYY>", the line "Confirmed entries from my own hours log.
  Suggested lines are not counted.", totals by area (in areas.txt order, then "unassigned" and unknown areas), totals
  by event with the "from comms logs" column next to it, the double-counting hints, and a grand total.
- "Not counted" rows (section 3) show as a warning with their line numbers in every view (Edit areas included) and
  in the month report;
  the report CSV gets one line per warning, starting with "Warning".
- A check box "Include task texts", OFF by default. Off: no task text appears anywhere in the report or its CSV.
- "Print or save as PDF" uses window.print(); a print style sheet prints the report section only - every other section (timer, import box and its preview, views, forms, buttons) is hidden in print.
- "Download report CSV": hours-report-YYYY-MM.csv with the same totals (formula guard applies).
- No targets, no comparisons, no percentages of anything, no names - only my own numbers.

9. hours-core.js - functions (pure, all tested)
parseCsv(text) · toCsv(rows) · guardCell(text) · unguardCell(text) · parseAreas(text) · defaultAreasText() ·
suggestArea(text, areas) (the area whose keywords or name occur most often in the text, case-insensitive; a tie or
no hit returns null) · matchArea(name, areas) · parseHoursLine(line) · parseHoursBlock(text) ·
isDuplicate(entry, rows) · commsLogEvent(relativePath) · sumCommsLog(text) · doubleCountWarnings(rows, commsHours) · localDateString(date) ·
parseLocalDate(ymd) · weekRange(ymd) · monthRange(ym) · aggregate(rows, from, to, by) (by = "area" | "event" |
"day") · startTimer(state, area, event, now) · stopTimer(state, now) · correctionRows(original, changed, now) ·
newRow(fields, now) · buildMonthReport(rows, ym, areas, commsHours, { includeTasks }) · reportToCsv(report) ·
entries(rows) (originals with their corrections and net state) · deleteRows(entry, now) · uniqueEnteredAt(rows, now)
· lastRecordComplete(text) · claimTab(stored, tabId, now) (returns { canSave, claim }) · takeOver(storedPending, memoryPending) · fallbackFileName(kind, now)
(kind = "log" | "new") · areasChanged(openedText, currentText) (line ends and a trailing line break do not count).
startTimer refuses while another timer runs; stopTimer refuses when none runs; both return a new state, never
change their input. The timer state is plain data ({ area, event, startedAt } with startedAt in milliseconds), so it
survives JSON.stringify and JSON.parse. TASK_HINT is the exact hint text of section 6.

10. TESTS - self-test.html
- Loads hours-core.js the same way as hours.html, under the same CSP meta tag. First checks: HoursCore exists (else
  a big red line "hours-core.js did not load - check the Content-Security-Policy line"), and a network probe:
  fetch('https://example.invalid/csp-probe') must be blocked by the policy - listen for the securitypolicyviolation
  event with connect-src; show "Network blocked: yes" or a red "no".
- Fictional data only: "Lakeside Chapter (fictional)", events like 2026-12-04_holiday-dinner and
  2026-10-22_wine-dinner, roles instead of names, phone numbers only starting with +00. No real data anywhere.
- Cover at least:
  HOURS lines - a valid confirmed line; a suggested line; malformed lines (missing field, "min" missing, 0 min,
  1441 min, 2026-02-30, text instead of a number) reported with line numbers; extra spaces and a list marker
  before HOURS; a task containing "·"; unicode in area and task (é, ü, an emoji).
  CSV - round trip with commas, double quotes, line breaks and leading spaces; BOM and CRLF read correctly; a
  missing final line break; the formula guard on = + - @ for text cells and lossless reading back; minutes -15
  written unguarded.
  Areas - comments and blank lines ignored; keywords parsed; case and NFC matching; duplicate names; suggestArea
  with a clear winner, a tie and no hit; an imported unknown area stays "unassigned".
  Duplicates - the same line twice in one paste; a line already in hours.csv; a line differing only in case and
  spaces of the task; the same date, area, task and minutes but another event is NOT a duplicate.
  Odd names - areas and events named "__proto__", "constructor" and "toString", 30 minutes each: every total is a
  number and the grand total is 90.
  No-op correction - a correction whose wanted values equal the current net values writes no row and leaves no
  pending entry.
  Fallback corrections - a pending correction (60 shown, wanted 20) and an export base file where the original is
  now 30: nothing is written for it, and it is returned for renewed confirmation with the current value 30.
  Comms-log paths - commsLogEvent: "chapter/03-events/2026-10-22_wine-dinner/comms-log.md" and
  "03-events/2026-10-22_wine-dinner/comms-log.md" give "2026-10-22_wine-dinner"; "chapter/03-events/_event-template/
  comms-log.md", "chapter/03-events/x/notes.md", "chapter/00-handover/comms-log.md" and
  "chapter/03-events/a/b/comms-log.md" give null.
  Comms logs - "· 0.5h", "· 2h", "·1.5 h", "· 1,5h", a line without hours, the template's own purpose line, a line
  not starting with a date - and the sum per event and date.
  Double counting - warning when hours.csv and a comms log share event and date; none on different dates.
  Aggregation - today, week Monday to Sunday across a month end, month boundaries (2026-10-31 in October,
  2026-11-01 in November), corrections reduce the sum, rows with other statuses are not counted; local dates:
  localDateString(new Date(2026, 9, 25, 0, 30)) is "2026-10-25" and parseLocalDate("2026-11-01") gives
  1 November in any time zone.
  Timer with a fake clock - start, stop after 25 min gives 25; 20 seconds gives 1; a second start while running is
  refused; stop without a running timer is refused; the row's date is the local start date; a "reload" (the state
  through JSON.stringify and JSON.parse, as from hoursApp.runningTimer) and a stop 25 min after the original start
  gives 25; stop after 10 min, then "reload" 60 min later: the review form shows 10, not 70.
  Corrections - fewer minutes, another area, delete: the right rows, the original row untouched. Net state: 60,
  corrected to 30, then to 20 gives net 20 (second correction row -10); a correction to another area moves the net
  minutes there; delete writes minus the net minutes, a second delete is refused; ref is the original's
  entered_at, or "row:<n>" for a row without entered_at; a correction whose ref matches nothing still counts.
  entered_at - three rows written in the same second get three different values.
  Old header - a file whose header ends with entered_at reads with ref empty.
  Unfinished last line - text ending inside an open double quote: lastRecordComplete is false, nothing is appended.
  Formula guard - "'=SUM(1,1)" and "'quoted" round trip unchanged; "=1+1" is written as "'=1+1" and read back.
  One tab - a claim by another tab 5 s old: canSave false; 20 s old: taken over, canSave true; the own claim:
  canSave true. Takeover - the new owner's pending list is the one read from storage at takeover, not its old
  in-memory copy (takeOver(storedPending, memoryPending) returns storedPending). Lost claim -
  a save whose claim check fails before close() writes nothing and keeps its entries (simulate with a stub writer).
  Stale correction - an entry shown at 60 net, the file re-read with the original at 30: no row is generated and the
  current value 30 is returned for confirmation.
  Fallback names - fallbackFileName("log", 2026-11-12 14:05) is "hours-2026-11-12-1405.csv", "new" gives
  "hours-new-2026-11-12-1405.csv"; neither is ever "hours.csv".
  Areas - areasChanged is true for a changed line, false for the same text with CRLF instead of LF.
  Not counted - a row with status "draft" and an unreadable row appear as warnings with line numbers in the month
  report and as "Warning" lines in its CSV.
  Report - no task text with includeTasks false (search the whole report and its CSV for a fixture task text);
  task texts present with true; comms-log hours in their own column and not in the totals.
  No event - an imported line with event "-" and a timer row without event write an empty event cell (no "'-"
  anywhere in the CSV), and views and the report show "(no event)".
  Task hint - HoursCore.TASK_HINT is exactly "Roles, not names. Forum: logistics only - never a topic or a name."
- Show one line per test (name, pass or fail with the reason) and at the top, large: "N passed, 0 failed".

11. FINISH
- Write the three files. Then check the code yourself against sections 2 and 9 and tell me in a few lines: no
  network calls, no innerHTML, no eval, no libraries, the CSP line is in both HTML files.
- If you can run Node here, you may check hours-core.js with it; the proof for me is self-test.html.
- Then walk me through, one step at a time, waiting for my "done" after each:
  1) open self-test.html in Chrome or Edge (Mac: right-click, Open With, Google Chrome; Windows: right-click,
     Open with, Microsoft Edge) and read me what the top line should say;
  2) open hours.html the same way, click "Pick my hours folder", choose my hours folder, allow editing;
  3) one timer run: start one area, stop it, see the grey hint under the task field, check the minutes, save, then
     open hours.csv in Notepad or TextEdit and find the new row;
  4) one import: paste a suggested line and a confirmed line you give me (fictional), confirm the first, import,
     paste the confirmed one again and see it flagged as a duplicate;
  5) one month report: open it, see that task texts are off, print preview, download the report CSV.
```

Next: tick [`CHECKLIST.md`](CHECKLIST.md). Something does not work? [`TROUBLESHOOTING.md`](TROUBLESHOOTING.md).
