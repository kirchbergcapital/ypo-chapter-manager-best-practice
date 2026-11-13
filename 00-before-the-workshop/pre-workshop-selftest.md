# Pre-workshop self-test

Purpose: in about 20 minutes, get your laptop ready for the workshop — the desktop app of your AI tool works in one folder on your laptop, reads a file there and saves a file itself — and training on your data is switched off. If all five steps work, you are ready.

The workshop runs in the **desktop app** — ChatGPT or Claude, whichever you already pay for. Use the paid plan you will bring.
A paid plan is the first prerequisite — set it up before the test
(about 20 minutes, see [../01-foundations/paid-plan-and-training-off.md](../01-foundations/paid-plan-and-training-off.md); before anyone pays, the plan pick and check in [../01-foundations/business-plan-checklist.md](../01-foundations/business-plan-checklist.md)).
Menu names as of Oct 2026 — menus move `[verify]`.

## Step 1 — Desktop app installed and signed in (5–10 min)

Install the desktop app of your tool from the provider's own website and sign in with your paid plan:

| Tool | What you need | Source |
|---|---|---|
| ChatGPT | The ChatGPT desktop app for Mac or Windows; *Work* is the mode that works with files on your laptop. Work comes with paid plans except Free and Go; in Enterprise and Edu workspaces your admin switches it on | [OpenAI release notes](https://help.openai.com/en/articles/6825453-chatgpt-release-notes) |
| Claude | The Claude desktop app for Mac or Windows; *Cowork* works with a folder on your laptop, on paid plans | [Claude help](https://support.claude.com/en/articles/13345190) |

**Works if:** the app opens and you see an empty chat.

## Step 2 — Your synced drive on the laptop (5 min)

Your chapter files will live in your OneDrive or Google Drive — on the laptop through its sync app (OneDrive comes with Windows; Mac: the OneDrive app or *Google Drive for desktop*).

**Works if:** in Finder or File Explorer you see a folder called `OneDrive …` or `Google Drive` that matches your cloud storage. Two OneDrives on Windows (private and work)? Use the one of your chapter login — or your own for now.

## Step 3 — One working folder with the kit inside (3 min)

1. Inside that synced folder, create a folder `CM-Workspace`.
2. Download the kit as one file, [`_kit.zip`](https://github.com/kirchbergcapital/ypo-chapter-manager-best-practice/releases/latest/download/_kit.zip) (also the link in your pre-workshop message). Move it into `CM-Workspace` and unzip it there — Windows: right-click → *Extract All* → *Extract*; Mac: double-click. You get a folder `_kit`. Named `_kit (1)` or `_kit 2`? Rename it to `_kit`. Safari unpacked it already? Move that `_kit` folder from Downloads.
3. In `CM-Workspace`, create a small text file `selftest.txt` (Notepad on Windows; TextEdit on Mac, *Format → Make Plain Text*) with this — all fictional:

```
Lakeside Chapter (fictional) — test file
Chapter Manager: Jamie Example
Next event: Holiday Dinner, 12 December, Lakeside Boathouse
RSVP by: 20 November
```

**Works if:** you find exactly this arrangement in Finder or File Explorer:

```
OneDrive … or Google Drive/
  CM-Workspace/
    _kit/
      AI-GUIDE.md
      02-your-assistant/
    selftest.txt
```

Is `AI-GUIDE.md` one folder deeper? Then move that inner folder here and name it `_kit`. Keep using this same `CM-Workspace` in the workshop.

## Step 4 — The folder test (5 min)

Open the desktop app, start a task that works with a folder (ChatGPT: Work · Claude: Cowork `[verify the menu name]`), choose `CM-Workspace` and allow access to that folder only. With Claude, keep the app open while it works. If the app refuses your synced drive, copy the whole `CM-Workspace` (with `_kit` and `selftest.txt`) into `Documents`, choose that copy and repeat this step. Your AI says a file is empty or cannot be read? The files sit online only — right-click `CM-Workspace`: *Always keep on this device* (OneDrive) · *Available offline* (Google Drive; Windows: under *Offline access*) · *Keep Downloaded* (iCloud, also when Documents is in iCloud; older macOS: *Download Now*) — and repeat this step. Then paste:

```
Read selftest.txt in this folder. When is the RSVP deadline for the next event, and where is the event? Quote the line you used. If the file does not say, answer UNCHECKED.
```

**Works if:** the answer is *20 November* and *Lakeside Boathouse*, with the quoted lines. Then:

```
Save a new file done.txt in this folder with one line: Desktop test passed, and today's date. Then stop.
```

**Works if:** you open `CM-Workspace` in Finder or File Explorer and see `done.txt` — the assistant saved it; you did not download or copy anything. That is how the whole workshop works.

## Step 5 — Check the training setting (3 min)

Find the setting that controls whether your chats are used to train the AI model, and make sure it is **off**.
Where it is and what your plan allows: [../01-foundations/paid-plan-and-training-off.md](../01-foundations/paid-plan-and-training-off.md).

**Works if:** you have seen the setting and know whether it is off.

## Your result

| Step | ✓ | If not |
|---|---|---|
| 1 Desktop app | ☐ | Can't install (a laptop managed by IT) or Work is switched off in your workspace? Note it in the form — on the day you take the browser path: the same labs, and you save the files yourself |
| 2 Synced drive | ☐ | Note it. Today a folder on the laptop is fine; it moves into the synced drive later |
| 3 Working folder | ☐ | Compare with the arrangement above — `AI-GUIDE.md` sits directly in `_kit` |
| 4 Folder test | ☐ | It read the file but did not save `done.txt`, or there was no way to choose a folder? Note what happened — we sort it out at the helpdesk table, or you take the browser path |
| 5 Training setting | ☐ | Bring the question; it is part of the Foundation block |

Send your five ticks with your check answers (the form, or a reply to the pre-workshop message) — the trainer then plans
the first 20 minutes around them, and nobody has to report in the room.

**Your phone:** keep the same app on it — ordinary chats and drafts work there on the go. The folder task stays on the laptop.

Done? Delete `selftest.txt` and `done.txt` if you like — keep `CM-Workspace` and `_kit`; the workshop starts there. Bring your laptop and charger.
Not done? Come anyway. You'll pair up with a neighbour.

Back to [README.md](README.md) · [laptop-and-account-check.md](laptop-and-account-check.md)
