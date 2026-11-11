# Add-ons — extras on top of your mini CRM

Purpose: grow the mini CRM step by step, one prompt at a time, when you need it — never all at once.
How to use it: open your coding tool in the `chapter-crm` folder, start a **new** chat or task there, paste **one** prompt, say yes to file changes in the folder. After each add-on: `node self-test.js` shows `0 failed`, then make a backup.

Every add-on keeps the rules of the app: nothing is sent automatically, Forum content never, photos only with *photo OK* — and your AI tool never opens `crm.db`, `backups/`, `exports/` or `photos/`; it tests with a temporary database. Every prompt below ends with that sentence on purpose.

## A · Photo book

For a welcome evening, a new-member pack or the table plan of a retreat: one page per person or a grid, with photo, name, company and chapter role.

```text
Add a photo book to my mini CRM. In the browser: a "Photo book" page where I choose people by filter (kind, tag,
or an event's registered or attended list), a layout (grid with 6 or 12 per page, or one per page) and the fields
(name, company, title, chapter role, member since). Only people with photo_ok = 1 get their photo; the others get
a neutral placeholder with their initials. The page has a "Print or save as PDF" button with a print style
(A4, no buttons on paper). Nothing leaves the laptop. Add tests to self-test.js for the filter and the photo_ok
rule, run it until 0 failed, and show me the last line.
Never open crm.db, backups/, exports/ or photos/ - test with a temporary database only.
```

## B · Mailing drafts

For invitations, reminders and thank-you notes: personal drafts, sent by you.

```text
Add mailing drafts to my mini CRM. In the browser: a "Mailing" page where I choose recipients by filter (kind, tag,
or an event's status list), write a subject and a text with placeholders {first_name}, {last_name}, {company},
{event_name}, {event_date}, and see a preview for three recipients. Then two choices: (1) export a CSV for mail
merge (columns email, first_name, last_name, company, subject, body) into exports/, or (2) one .eml draft file per
recipient into exports/mailing-YYYY-MM-DD-HHMM/, marked as unsent (X-Unsent: 1), that I open in my mail program and
send myself. Never send anything, never connect to a mail server. Skip people without email and list them. Add
tests for the placeholders and the CSV, run self-test.js until 0 failed, and show me the last line.
Never open crm.db, backups/, exports/ or photos/ - test with a temporary database only.
```

## C · WhatsApp links

For a short reminder to the registered people of one event — one by one, from your own phone or WhatsApp on the laptop.

```text
Add WhatsApp links to my mini CRM. On an event page: a "WhatsApp reminder" box where I write one short text with
the placeholders {first_name} and {event_name}. For each chosen person with a mobile number, show a row with the
name and a link https://wa.me/<number in international format, digits only>?text=<the text, URL-encoded>. I click
each link myself and press send in WhatsApp. No automatic sending, no WhatsApp library, no bulk sending. Mark
numbers that do not start with + or 00 as "check number" instead of guessing a country code. Add tests for the
number format and the encoding, run self-test.js until 0 failed, and show me the last line.
Never open crm.db, backups/, exports/ or photos/ - test with a temporary database only.
```

Reading your WhatsApp chats is a different tool: [`../09-whatsapp-app-build-guide/`](../09-whatsapp-app-build-guide/README.md).

## D · Event check-in list

For the evening itself: a printable list, or the laptop at the door.

```text
Add a check-in list to my mini CRM. On an event page: a "Check-in" view with the registered and waitlist people,
sorted by last name, large text, one tap or click to mark "attended", and a counter "N of M arrived". A print
version (A4, a tick box per line) for events without a laptop at the door. Add tests for the counter and the
status change, run self-test.js until 0 failed, and show me the last line.
Never open crm.db, backups/, exports/ or photos/ - test with a temporary database only.
```

## Your own idea

Describe the extra in two sentences, add *"Keep the rules of this app: nothing is sent, no Forum content, photos only with photo_ok, never open crm.db, backups/, exports/ or photos/ - test with a temporary database, tests in self-test.js until 0 failed"*, and paste it. One extra at a time; back up before each.
