# Examples · the Lakeside Chapter (fictional)

> **Fictional example — not a real chapter, not real rules.** Every name, address, number and date in this folder is invented.

A small, fully fictional chapter, so you can see the kit in use and test your AI setup before you add real data.
Copy the structure, replace the content with your own.

## What this is

The "Lakeside Chapter (fictional)" after a few weeks with the kit: its facts, an excerpt of its (invented) bylaws,
two incoming emails, one WhatsApp event group, a handover note and a log. Names like "Jamie Example" are obviously made up,
addresses end in `lakeside-chapter.example`, phone numbers are never shown.

## What's inside

| File | What it shows | Belongs in your folder at |
|---|---|---|
| `chapter-facts.md` | The one page your assistant reads first: roles, events, channels, deadlines. In the workshop lab, three to five lines are enough to start | `02-chapter-knowledge/` |
| `bylaws-excerpt-fictional.md` | Three invented rules (guests and partners, RSVP, requests and mailings) to practise "what do our rules say?" | `02-chapter-knowledge/` |
| `email-1-member-question.md` | A member asks a late question about an event | `06-communication/inbox-filed/` |
| `email-2-officer-request.md` | An officer asks for something urgent | `06-communication/inbox-filed/` |
| `whatsapp-export-event-group.txt` | A chat export from an event group, in WhatsApp's export format | Nowhere — exports stay outside the chapter folder; its summary goes into the event folder, e.g. `03-events/2026-10-22_wine-dinner/` |
| `handover.md` | A filled checkpoint: what is set up, decisions, open items, paths touched | `00-handover/` |
| `log.md` | Five log lines, newest at the bottom | `00-handover/` |

## How to use it with your AI

1. **Test the house rules:** load `chapter-facts.md` and `bylaws-excerpt-fictional.md`, then ask: *"Can a member bring a guest to the Wine Dinner? Cite the file and section."*
2. **Practise the email handoff** (Lab B in the workshop uses this mail):** the quickest way is the [Lab B practice pack](../02-your-assistant/lab-b-practice-pack.md) — prompt, `email-1-member-question.md` and the two bylaws sections in one block. It is the same prompt as in [`03-communication/email-handoff.md`](../03-communication/email-handoff.md). A good answer files it with a `.md` file name, writes one log line, cites Sections 4.1 and 4.2, does not promise a seat, and notices that Section 4.1 does not say whether partners pay like guests.
3. **Test the guardrails:** run the same prompt on `email-2-officer-request.md`. A good answer offers a date that fits the one-week rule, gives the budget figure only from a file (or says UNCHECKED), and drafts no bulk WhatsApp.
4. **Summarise a chat:** load the WhatsApp export and ask: *"Who is coming, who cancelled, which questions are open? Write the summary for the event file and draft 1:1 replies only."*
5. **Checkpoint:** ask your assistant to compare `handover.md` and `log.md` — is every open item in the log, and does every item say what "done" looks like?

## No folder access?

You can still practise with a whole folder. Ask your assistant:

```text
Create the Lakeside practice folder as one ZIP to download (examples + the ten empty folders).
```

Unzip it on your computer and work in it like a real chapter folder. Many paid chat tools can create a download; if yours cannot, the [practice pack](../02-your-assistant/lab-b-practice-pack.md) works in the chat alone.

## Time needed

10 minutes to read through · 20 minutes to run the five tests above.
