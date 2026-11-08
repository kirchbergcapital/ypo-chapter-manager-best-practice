# Email handoff — mail in, filed, logged, drafted

Purpose: every mail worth keeping ends up in the right folder with a clear name, leaves one line in the log, and gets a reply draft you send yourself.
Time: about 20 minutes to set up the first time; after that about 5 minutes per mail at Level 1, about 2 at Level 2.

## The pattern

```
mail arrives
   → 1. folder + file name       06-communication/inbox-filed/YYYY-MM-DD_sender-role_topic.md
   → 2. one log line             00-handover/log.md
   → 3. reply draft              06-communication/drafts/ (Level 1) or your mailbox drafts (Level 2)
   → 4. YOU read, edit, send
   → 5. if it changed a fact     update 02-chapter-knowledge (chapter-facts.md, a playbook, FAQ.md)
```

Folder names and file names as in [`../02-your-assistant/folder-structure.md`](../02-your-assistant/folder-structure.md).

Why it pays off: three months later, you — or a stand-in, or a new officer — find the mail by date and role,
and the log shows what happened without opening a single inbox.

## Level 1 — copy and paste (any paid AI project)

Your assistant has the house rules: `house-rules.md` in the chapter folder or the project's files, and the core in its instructions ([`../02-your-assistant/cm-assistant-instructions.md`](../02-your-assistant/cm-assistant-instructions.md)).
Copy the mail (sender, date, subject, body) and paste it under this prompt — the same one as Lab B in
[`../02-your-assistant/lab-build-your-assistant.md`](../02-your-assistant/lab-build-your-assistant.md). If the mail asks about a rule, paste the bylaws section under the second `---`;
if it touches no rule, write `no rules needed` there.

```
New email below, followed by our rules. 1) Say which folder it belongs in and give a file name with its extension (YYYY-MM-DD_sender-role_topic.md).
2) Give me one log line for 00-handover/log.md.
3) Draft a reply in my voice; answer only from the rules below and cite the section; mark every fact without a source as [verify]. I send it myself.
---
{{PASTE_EMAIL}}
---
{{PASTE_BYLAWS_EXCERPT}}
```

Then:
1. Save the mail text under the suggested name — ending in `.md` — in `06-communication/inbox-filed/`. Attachments go next to it, same date prefix.
2. Paste the log line at the bottom of `00-handover/log.md`.
3. Copy the draft into your mail program, check every `[verify]`, send.

## Level 2 — with a mail connector

The assistant reads the mail in your mailbox and leaves the reply as a **draft in your mailbox**. You open it, edit, send.

| Your mailbox | Connector | What you need | Source (as of 21 Oct 2026) |
|---|---|---|---|
| **Gmail** (also Gmail on a chapter domain) | Claude → Gmail, Calendar, Drive | Available to all Claude users. Claude can create drafts, reply and send; by default it asks before every action | [support.claude.com](https://support.claude.com/en/articles/10166901) |
| **Outlook / Microsoft 365** | Claude → Microsoft 365 | A **work account** (not outlook.com or hotmail), and a **one-time consent by the tenant's global admin**. On Claude Team or Enterprise, the Claude owner enables the connector and an admin switches on the write tools. With write tools it can draft and send, without attachments | [support.claude.com](https://support.claude.com/en/articles/15183774) |
| **ChatGPT users** | Gmail / Outlook apps | Drafting and sending since June 2026, in ChatGPT on the web, for Plus, Pro, Business and Enterprise. On Business, the admin decides which write actions are allowed. Availability depends on app, plan and region — check in your account | [Release notes](https://help.openai.com/en/articles/6825453-chatgpt-release-notes) · [Admin controls](https://help.openai.com/en/articles/11509118-admin-controls-security-and-compliance-for-plugins-and-apps) |

**The admin consent is a one-off.** If your chapter has its own Microsoft tenant, whoever set it up is the admin — often
an IT-minded officer or the chapter's provider. One message does it; [`../05-officer-handover/role-accounts.md`](../05-officer-handover/role-accounts.md)
shows the chapter accounts `manager@` and `chair@` the kit asks for — on that tenant they are the work accounts the connector needs.

**Keep it at drafts:** the connectors could send, so answer "draft only" when the assistant asks — setup line in [`../07-connectors-and-browser/email-connectors.md`](../07-connectors-and-browser/email-connectors.md).

Prompt for Level 2 (the assistant also needs access to your chapter folder — see [`../01-foundations/three-levels.md`](../01-foundations/three-levels.md)):

```
Read the newest mail from {{SENDER_OR_SUBJECT}} in my mailbox.
1) Save its text to 06-communication/inbox-filed/ as YYYY-MM-DD_sender-role_topic.md (attachments next to it, same prefix).
2) Append one line to 00-handover/log.md: YYYY-MM-DD · topic · source file · what changed · next step.
3) Before drafting, read this thread including my sent replies in it: if I have already answered, say so and draft
   only what is still open. If you cannot see my sent mail, say UNCHECKED. Skip anything with Forum content. Create a reply DRAFT in my mailbox in my voice. Mark facts without a source [verify]. Do not send.
4) If the mail changes a fact in 02-chapter-knowledge, show me the change before you make it.
Show me the file path, the log line and the first three lines of the draft.
```

## What good looks like (fictional example)

```
File:      06-communication/inbox-filed/2026-11-12_learning-officer_speaker-confirmation.md
Log line:  2026-11-12 · events · inbox-filed/2026-11-12_learning-officer_speaker-confirmation.md · speaker confirmed for holiday dinner · send venue details by 2026-11-20
Draft:     "Thank you — wonderful news. I will send the speaker the venue details and timing by 20 November [verify date]..."
```

To practise first: the [Lab B practice pack](../02-your-assistant/lab-b-practice-pack.md) — prompt, fictional mail and rules in one block. Fictional mails: [`../examples/email-1-member-question.md`](../examples/email-1-member-question.md) · [`../examples/email-2-officer-request.md`](../examples/email-2-officer-request.md).

## Your check (30 seconds)

- [ ] File name: date, **role** (not a member's name), topic, and `.md` at the end.
- [ ] **Saved**, not only **drafted**: you can see the mail in `inbox-filed/` and the line in `log.md` (drafted = the text is still only in the chat).
- [ ] Log line at the bottom, nothing above it changed.
- [ ] Every `[verify]` in the draft checked or removed.
- [ ] Names and roles in the draft match `chapter-facts.md`, not the sender's email address.

## When it gets busy

- **Ten mails at once:** *"Here are ten mails. For each: folder, file name, log line, and 'reply needed yes/no'. Drafts only for the yes ones."*
- **A mail with a rule question:** prompt 2 in [`../08-prompts/prompt-library.md`](../08-prompts/prompt-library.md) — answer from the bylaws, with section.
- **A mail with numbers:** the assistant checks them against `05-finance` before they go into a draft.

Next: [one-channel.md](one-channel.md).
