# Canva

Purpose: let your assistant turn an event text into a first Canva design — invitation, save-the-date, social post — in the Canva account you already use as Chapter Manager.
Time: 10 minutes to connect, then a few minutes per design.

**As of 21 Oct 2026.** Sources linked; `[verify]` = not confirmed on the provider's own page.

## What you already have

Chapter Managers can use a Canva account through YPO (a limited package). Your Regional Manager knows what your package includes.
Use that account, so designs, brand colours and templates stay with the role.

## Which AI works with Canva

| AI | Canva connection | Source |
|---|---|---|
| **Claude** | Official Canva connector, available in Claude's connector directory; check which plans include it there; on Team and Enterprise the owner enables it first | [support.claude.com](https://support.claude.com/en/articles/11176164) · [claude.com/connectors/canva](https://claude.com/connectors/canva) |
| **ChatGPT** | Canva app in ChatGPT. Per Canva, available for all Canva accounts; on Canva Business and Enterprise an admin enables it first. Check whether it is available in your region | [canva.com/help](https://www.canva.com/help/connect-chatgpt-to-canva/) |

## Set it up (Claude)

1. In Claude, open the connectors and choose Canva `[verify the menu name]`.
2. Log in with the **Canva account of your CM role** in the window that opens. Allow access.
3. Test: *"List my five most recent Canva designs. Do not change anything."*

## A first design (5 minutes)

```
Read 03-events/{{EVENT_FOLDER}}/ and chapter-facts.md.
Create a Canva design for a save-the-date for {{EVENT_NAME}}: title, date, weekday, city, one line why it is worth it.
Start from my template "{{TEMPLATE_NAME}}" if it exists. Use only facts from the files; anything missing: [verify] in the design.
Give me the link to the design. Do not share or publish it.
```

Then open the design in Canva, check date and weekday, adjust, and export or share it yourself.

## Good habits

| Habit | Why |
|---|---|
| Start from the chapter's own templates | Your look stays consistent across officers and years |
| Facts from the event folder | The design says what the invitation says |
| Save the final file in `03-events/{{EVENT_FOLDER}}/` | Your successor finds it next to the event, not only in Canva |
| No member photos or names without the chapter's OK | The designs often leave the chapter — on social media or in mails |

## Without the connector

Level 1 works too: ask your assistant for the text in three lengths (headline, two lines, one paragraph) and paste it into your Canva template.
