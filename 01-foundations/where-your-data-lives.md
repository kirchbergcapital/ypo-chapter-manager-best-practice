# Where your data lives

Purpose: decide on one storage for all chapter work — owned by the chapter, readable by your AI, and synced to your laptop once you move to Level 2.
Time: 15 minutes to decide, one conversation with your Chair to make it official.

## The idea in one line

**One storage. The chapter owns it. You run it. Your AI reads it. Whoever steps in can continue from it.**

## Four rules

| Rule | In practice |
|---|---|
| **One storage** | Google Drive *or* OneDrive — not both, not three. Mail attachments, summaries of WhatsApp chats and downloads end up in the folder, not on the desktop |
| **The chapter owns it** | The chapter has accounts in Microsoft 365 or Google Workspace — required: at least `manager@<chapter-domain>` for you and `chair@<chapter-domain>` for your Chair. The storage belongs to `manager@`, and `chair@` can read it, so the handover works and your Chair sees the chapter folder. Chair and Chapter Manager are both admins; the Past Chair is the reserve. See [`../05-officer-handover/role-accounts.md`](../05-officer-handover/role-accounts.md) |
| **Synced to your laptop — from Level 2** | Level 1 needs no sync app: you work in the browser and upload files. From Level 2, install the storage's desktop app so the same folder lives on your laptop; Level 2 and Level 3 tools work in that local copy, the cloud keeps the chapter's copy |
| **One structure** | The ten folders from [`../02-your-assistant/folder-structure.md`](../02-your-assistant/folder-structure.md), the same in every chapter that uses this kit |

## Google world or Microsoft world?

The chapter accounts live in one of the two. Pick the world your chapter already lives in — both work.

| | Google world | Microsoft world |
|---|---|---|
| Storage | Google Drive (a shared drive owned by the chapter account is ideal) `[verify plan]` | OneDrive or a SharePoint site owned by the chapter account `[verify plan]` |
| Mail | Gmail on the chapter domain | Outlook on the chapter domain |
| AI inside the suite | Gemini Gems read files from Drive, always the current version, once Google Workspace is connected to Gemini and activity is on ([source](https://support.google.com/gemini/answer/15146780)) · Gemini in Workspace: no training without permission ([source](https://support.google.com/a/answer/15706919)) — so on the chapter accounts activity stays on; the "Keep Activity → off" switch in [paid-plan-and-training-off.md](paid-plan-and-training-off.md) is for personal Google accounts | Copilot Notebooks take up to 300 files and a SharePoint or OneDrive folder as a source; also on Microsoft 365 Personal, Family and Premium · Work accounts: Enterprise Data Protection ([source](https://learn.microsoft.com/en-us/copilot/microsoft-365/enterprise-data-protection)) |
| Claude connector | Gmail, Calendar, Drive — all users ([source](https://support.claude.com/en/articles/10166901)) | Microsoft 365 — work accounts only, one-time admin consent; on Team and Enterprise the Claude owner enables it and an admin switches on write tools ([source](https://support.claude.com/en/articles/15183774)) |

As of 21 Oct 2026. Details per connector: [`../07-connectors-and-browser/email-connectors.md`](../07-connectors-and-browser/email-connectors.md).

**Bonus:** the chapter account `manager@` is also what the Microsoft connector needs — a *work* account.
One decision solves two problems.

## Why Markdown files, not a database

Your knowledge base is a folder of short text files (`.md`). Every AI reads them well, they open on any computer,
they sync like any other file, and the next Chapter Manager needs no special software. A database would need someone to run it.

## What goes in, what stays out

| Goes in | Stays out — and where it goes instead |
|---|---|
| Bylaws, guidelines, event files, budgets, invoices, filed mails, summaries and decisions from WhatsApp chats, reports, minutes | **Forum content** → stays in the Forum. Forum is sacred. We use AI for Forum logistics only: dates, places, headcounts, costs, deadlines. Never for what is said in or around a Forum: topics, stories, notes, retreat conversations, anything shared in confidence, or any link between a name and a topic. If in doubt, leave it out. |
| Officer names, roles and role addresses; members' email, mobile number and the business details you need for invoicing; who came to which event | **Passwords, PINs, card numbers** → the chapter's password manager |
| Prospect pipeline, onboarding steps | **A copy of the member directory** → link to YPO Connect instead |
| Your learnings after each event | **Home addresses, ID or passport copies, health or family details** → not needed for the role |

## YPO Data or chapter data?

YPO's AI guidance for Chapter Managers (October 2026) draws one line that is useful to know. It is guidance, not a rule today.

| | What it is | Examples |
|---|---|---|
| **YPO Data** | What comes from YPO's systems — the guidance names Salesforce, Cvent and the Chapter Management Hub; you usually open them as YPO Connect and the Hub. Exports, copies and anything derived from them stay YPO Data | Member directory, YPO Global event lists, membership reports, exports from YPO systems |
| **Chapter data** | What your chapter collects itself, not taken or derived from YPO Data | Your own surveys and sign-ups, chapter event engagement, mails and files that did not come from a YPO system |

Chapter data is yours to work with; Forum content stays out either way. For YPO Data, YPO has proposed an AI appendix to its Operations Manual for 2027, subject to its Board's approval. If the Board approves it, connecting AI to YPO systems or sharing YPO Data with an AI tool would need YPO's approval.
Until then you can work as this kit describes — and look at the policy again when it comes. Questions: your Regional Manager or aigovernance@ypo.org.

## Already working from a private drive?

Fine for today, while your Chair sets up the chapter accounts. Build the folder structure there now. When `manager@` exists, move the whole folder across —
the structure moves with it — and give `chair@` access. Add a line to `00-handover/log.md` when you do.

## Do it now

```
I am the Chapter Manager of {{CHAPTER}}. Today my chapter files are in: {{WHERE_TODAY}}.
Our chapter uses {{GOOGLE_OR_MICROSOFT}} and has / has no own domain: {{DOMAIN_OR_NONE}}.
Give me a five-step plan to get to chapter accounts in Google Workspace or Microsoft 365 — at least manager@ for me and chair@ for my Chair —
and one storage owned by manager@, readable by chair@, synced to my laptop.
Mark every step that needs my Chair. Mark plan or price questions [verify].
```

Next: [three-levels.md](three-levels.md).
