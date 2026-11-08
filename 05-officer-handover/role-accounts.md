# Role accounts — mail and files that belong to the chapter

**In one sentence:** the chapter's mail and files live in accounts owned by the *role* — manager@, chair@ — and in
one cloud folder owned by the *chapter*, so that every handover is a password reset instead of a treasure hunt.

**Required by this kit:** the chapter has Microsoft 365 or Google Workspace with **at least two accounts — `manager@` for the
Chapter Manager and `chair@` for the Chair.** That is what makes the handover work and lets the Chair read the chapter folder.

## Why this matters to you

- **Officers change every year, you stay.** When a Chair leaves, the mail threads with venues, speakers and sponsors
  should stay with the chapter. With chair@ they do.
- **You work for the chapter — self-employed or as its employee.** Your own mailbox, your WhatsApp number and your
  know-how are yours. Chapter work in a chapter account keeps that line clean — for you and for the chapter
  ([what-stays-yours.md](what-stays-yours.md)).
- **A stand-in or the next officer can continue,** from a working system instead of an empty inbox. That is the most generous handover there is.
- **Your Chair can read the chapter folder** with chair@ in the same workspace — no forwarded attachments, no "can you send me that again".
- **Your assistant works better** when everything it should know sits in one place the chapter owns.

## Who owns what

| Thing | Owner | Who uses it | Admins |
|---|---|---|---|
| manager@{{chapter-domain}} — **required** | The chapter | The Chapter Manager in office | Chair + CM |
| chair@{{chapter-domain}} — **required** | The chapter | The Chair in office | Chair + CM |
| events@{{chapter-domain}} *(optional)* | The chapter | Whoever runs registrations and venues | Chair + CM |
| Chapter cloud folder (Google Drive or OneDrive) | The chapter, held by manager@ — not a personal account | CM and Chair, officers as needed | Chair + CM |
| Password manager / vault for chapter logins | The chapter | CM, Chair | Chair + CM |
| Your own phone number and WhatsApp chats, your own mail, your general templates, a personal AI plan if you have one | You | You | You |

**WhatsApp stays on your own number.** Role accounts cover mail and files — there is no chapter WhatsApp number to set up.
What the chapter needs from a chat (decisions, RSVPs, promises) goes into the chapter folder as a short summary:
export the chat, let your assistant summarise it, file the summary in the event or member file
([../03-communication/whatsapp.md](../03-communication/whatsapp.md)). The chat itself stays on your phone.

**Two admins, always.** Chair and CM are both admins of the role accounts and the chapter folder. The Past Chair can be
a reserve admin for a year. If one person is unreachable, nothing is locked.

## How to get there

### The requirement: Microsoft 365 or Google Workspace, at least manager@ and chair@

The chapter has (or registers) its own domain and runs a small Google Workspace or Microsoft 365 setup on it,
with **at least two accounts: manager@ and chair@**. events@ and more only if useful. The shared chapter folder lives there too.

- Handover = the admin resets the password and the new person signs in. Mail history, folder, calendar stay.
- Your assistant can connect to one chapter mailbox and one chapter folder
  (see [../07-connectors-and-browser/email-connectors.md](../07-connectors-and-browser/email-connectors.md)).
- Plans, prices and any association or nonprofit offers change — check them on the day you set it up **[verify]**.
  Who pays is an ExCo decision.

Some chapters already have a domain or a workspace. Ask your Chair and the previous CM first — and your Regional Manager
whether there is a recommendation for chapter accounts in your region **[verify]**.

### An extra, not a replacement: forwarding addresses

Further role addresses — events@, info@ — can simply **forward** to manager@ or to the person in the role.

- The address on the website, on invitations and in YPO tools stays the same. When the person changes,
  you change the forwarding — members keep writing to the same address.
- File chapter mails into the chapter folder (`06-communication/inbox-filed/`) — the email handoff in
  [../03-communication/email-handoff.md](../03-communication/email-handoff.md) does exactly that.

Forwarding fixes an address. It keeps no history and gives no one the chapter folder — which is why manager@ and chair@ are real accounts.

### Until the accounts exist

Start today in your own Google Drive or OneDrive with the kit's folder structure, and put "chapter accounts manager@ + chair@,
then move the folder" in `00-handover/handover.md`. When manager@ exists, the whole folder moves across in one step
([../01-foundations/where-your-data-lives.md](../01-foundations/where-your-data-lives.md)).

### What we leave behind: chapter work only in a private mailbox

Chapter work that lives only in someone's private mailbox and private drive leaves with that person.
Moving it into a role account or the chapter folder is the whole point of this page.

## How to propose this to your Chair — a conversation guide

You do not need to ask for anything for yourself. You are offering the chapter a way to keep its own memory.
The Chair decides; you make the decision easy.

**1. Pick the moment.** Good moments: while next year's officers are being chosen, before the handover to a new Chair,
or at the first ExCo of the year. A 15-minute slot is enough.

**2. Open with the chapter's benefit, not your workload.**
> "Every year we lose a bit of the chapter's history when officers change. I'd like to suggest a simple way to keep it —
> it takes one decision from the ExCo."

**3. Show the picture in one sentence.**
> "Chapter mail goes to manager@ and chair@ — two accounts in Microsoft 365 or Google Workspace on a domain the chapter owns —
> and our files live in one chapter folder you can open too.
> When someone hands over, the admin resets a password — and everything is still there."

**4. Name what you will do.**
> "I can prepare the setup, the folder structure and the handover notes. From you I'd need three decisions:
> Microsoft 365 or Google Workspace, who are the two admins, and by when."

**5. Bring the one page.** Hand over the AI-use one-pager from
[../06-chapter-rules/ai-use-one-pager.md](../06-chapter-rules/ai-use-one-pager.md) — rule 4 is exactly this point, ready for the ExCo to adopt.

**6. Keep the start small.**
> "Two accounts are enough to start — manager@ and chair@. events@ and anything else can follow when we want them."

**7. Follow up in writing the same day.** Ask your assistant:

```
Draft a short follow-up email to {{CHAIR_ROLE}} after today's conversation about role accounts.
Summarise: the proposal (chapter accounts manager@ and chair@ in Microsoft 365 or Google Workspace, one chapter folder, two admins),
the three decisions we need (Microsoft 365 or Google Workspace, the two admins, the date), and what I offered to prepare.
Use only what is in 00-handover/handover.md and my notes below; mark anything else [verify]. I send it myself.
---
{{YOUR_NOTES}}
```

Then add one line to `00-handover/log.md`: date · role accounts · conversation with Chair · what was decided · next step.

## Moving the folder into manager@

Started on the bridge — the chapter folder in your own drive? Once `manager@` exists, it moves in one step (menu names as of Oct 2026 `[verify]`):

- **OneDrive:** in your own OneDrive on the web, select the chapter folder → Download (it arrives as one ZIP) → unzip it (Windows: right-click → Extract all · Mac: double-click) → sign in as `manager@` at office.com → OneDrive → Upload → Folder → pick the unzipped folder.
- **Google Drive:** in your own Drive, right-click the chapter folder → Download (one ZIP) → unzip it → sign in as `manager@` → Drive → New → Folder upload → pick the unzipped folder.
- Then: check that the ten folders are there, share the folder with `chair@`, note the new place in `00-handover/setup-progress.md`, and remove the bridge copy so there is one storage.

## When it is set up

- [ ] At least two accounts in Microsoft 365 or Google Workspace: manager@ (Chapter Manager) and chair@ (Chair)
- [ ] Role addresses listed in `02-chapter-knowledge/chapter-facts.md`
- [ ] Two admins named in `01-role-and-calendar/` (and in the ExCo minutes)
- [ ] Chapter folder owned by manager@, chair@ can open it, shared with the people who need it
- [ ] Chapter logins in the chapter's password manager, not in chats or files
- [ ] Role addresses entered wherever members and partners find the chapter (website, invitations, YPO tools where you manage them)
- [ ] Handover steps updated in [handover-checklist.md](handover-checklist.md)
- [ ] Agreed that access ends with the role: when someone leaves a role, the admins remove them the same day
