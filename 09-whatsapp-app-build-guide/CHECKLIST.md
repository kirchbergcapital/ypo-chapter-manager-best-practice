# Before you use it — ten ticks

Purpose: a short check of the app your AI tool built, before you use it with real chats.
Time: about 10 minutes. Ask Claude Code the questions in *italics* in the app folder; you do not need to read the code yourself.

Print it or copy it into a note and tick as you go.

- [ ] **1 · Node and Git are there.** `node --version` shows `v20` or higher; `git --version` shows a version number.
- [ ] **2 · The library version is the tested one, pinned.** Open `package.json` (any text editor) or ask *"Show me the dependencies in package.json."* — you see `"baileys": "6.7.24"`, plus exact versions for `pino` and `qrcode-terminal`, with no `^` or `~` in front. Not 6.17.x, not 7.0.0-rc.
- [ ] **3 · The tests pass.** Run `npm test` yourself in a terminal window. The summary at the end shows **`fail 0`**.
- [ ] **4 · Nothing in the code sends — two ways.** (a) In the `npm test` output from tick 3, find a passing test with **"tripwire"** in its name — it scans the code for every sending function. (b) Ask *"Show me every place in the code that sends anything to WhatsApp."* — the answer should be: none in the app's own code; only the protocol traffic the library sends by itself (delivery receipts, offline presence). If you added the [optional send step](OPTIONAL-SEND.md): exactly one place, behind your `y`.
- [ ] **5 · It stays offline on WhatsApp and stores only what it needs.** *"Is markOnlineOnConnect the literal false, is the console muted while the connection runs, and which fields does the app write to messages.jsonl?"* — yes, yes, and a short list (id, chat, time, sender, from-me, text or media marker, edit/delete) — no raw message, no media keys, no URLs.
- [ ] **6 · Your keys stay home.** The app folder is in your home folder, not in iCloud Drive, OneDrive, Google Drive or Dropbox — and `.gitignore` lists `/auth/`, `/data/`, `/exports/` and `/node_modules/`. Disk encryption (FileVault / BitLocker) is on, or the app folder is excluded from your backup. `CLAUDE.md` and `AGENTS.md` in the app folder tell the AI tool never to open `auth`, `data` or `exports`; your chapter folder holds no export.
- [ ] **7 · The QR code shows only in a terminal window.** In Claude Code, *"run npm run link"* — the app should refuse with "Run this in a terminal window". And `npm run listen` before you ever linked stops with "run npm run link first".
- [ ] **8 · The self-chat test worked.** "Message yourself" → `npm run chats` lists *Me (message yourself)* → `npm run export -- --chat "Me" --days 1` gives a readable file in `exports` → a second export gives a new file ending in `-2.md`.
- [ ] **9 · Forum chats are excluded, and only exact names export.** `never-export.txt` contains `forum`, and *"Show me the tests that prove a chat with 'Forum' in its name is refused for export and never written to ./data."* — both exist and pass. `npm run export -- --chat "e"` exports nothing and lists names instead. Add words for any other chat that must never leave your phone.
- [ ] **10 · You know the way out.** You noted the laptop's name under WhatsApp → Settings → **Linked devices**; to log out, tap it → **Log out**. On your laptop: delete the app folder by hand. `npm run unlink` prints the same steps and deletes nothing.

All ten ticked? Then go to step 6 in the [README](README.md): export one real chat and let your assistant summarise it.
Something did not tick? Paste the question and the answer into Claude Code and ask it to fix the app — then run `npm test` again.
Stuck: [`TROUBLESHOOTING.md`](TROUBLESHOOTING.md).
