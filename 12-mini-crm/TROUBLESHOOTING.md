# Troubleshooting — your mini CRM

Purpose: the usual bumps with the mini CRM, and the quick way past each one.
Tested in a reference build (Nov 2026): about 10 minutes to build, self-test `0 failed`.

## Building

| What you see | What to do |
|---|---|
| The tool says Node.js is missing or older than 24 | Install the newest version marked *LTS* — Node 26 in November 2026; Node 22 is too old for this app — [`../setup/macos.md`](../setup/macos.md) § 3 or [`../setup/windows.md`](../setup/windows.md) § 3. Open a **new** Terminal or PowerShell window afterwards, then paste the prompt again |
| The tool wants to run `npm install` | Say no. The app needs no packages; paste: *"No packages — Node's built-in modules only, as the prompt says."* |
| The tool stops: the folder is synced | Move `chapter-crm` to a place on your laptop outside iCloud Drive, OneDrive, Google Drive and Dropbox, open the tool there and paste the prompt again |
| A chat in the browser gives you code to copy | A browser chat cannot run the app. Use a coding tool on your laptop (README step 3) |
| The self-test shows failed tests | Paste the failing lines into the tool: *"Fix these until the self-test shows 0 failed."* |

## Starting

| What you see | What to do |
|---|---|
| Mac: "cannot be opened" or "Apple could not verify …" | Double-click once, close the message, then *System Settings* → *Privacy & Security* → scroll down → *Open Anyway* next to `start-mac.command`. On older macOS: right-click → *Open* → *Open*. Only the first time |
| Mac: nothing happens on double-click | Ask your AI tool: *"Make start-mac.command double-clickable."* — once |
| Windows: SmartScreen warns about `start-windows.bat` | *More info* → *Run anyway*. The file only starts `node server.js` in this folder |
| "Port in use" | The app is already running in another window — use that one, or close it and start again |
| The browser does not open by itself | Copy the address with `?t=…` from the start window into your browser |
| Windows asks whether to allow Node.js on networks | Choose *Cancel* or *No*. The app still opens on this laptop |
| The browser shows an empty list or an error code (401) | Use the address the start window prints, with `?t=…` at the end. Bookmarks of an old address stop working after a restart — on purpose |

## Using it

| What you see | What to do |
|---|---|
| Import shows strange characters (Ã©) | Save the file in Excel as *CSV UTF-8*, then import again |
| Import puts everything into one column | The file uses another separator — the preview shows it; save as CSV with commas or semicolons |
| "Email already exists" | The same email is already in the list. Edit that person instead of adding a second one |
| A photo is not shown | Tick *photo OK*. Still missing? Export the photo as JPEG (Mac Photos: *File* → *Export*; iPhone photos are often HEIC) and upload that file |
| A name in Excel starts with `'` | On purpose: the export's guard against formulas. Keep it |
| Everything in one column in Excel | Export again with the other separator (semicolon or comma) |

## Data

| Question | Answer |
|---|---|
| Where is my data? | In `crm.db` in your `chapter-crm` folder, and in `photos/` |
| How do I hand it over? | *Backup now*, then give your successor the newest file from `backups/` and the `photos/` folder — through the chapter storage, not by private mail. Never copy `crm.db` itself while the app runs |
| How do I restore a backup? | Close the app. If a `crm.db` is there, rename it and its `-wal`/`-shm` files to `crm-old…` first. Copy the backup file into `chapter-crm`, rename it to `crm.db`, put the `photos/` folder next to it, start the app |
| Can two people use it? | Not at the same time. One laptop, one Chapter Manager; others get exports. Two tabs are fine — if one is out of date, it asks you to reload instead of overwriting |
| I want to start again | Close the app first. Then rename all three together — `crm.db`, `crm.db-wal`, `crm.db-shm` — to `crm-old.db`, `crm-old.db-wal`, `crm-old.db-shm`, and start again. Never delete a database without a backup |

Still stuck: paste what you see into your coding tool and ask it to explain in plain words — or rebuild the app from [`BUILD-PROMPT.md`](BUILD-PROMPT.md); your `crm.db` stays as it is.
