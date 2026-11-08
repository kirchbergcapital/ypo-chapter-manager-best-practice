# Troubleshooting

Purpose: the usual bumps with the hours line and the hours app, and the quick way past each one.
The hours app was tested in reference builds (Oct 2026): self-test 0 failed, every check of the walk-through passed in Chrome. `0 failed` is the check; the number passed varies.
First move, every time: paste the exact message or a screenshot (no personal data in view) into your AI tool and ask *"What does this mean, and what should I do?"*

## The hours line (Levels 1 and 2)

| What you see | What helps |
|---|---|
| The assistant does not offer an hours line | Your `house-rules.md` still has the old rule 19. Copy the section *Game plan and hours* from [`../02-your-assistant/template-folder/house-rules.md`](../02-your-assistant/template-folder/house-rules.md) into your own `house-rules.md` (and upload it again to the project at Level 1), then start a fresh chat |
| It offers a line after every small step | Say *"One hours line per finished task, please — not per step."* Or *"no hours today"* to pause it for the session |
| It uses an area that is not in your list | Upload your `areas.txt` to the project (Level 1) or tell it where the file is (Level 2). Until then it falls back to the default list in [`areas-template.txt`](areas-template.txt) |
| A line shows `confirmed` although you never gave the minutes | Say so: only minutes you confirm count (house rule 19). Ask it to change the line back to `suggested` and give your own number |
| The pasted rows land in one cell in Excel | Paste into `hours.csv` with Notepad (Windows) or TextEdit (Mac), not in Excel. Excel is for reading the file later |
| TextEdit shows formatting or saves as `.rtf` | *Format → Make Plain Text* before you paste, then save. The name stays `hours.csv` |

## Opening the app

| What you see | What helps |
|---|---|
| `hours.html` opens in Safari or Firefox | Your default browser opens it. Right-click → *Open With* → Google Chrome (Mac), or right-click → *Open with* → Microsoft Edge (Windows). Safari and Firefox work too, with **Open** and **Download** instead of saving straight into the folder |
| `self-test.html` says "hours-core.js did not load" | The three files must sit in the same folder, with exactly these names. Still red: ask your AI tool *"self-test says hours-core.js did not load under the Content-Security-Policy — please check the script tag and the policy line"* |
| `self-test.html` shows failed tests | Copy the failing lines into your AI tool and ask it to fix the app, then reload the self-test |
| The chat tool gave you files named `hours (1).html` or with `.txt` at the end | Rename them to exactly `hours.html`, `hours-core.js`, `self-test.html`. Windows: File Explorer → View → Show → File name extensions first |
| A blank page | Open `self-test.html` first — it shows what is missing. Then ask your AI tool with that line |

## Folder and saving

| What you see | What helps |
|---|---|
| No "Pick my hours folder" button, only **Open hours.csv** | You are in Safari or Firefox. Use Chrome or Edge to save straight into the folder — or work with Open and Download. On a Mac, install Chrome; treat Safari as a stopgap |
| The browser asks again for the folder every time | Expected: one click at the start of each session |
| "This looks like your chapter folder" | Working as intended. Pick your own `my-work/hours` folder |
| The browser will not let you pick a folder | Some browsers refuse top-level system folders such as your home folder or the whole Documents folder `[verify]`. Pick the `hours` folder inside them |
| "Not saved — close hours.csv in other programs" | The file is open in Excel (Windows locks it). Close it there, then click **Save** again. Your entry waits until it is written |
| Banner "N entries not saved to file yet" | Safari or Firefox: click **Download my log**. You get a file such as `hours-2026-11-12-1405.csv` — your whole log plus the new rows. Rename it to `hours.csv` yourself when you are sure it is the newest copy, and put it in place of the old one |
| The download is called `hours-new-2026-11-12-1405.csv` | You did not open your `hours.csv` in this session, so the app will not offer a short file under the name of your log. Open `hours.csv` first, then download again — or add the rows by hand |
| The download is called `hours-2026-11-12-1405.csv` | On purpose: the app never names a download `hours.csv`, so nothing overwrites your log by accident. Rename it yourself when you are sure it is the newest copy |
| "hours.csv ends with an unfinished line" | The last line of the file is cut off — often a missing `"`. Open `hours.csv` in Notepad or TextEdit, fix or delete the last line, save, then click **Save** again. Your entry waits until then |
| "The app is already open in another tab" | Only one tab saves. Switch to the other tab, or close it and reload this one after a few seconds |

## Import

| What you see | What helps |
|---|---|
| "Could not read" for a line | The line is not in the exact hours-line form — a missing `min`, a date that does not exist, or a missing part. Ask the assistant for the line again in the exact form (house rule 20) |
| A line shows "to confirm" | It was `suggested`. Check the minutes, tick it, then import |
| A line shows "unassigned" | The area is not in your `areas.txt`. Choose one from the drop-down, or import it as unassigned and correct it later. Many of these? Add the area to `areas.txt` |
| "Already in your log" | The same date, area, event, task and minutes are already in `hours.csv`. Did the same task really happen twice? Then tick the line in the preview to import it anyway |

## Event hours from comms logs

| What you see | What helps |
|---|---|
| The browser asks to "upload" the files of a folder | That is the browser's word for letting a page read a folder `[verify the exact wording]`. The app has no internet connection; it only reads the `comms-log.md` files |
| An event shows no hours "from comms logs" | Only lines that start with a date and end with hours like `· 0.5h` count — the format in [`../04-knowledge-base/event-lifecycle.md`](../04-knowledge-base/event-lifecycle.md) § 1 |
| "Possible double counting" | The same event has hours in your log and in its comms log on the same day. Check whether they are the same work; if yes, keep one and remove the other from your log with **Delete** |

## Excel and the report

| What you see | What helps |
|---|---|
| Excel shows everything in one column | Your Excel expects semicolons. Open Excel first → *Data* → *From Text/CSV* → choose `hours.csv` → delimiter *Comma* `[verify the menu names]` |
| A task starts with `'` in Excel | The app's guard against formulas in text cells. It is removed again when the app reads the file |
| The printed report shows buttons | Use the app's **Print or save as PDF** button, not the browser menu, so its print style applies |
| You want task texts in the report | Tick **Include task texts** — off by default, so you decide what you share |

Still stuck: open `self-test.html` and start from what it shows. Or rebuild the app from [`BUILD-PROMPT.md`](BUILD-PROMPT.md) — your `hours.csv` and `areas.txt` stay as they are.
