# Event lifecycle — from first idea to archive

> Events come back all year, and each one touches many people and files. One event folder, the same eight files every time, and a fixed rhythm from T-90 to T+14:
> your assistant finds every event fact in the same place, and the next organiser starts from your folder instead of from zero.

---

## 1 · The event folder

Copy `03-events/_event-template/` from your chapter folder ([`../02-your-assistant/template-folder/03-events/_event-template/`](../02-your-assistant/template-folder/03-events/_event-template/) in the kit) and rename it `YYYY-MM-DD_event-name`.

| File | What it holds |
| --- | --- |
| `brief.md` | Why, for whom, format, date, target number, who decides (by role), what success looks like — the event's one truth |
| `budget.md` | The budget line from `05-finance`, commitments, actuals — amounts only from a contract, an invoice or a receipt |
| `run-of-show.md` | Minute plan with roles, tech and plan B — after the event, the candidate for the playbook |
| `speaker.md` | Bio, briefing, what was agreed, tech and travel needs — nothing without a source |
| `venue.md` | Contract, capacity, deadlines, contact by role, deliveries, parking |
| `rsvps.md` | One table: person as on the list · status · guests · venue note the member agreed to share · source and date · attended |
| `comms-log.md` | Append-only, one line per item: date · channel · topic · open point · hours — every line ends like `· 0.5h` |
| `debrief.md` | Worked · did not work · change · numbers · hours — the source for the learnings files |

Optional: `follow-up.md` for open loops after the event, and `YYYY-MM-DD_whatsapp-summary.md` for what the chapter keeps from the event group — the chat itself stays on your phone ([`../03-communication/whatsapp.md`](../03-communication/whatsapp.md)).

## 2 · From T-90 to T+14

T = the event day. Adjust the distances to your chapter; keep the order.

| When | What | Lands in | Prompt |
| --- | --- | --- | --- |
| T-90 | Clarify the brief with the officer in charge, block the date, create the folder | `brief.md` | — |
| T-75 | Venue requests and deadlines | `venue.md`, `budget.md` | 11 Email handoff |
| T-60 | Speaker: research, request, confirm | `speaker.md` | 6 Speaker research |
| T-45 | Invitation draft, approval | `rsvps.md` (header) | Template 1 in [`../03-communication/message-templates.md`](../03-communication/message-templates.md) |
| T-30 | Run-of-show draft, budget check | `run-of-show.md`, `budget.md` | 17 Run of show · 4 Budget check |
| T-21 | Speaker briefing — your assistant drafts, you send | `speaker.md` | 15 Speaker briefing |
| T-14 … T-3 | RSVP reconciliation, weekly, then daily | `rsvps.md` | 16 RSVP reconciliation |
| T-7 | Final number to the venue | `venue.md` | — |
| T-1 | Checklist, mails to the roles involved, checkpoint | `comms-log.md`, `00-handover/handover.md` | 13 Checkpoint |
| T-0 | Attendance | `rsvps.md`, column "attended" | — |
| T+2 | Thanks, close the loops | `follow-up.md` | 1 Event follow-up |
| T+7 | Debrief with numbers and hours | `debrief.md`, `02-chapter-knowledge/learnings-{{ROLE}}.md` | 18 Debrief → learnings |
| T+14 | Reconcile invoices, move the folder to `09-archive` | `budget.md` (final) | 4 Budget check |

All prompts: [`../08-prompts/prompt-library.md`](../08-prompts/prompt-library.md) — group G · Event lifecycle (15–18), the others by number.

## 3 · Make event hours visible

Event work comes in waves, and it is easy for it to disappear into "the job". A few small habits make it visible — to you first.

| Habit | How |
| --- | --- |
| **Hours in the comms log** | Each line in `comms-log.md` ends with your hours, for example `· 0.5h`. You write them, or confirm the assistant's suggestion; only hours you confirm count |
| **Hours in the debrief** | `debrief.md` has an "Hours" block per phase — and a line for the base work you postponed meanwhile |
| **Base work stays separate** | Everyday chapter work stays in `00-handover/log.md`, without an hours column — your hours for it go into your own hours log, by area ([`../10-time-by-area/`](../10-time-by-area/)) |
| **A conversation about facts** | Your hours per event are on file. When you share a debrief with your Chair, scope and event fees become a conversation about what the work really took |
| **Your own pattern** | After three events, ask your assistant for the pattern across your own debriefs — and only your own |

No benchmark numbers here on purpose: your chapter, your events, your log. The bet: the hours come from searching and answering twice. Test it with your own week ([log](../10-time-by-area/)).

```
Read the debrief.md files of my last three events in 03-events/ and 09-archive/.
Show hours per phase for each event, side by side, and the base work I postponed.
What pattern do you see? Only from these files — no comparison with other chapters.
```

## 4 · After the event: into the knowledge base

The debrief feeds the chapter's memory: learnings into `02-chapter-knowledge/learnings-{{ROLE}}.md`, playbook changes as proposals, and the run of show as the start of next year's playbook.
How the learnings files work: [`keeping-it-true.md`](keeping-it-true.md) § 5. What a playbook holds: [`knowledge-base.md`](knowledge-base.md) § 2.

## 5 · The same facts, typed once

Before you type an event into a platform, open `02-chapter-knowledge/platform-fields.md` (prompt 30).
Each field points at the event file that already holds the value. You copy. You submit.
When the screen changes, run prompt 30 again.
A required field on the screen stays required.

*Patterns from chapter practice. Not official YPO material.*
