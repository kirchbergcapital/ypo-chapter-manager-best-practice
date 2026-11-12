# Checklist — your mini CRM, before real names go in

Purpose: a short check of the app your AI tool built, before you put real people in.
Time: about 15 minutes. Ask your AI tool the questions in *italics* — in the chat where it built the app; you do not need to read the code yourself.

- [ ] **1 · Self-test.** `node self-test.js` ends with `0 failed`. *"Run the self-test and show me the last line."*
- [ ] **2 · No packages.** *"Did you install any package? List every file you created."* — the answer: no packages, and no folder `node_modules`.
- [ ] **3 · Only your laptop.** *"Which address does the server listen on?"* — the answer is `127.0.0.1` or `localhost`. Never `0.0.0.0`.
- [ ] **4 · The token.** Copy the address from your browser, delete everything from `?t=` to the end, paste it into a new tab: the list stays empty or shows an error. With the full address it works.
- [ ] **5 · Sends nothing.** *"Is there any code that sends an email, a WhatsApp message or a request to the internet?"* — the answer is no.
- [ ] **6 · Import with preview.** Import `sample-people.csv`: you see a preview and the counts (new, updated, skipped) before anything is saved.
- [ ] **7 · Excel-safe export.** Add a fictional person with the first name `=1+1`, export the list, open it in Excel: `=1+1` stays text (a leading `'` is fine), accents look right, and each value has its own column.
- [ ] **8 · Photo only with the tick.** Add a photo to a fictional person, untick *photo OK*: the photo disappears from the list.
- [ ] **9 · Backup.** *Backup now* creates a file you can find in `backups/`. Copy that file and `photos/` into your chapter storage the same day.
- [ ] **10 · The folder is not synced.** `chapter-crm` is not inside iCloud Drive, OneDrive, Google Drive or Dropbox.

All ten ticked? Delete the fictional people and the *Holiday Dinner*, then add your real list.
Something did not tick? Paste the point and what you saw into your AI tool and ask it to fix the app — then run the self-test again.
