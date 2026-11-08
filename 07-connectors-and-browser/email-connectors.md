# Email connectors

Purpose: connect your mailbox to your AI so it can read a mail, file it in the chapter folder and leave a reply draft in your mailbox — you send.
Time: 10 minutes for Gmail; for Microsoft 365 add one message to your tenant's admin.

**As of 21 Oct 2026.** Sources linked per row. `[verify]` = not confirmed on the provider's own page. Check once a quarter — menus move.

## Which connector fits your mailbox

Choose by your **address**, not by the app you read it in: an `@gmail.com` address read in Outlook uses the Gmail connector.

| Your mailbox | AI | Connector | What it can do | What you need | Source |
|---|---|---|---|---|---|
| Gmail / Google Workspace | Claude | Gmail, Google Calendar, Google Drive | Read mail, create drafts, reply, send. By default Claude asks before every action | Any Claude user | [support.claude.com](https://support.claude.com/en/articles/10166901) |
| Outlook on Microsoft 365 | Claude | Microsoft 365 | Read mail; with write tools draft and send (no attachments) | A **work account** — not outlook.com or hotmail — and a **one-time consent by an Entra global admin** of the tenant. All Claude plans; on Team/Enterprise the Claude owner enables it, an admin switches on write tools | [support.claude.com](https://support.claude.com/en/articles/15183774) |
| Gmail / Google Workspace | ChatGPT | Gmail app | Draft and send since June 2026 (release notes), in ChatGPT on the web | Plus, Pro, Business or Enterprise. On Business, the admin decides which write actions are allowed. Availability depends on app, plan and region — check in your account | [Release notes](https://help.openai.com/en/articles/6825453-chatgpt-release-notes) · [Admin controls](https://help.openai.com/en/articles/11509118-admin-controls-security-and-compliance-for-plugins-and-apps) · [Apps](https://help.openai.com/en/articles/11487775-connected-apps-in-chatgpt) |
| Outlook on Microsoft 365 | ChatGPT | Outlook app | Draft and send since June 2026 (release notes), in ChatGPT on the web | Same plans. On Business, the admin decides which write actions are allowed. On a work account, the Microsoft tenant may need to give consent once `[verify]` | [Release notes](https://help.openai.com/en/articles/6825453-chatgpt-release-notes) · [Admin controls](https://help.openai.com/en/articles/11509118-admin-controls-security-and-compliance-for-plugins-and-apps) · [Apps](https://help.openai.com/en/articles/11487775-connected-apps-in-chatgpt) |
| OneDrive / SharePoint | ChatGPT | SharePoint app | Connects SharePoint and work or school OneDrive | A work or school account — personal OneDrive is not supported | [help.openai.com](https://help.openai.com/en/articles/12143177-sharepoint-app-and-setup-in-chatgpt) |
| Microsoft 365 work account | Copilot | Built in | Works inside your Microsoft 365, with Enterprise Data Protection. Copilot Notebooks take a OneDrive or SharePoint folder as a source | Work account | [Microsoft Learn](https://learn.microsoft.com/en-us/copilot/microsoft-365/enterprise-data-protection) |
| Gmail on Google Workspace | Gemini | Built in | Gemini in Workspace; no training without permission. Mail features by edition `[verify]` | Workspace account | [support.google.com](https://support.google.com/a/answer/15706919) |

## Set it up (Claude, Gmail)

1. In Claude, open the connectors settings and choose Gmail (and Drive, if your chapter folder is on Google Drive) `[verify the menu name]`.
2. Log in with the **chapter's** Google account (the role account), not a private one, in the Google window that opens. Allow access.
3. Test: *"Find the latest mail from {{SENDER}}. Summarise it in three lines. Do nothing else."* Pick a sender with no Forum topics — for example the region, a venue or a speaker's office; never a Forum mail, also not as a test.
4. Then run the Level 2 prompt in [`../03-communication/email-handoff.md`](../03-communication/email-handoff.md).

## Set it up (Claude, Microsoft 365)

1. Make sure you use a **work account** on the chapter's tenant — your chapter account `manager@<chapter-domain>` ([`../05-officer-handover/role-accounts.md`](../05-officer-handover/role-accounts.md)).
2. Ask the tenant's admin for the one-time consent — with the template below.

### Asking your Microsoft 365 admin for consent

```text
Hi {{ADMIN_NAME}},
I'd like to connect Claude's Microsoft 365 connector to the chapter mailbox {{ROLE_ADDRESS}}.
I use it to read mail and to create reply drafts in that mailbox. I send every mail myself; my assistant's house rules say it drafts and never sends.
Only I use it, as the chapter's Chapter Manager, logged in with the chapter's work account.
Microsoft 365 needs a one-time consent from a global admin before the connector can be used; Anthropic's guide is here:
https://support.claude.com/en/articles/15183774
Could you approve it once, or find 10 minutes with me to do it together? Thank you!
{{YOUR_NAME}}
```

3. After the consent: connect, log in with the work account, run the same test as for Gmail.

**No tenant yet, only outlook.com?** Stay at Level 1 copy-and-paste for now — it works with any mailbox. The chapter accounts `manager@` and `chair@` the kit asks for ([`../05-officer-handover/role-accounts.md`](../05-officer-handover/role-accounts.md)) are the step that unlocks Level 2.

## Set it up (ChatGPT, Gmail or Outlook)

1. In ChatGPT, open the apps settings and connect Gmail or Outlook `[verify the menu name]`. Log in with the **chapter's** account, not a private one.
2. On a Microsoft 365 work account, if a consent screen asks for an admin, send your admin the request above, with ChatGPT in place of Claude `[verify]`.
3. Ask it to create drafts only — put the line from *Keep it at drafts* below into your `house-rules.md`.
4. Run the same test as for Gmail with Claude.

## Keep it at drafts

The connectors can send. Your house rules say *draft, never send*, and Claude asks before each action by default — answer "draft only". In ChatGPT, ask it to create drafts only.
Put this line into your `house-rules.md` as well, under *Drafts only*:

```
Mail connector: create drafts only. Never send, never reply directly, never forward. Tell me the draft is ready.
```

## Once it runs: the weekly sweep

With the connector, your assistant can read the week's mail for asks — forms, surveys, reports, trainings, deadlines — and offer rows for your incoming work list, without one paste per mail: prompt 40 *Incoming work sweep* in [`../08-prompts/prompt-library.md`](../08-prompts/prompt-library.md). The prompt tells it to read only — never move, label or archive a mail. Whether opening a mail through the connector marks it as read depends on the connector `[verify in your tool]`.

## Your check after the first week

- [ ] Every filed mail has a log line in `00-handover/log.md`.
- [ ] Drafts sit in your mailbox's draft folder, none was sent without you.
- [ ] The connector is logged in with the chapter's account, so it passes to your successor with the role.
