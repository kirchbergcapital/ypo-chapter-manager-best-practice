# Before you use it — ten ticks

Purpose: a short check of the hours app your AI tool built, before you log real hours with it.
Time: about 15 minutes. Ask your AI tool the questions in *italics* — in the chat where it built the app; you do not need to read the code yourself.

Print it or copy it into a note and tick as you go.

- [ ] **1 · Three files, nothing else.** Your hours folder holds `hours.html`, `hours-core.js` and `self-test.html` — plus your own `hours.csv` and `areas.txt`. No `package.json`, no `node_modules`, nothing to install.
- [ ] **2 · The self-test passes.** Open `self-test.html` in Chrome or Edge. The top line shows **`0 failed`**, and the page says **"Network blocked: yes"**.
- [ ] **3 · No internet, no libraries.** *"Show me every place in the three files that loads something from the internet or sends something anywhere — and the Content-Security-Policy line in both HTML files."* — the answer: no libraries, nothing loaded or sent from `hours.html` or `hours-core.js`; the only network line is the one blocked test call in `self-test.html` (the page says "Network blocked: yes"); and a line with `connect-src 'none'` in both HTML files.
- [ ] **4 · Text stays text.** *"Do the files use innerHTML, eval, new Function or onclick attributes anywhere?"* — no, none of them.
- [ ] **5 · Your folder, not the chapter's.** In `hours.html`, **Pick my hours folder** → your `my-work/hours` folder works. Try your chapter folder once: the app refuses it ("This looks like your chapter folder").
- [ ] **6 · One timer run.** Start one area, stop it — under the task field the grey hint *"Roles, not names. Forum: logistics only - never a topic or a name."* — change the minutes, save. Open `hours.csv` in Notepad or TextEdit: one new row at the bottom, `source` timer, `status` confirmed, all older lines unchanged.
- [ ] **7 · One import.** Paste one `suggested` and one `confirmed` hours line (fictional ones from your AI tool): the suggested one shows "to confirm", the confirmed one is ticked. Import, then paste the confirmed line again — it is flagged "already in your log" and not imported twice.
- [ ] **8 · A change is a new row.** Use **Correct** on one entry and change its minutes. `hours.csv` gets a new `correction` row at the bottom; the original row is still there, unchanged, and the week view shows the entry once, with its new minutes. **Delete** it: one more `correction` row, and the entry shows as deleted — a second **Delete** is not offered.
- [ ] **9 · The report shares only what you choose.** Open the month report: task texts are **off**; totals by area and by event are there; print preview shows no buttons; **Download report CSV** gives `hours-report-YYYY-MM.csv`.
- [ ] **10 · Comms logs are read, never written.** Optional, if you keep event hours in comms logs: **Read event hours from my chapter folder** shows them per event as "from comms logs", not inside your totals. Afterwards, the comms-log files in the chapter folder still show their old "modified" date.

All ten ticked? Then use the app for a week alongside the hours line from your assistant ([README](README.md), steps 4–6).
Something did not tick? Paste the question and the answer into your AI tool and ask it to fix the app — then open `self-test.html` again.
Stuck: [`TROUBLESHOOTING.md`](TROUBLESHOOTING.md).
