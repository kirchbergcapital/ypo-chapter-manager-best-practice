# Troubleshooting

Purpose: the usual bumps and the quick way past each one.
First move, every time: paste the exact message into Claude Code in the app folder and ask *"What does this mean, and what should I do?"* — it knows the app it built.

## Getting started

| What you see | What helps |
|---|---|
| A browser window opens when you first type `claude` | That is the login. Sign in with your Claude account (Pro or Max), then return to the terminal. Step by step: [`../setup/macos.md`](../setup/macos.md) · [`../setup/windows.md`](../setup/windows.md) |
| "Do you trust the files in this folder?" | Yes, for your own `whatsapp-app` folder |
| Claude Code asks to run a command and you are unsure | Yes to `npm install`, `npm test` and file changes inside the folder. No to opening a port, extra downloads, installing outside the folder, `sudo`/admin, or opening or printing `./auth`, `./data` or `./exports`. Ask *"What does this do, in one sentence?"* first |
| A dragged folder path does not work | Type the command up to `--out `, then drag the folder into the terminal window; do not add your own quotes around it |

## Linking

| What you see | What helps |
|---|---|
| The QR code expires before you scan it, or the app stops after three codes | Open WhatsApp → Settings → **Linked devices** → **Link a device** on your phone **first**, then run `npm run link` and scan straight away |
| No QR code appears at all | The app should draw it directly in the window. Paste what you see into Claude Code and ask it to check that the QR code is written with `process.stdout.write`, not `console.log` |
| Two attempts did not work | Take a break from the app and use WhatsApp's own "Export chat" (stage 1 in [`../03-communication/whatsapp.md`](../03-communication/whatsapp.md)) for today — same result, one chat at a time. Try again later with the rows below |
| "Run this in a terminal window" | You started `link` inside Claude Code or the desktop app. Open *Terminal* (macOS) or *PowerShell* (Windows), go to the app folder, run it there |
| "No saved login yet - run npm run link first" | `listen` needs a link first. Run `npm run link` once, scan, then use `listen` from then on |
| The QR code looks broken or will not scan | Make the terminal window bigger, or zoom out (macOS `Cmd -`, Windows `Ctrl -`) until the whole code fits; a plain light or dark theme scans best |
| "WhatsApp logged this laptop out" | The link was ended — on your phone, or by WhatsApp after your phone was unused for a while `[verify]`. Delete the `auth` folder in the app folder by hand, then `npm run link` again |
| "Another session took over" (connection replaced) | The app runs in a second window, or on another laptop with the same keys. Close the other one, start again |
| "The app is already running in another window" | Usually `link` is still open in another window — it keeps listening, so you do not need `listen` as well. Use that window, or stop it with **Ctrl-C** first. No other window? The message names a lock file left over from a crash — delete that one file by hand and start again |
| Several laptops under Linked devices, not sure which is the app | Look for the name and date you noted when linking (step 4 in the [README](README.md)). Still unsure: log out all entries you do not recognise, then link again |
| Linking fails again and again, even with a fresh QR code | WhatsApp may have changed its web protocol. Ask Claude Code: *"Is there a newer stable Baileys version than 6.7.24 — no release candidate, not 6.17.x? If yes, explain, update the exact pin, and run the tests."* |

## Node, npm, Git and the terminal

| What you see | What helps |
|---|---|
| `node` or `npm` is "not found" / "not recognized" | Close the terminal window and open a new one after installing Node. Still missing: install the **LTS** version again from [nodejs.org/en/download](https://nodejs.org/en/download) |
| `node --version` shows `v18` or lower | Install the current **LTS** version from [nodejs.org/en/download](https://nodejs.org/en/download); it replaces the old one |
| `npm install` fails with `spawn git` or "git not found" | Git is missing. macOS: type `git --version` and accept the offer to install the command line developer tools. Windows: install Git for Windows from [git-scm.com/downloads/win](https://git-scm.com/downloads/win). Then open a new terminal window and ask Claude Code to run `npm install` again |
| `claude` is "not found" after installing | Open a new terminal window. Still missing: see [Troubleshoot installation](https://code.claude.com/docs/en/troubleshoot-install) |
| `npm install` fails with `EPERM` and mentions the npm cache or "root-owned files" | An old installation left npm's cache locked. Do **not** run the `sudo chown` line npm suggests. Ask Claude Code to run `npm install --cache ./.npm-cache` instead — the cache then lives inside the app folder — and to add `.npm-cache/` to `.gitignore` |
| `npm install` fails for another reason | Paste the error into Claude Code. Never use `sudo` to get past it, and do not let it switch to another Baileys version on its own |

## Windows and PowerShell

| What you see | What helps |
|---|---|
| "running scripts is disabled on this system" when you type `npm …` | Type `npm.cmd` instead of `npm` — for example `npm.cmd run link`. It does the same thing |
| The app says `--chat` is missing although you typed it | PowerShell can swallow the `--` in npm commands. Use `npm.cmd run export -- --chat "…"` |
| A path with spaces does not work | Drag the folder into the window (PowerShell adds the quotes), or type the quotes yourself: `--out "C:\Users\you\WhatsApp exports"` (a folder on this laptop — not your chapter folder, not a synced folder) |
| You are in CMD, not PowerShell (`'irm' is not recognized`) | Open **PowerShell** from the Start menu — the prompt starts with `PS` |
| Symbolic-link tests are skipped | Expected on Windows without the permission to create links; the app's checks still run |

## Network and firewall

| What you see | What helps |
|---|---|
| The app keeps reconnecting and gives up after 8 attempts | Check the internet connection. Company networks, hotel Wi-Fi or a VPN sometimes block WhatsApp Web; try your home network or your phone's hotspot |
| A firewall window asks whether Node may accept incoming connections | The app only connects out to WhatsApp and should not need incoming connections — you can decline. Ask Claude Code why the app asked; it should not open a port |
| WhatsApp Web works in the browser, the app does not | Same cause as "linking fails again and again" above: ask for a newer stable library version |

## Chats and exports

| What you see | What helps |
|---|---|
| "Use one of these names exactly" | The app exports only on an exact name. Copy one name from the list, in quotes, and run the export again |
| Two chats have the same name | The app will not guess. Rename one of them on your phone (group name or contact name), let `listen` run a moment, then export |
| A chat is not in `npm run chats` | The app knows only chats from the history it got when you linked, plus messages that arrived while `listen` ran. Keep `npm run listen` open while you work; try `npm run chats -- --search <part of the name>` |
| Older messages are missing from an export | Same reason — and the history WhatsApp shares at linking is limited `[verify]`. The export covers 7 days unless you add `--days`. For an older stretch, use WhatsApp's own "Export chat" (stage 1 in [`../03-communication/whatsapp.md`](../03-communication/whatsapp.md)) |
| Names show as phone numbers, or as "Unknown (lid)" | The app uses only the names WhatsApp shares; *Unknown (lid)* means WhatsApp shared neither name nor number. Your assistant should write "unknown number", never guess a name |
| "This looks like a Forum chat" | Working as intended. Forum stays out |
| "Skipped N unreadable lines" | A save was cut off, for example by a crash. The rest is fine; the app never repairs or rewrites its files |
| Where did the export go? | The app prints the full path at the end of every export. Without `--out` it is the `exports` folder inside the app folder |

Still stuck: start again from step 4 in the [README](README.md), or remove the app as described there and rebuild it — the build prompt gives you a fresh copy in 10 to 30 minutes.
