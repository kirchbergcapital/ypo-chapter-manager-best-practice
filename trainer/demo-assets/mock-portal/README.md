# Lakeside Chapter member portal (fictional demo)

A login-free static mock. It does not connect to a server, and it does not describe a real chapter or real people.

## Open it locally

1. Stay in the `mock-portal` folder so `style.css` loads beside the HTML files.
2. Double-click `index.html`, or open that file from a browser with File → Open.
3. Use the header links: Dashboard, Events, Members, Documents.

No install, no network, and no JavaScript. The three `.pdf` names on Documents are list items only. Those files are not in this folder.

## Demo prompts

A browser agent should answer from the pages. Expected answers:

### List the next three events with registrations

From `events.html`, soonest first:

1. Forum Breakfast — 2026-11-05 — Northbay — 18 registered / 30 capacity — Open
2. Chapter Workshop — 2026-11-18 — Pine Harbor — 22 registered / 40 capacity — Open
3. Shoreline Walk — 2026-11-29 — Elm Crossing — 11 registered / 25 capacity — Open

### Which event is closest to capacity?

Holiday Dinner — 48 registered / 50 capacity (2 seats open). It is closer than every other event on the list.

### What is the RSVP deadline for the holiday dinner?

2026-11-27

That date is on `event-holiday-dinner.html` (RSVP deadline) and on the Dashboard Deadlines list.
