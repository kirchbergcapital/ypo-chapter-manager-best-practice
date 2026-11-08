# Message templates

Purpose: five short patterns for the messages a Chapter Manager writes again and again. Your assistant fills the placeholders from your files; you read and send.
Copy the ones you use into `06-communication/templates/` and adapt them to your chapter's voice.

## How to use them with your assistant

```
Use the template "{{TEMPLATE_NAME}}" from 06-communication/templates/.
Fill the placeholders from {{EVENT_FOLDER_OR_FILE}} and chapter-facts.md. Names and roles only from chapter-facts.md.
Anything you cannot find: [verify]. Write it in {{LANGUAGE}}. Mail version and a short WhatsApp version. I send it.
```

The WhatsApp version is for a one-to-one chat or a group post you send yourself, from your own number.

---

## 1 · Event invitation

```text
Subject: {{EVENT_NAME}} — {{DATE}}, {{CITY}}

Dear {{FIRST_NAME}},

You are warmly invited to {{EVENT_NAME}} on {{WEEKDAY}}, {{DATE}}, {{START}}–{{END}}, at {{VENUE}}.
{{ONE_SENTENCE_WHY_IT_IS_WORTH_IT}}

Spouses / partners: {{YES_NO_PER_EVENT_RULE}}
Cost: {{COST_OR_"included"}}
Please register by {{DEADLINE}}: {{REGISTRATION_LINK}}

Looking forward to seeing you,
{{YOUR_NAME}}, Chapter Manager, {{CHAPTER}}
```
WhatsApp version: *"{{EVENT_NAME}}, {{WEEKDAY}} {{DATE}}, {{VENUE}}. {{ONE_LINE_HOOK}} Register by {{DEADLINE}}: {{LINK}}"*

## 2 · Reminder

```text
Subject: Reminder: {{EVENT_NAME}} — {{DATE}}

Dear {{FIRST_NAME}},

A quick reminder: {{EVENT_NAME}} is {{IN_X_DAYS / next WEEKDAY}}.
{{START}} at {{VENUE}}, {{ADDRESS}}. {{PARKING_OR_DRESS_CODE_IF_RELEVANT}}

{{IF_REGISTERED: "See you there!" / IF_NOT: "There are still a few places — register here: {{LINK}}"}}

{{YOUR_NAME}}
```
WhatsApp version: *"Reminder: {{EVENT_NAME}} {{WEEKDAY}} at {{START}}, {{VENUE}}. See you there!"*

## 3 · Follow-up after no reply

```text
Subject: {{EVENT_NAME}} — will you join us?

Dear {{FIRST_NAME}},

I'm finalising numbers for {{EVENT_NAME}} on {{DATE}}. Could you let me know by {{DATE}} whether you will join?
A simple yes or no is perfect.

Thank you,
{{YOUR_NAME}}
```
WhatsApp version: *"Hi {{FIRST_NAME}}, quick one: are you joining {{EVENT_NAME}} on {{DATE}}? A yes or no helps me plan. Thank you!"*

## 4 · Welcome, new member

```text
Subject: Welcome to {{CHAPTER}}, {{FIRST_NAME}}

Dear {{FIRST_NAME}},

Welcome to {{CHAPTER}} — we are delighted you are here.
I am {{YOUR_NAME}}, the Chapter Manager. I am your first contact for events, registrations and practical questions.

Three things for your first weeks:
1. Our next event: {{NEXT_EVENT}} on {{DATE}} — {{LINK}}
2. Your Forum: {{FORUM_OFFICER_ROLE}} will be in touch about Forum placement and training.
3. Your mentor: {{MENTOR_IF_THE_CHAPTER_ASSIGNS_ONE / "you will hear from us soon"}}

The fastest way to reach me: {{CHANNEL}}.
Warm regards,
{{YOUR_NAME}}
```
Prompt 5 in [`../08-prompts/prompt-library.md`](../08-prompts/prompt-library.md) fills this from your onboarding file.

## 5 · Request to officers for input

```text
Subject: Input needed by {{DEADLINE}}: {{TOPIC}}

Dear {{OFFICER_ROLES}},

For {{ExCo MEETING / REPORT / EVENT}} on {{DATE}} I need from you:

| Who (role) | What | By |
|---|---|---|
| {{ROLE}} | {{ITEM}} | {{DATE}} |
| {{ROLE}} | {{ITEM}} | {{DATE}} |

One week ahead gives everyone time to read before we meet — thank you.
If something is unclear, reply to this mail and I will sort it out.

{{YOUR_NAME}}
```
This follows the one-week lead time in [`../06-chapter-rules/operating-guardrails.md`](../06-chapter-rules/operating-guardrails.md).

---

## Your check before sending

- [ ] Date, weekday and time match the event folder.
- [ ] Every `{{PLACEHOLDER}}` and `[verify]` is gone.
- [ ] Names and roles come from `chapter-facts.md`.
- [ ] Sent by you, one message at a time or to the group you chose.
