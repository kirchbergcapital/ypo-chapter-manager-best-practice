Purpose: let your assistant interview you in 8 questions and write `chapter-facts.md` — the one page it reads before it answers anything about your chapter.
Time: about 30 minutes. In your first setup hour, write the five-line short version instead (about 10 minutes, part of Lab A in [`lab-build-your-assistant.md`](lab-build-your-assistant.md)) and run this full interview later as homework.
Answer from memory. Anything you do not know becomes [verify], and you fill it in later.

## Why this page matters

Your assistant knows nothing about your chapter. Without this page it guesses names, dates and budget lines.
With it, every answer starts from your facts. The page also tells a stand-in and every new officer how the chapter works.

It lives at `02-chapter-knowledge/chapter-facts.md`. A finished fictional example: [`../examples/chapter-facts.md`](../examples/chapter-facts.md).

## Step 1 — Paste this prompt into your assistant project

```
Interview me to build chapter-facts.md for my chapter.
Rules for the interview:
- Ask ONE question at a time, in the order below. Wait for my answer.
- Keep each question short. Give one example answer so I know the level of detail.
- If I say "skip" or "don't know", write [verify] in that field and move on.
- Roles before names. For officers, record role, name, role email address, term and status (confirmed, provisional or [verify]) only.
- Already have a chapter-facts.md without a Status column? Add it to the officer table, every row [verify], and ask me row by row.
  No private phone numbers, no home addresses, no family details.
- Do not invent anything. If my answer is unclear, ask once, then write [verify].

The 8 questions:
1. Chapter: the chapter's name, city or area, and roughly how many members.
2. Chapter year: when the term starts and ends, and when officers change.
3. Officers: each officer role, who holds it now, who is elect for the next term (and from when), their role email address, their term, and whether the choice is confirmed or still provisional. Provisional means the chapter has not finished the decision.
4. Standard events: the events that come back every year, with month and a one-line description.
5. Budget lines: the categories your chapter budget is split into (for example learning events, speakers, Forum, administration), who approves spending, and where the budget file lives.
6. Channels: how members hear from the chapter (email, WhatsApp, other), and the ONE channel officers use to reach me.
7. Deadlines: fixed dates in the year (commitments, elections, reports, renewals) and who owns each.
8. Templates and sources: where templates, logos, past event files and the bylaws live today.

When all 8 are done:
- Write chapter-facts.md in the template format below, filled with my answers.
- Put "Last checked: <today's date>" at the top.
- List every [verify] field at the end under "Open points", each with who could confirm it.
- If you can save files, save it to 02-chapter-knowledge/chapter-facts.md and add one line to 00-handover/log.md.
  If you cannot, show me the full text and the path, and I save it.

Template format:
{{PASTE THE TEMPLATE BELOW}}
```

Paste the template from Step 2 where it says `{{PASTE THE TEMPLATE BELOW}}`.

## Step 2 — The empty template

Copy everything between the lines into the prompt, or into a new file `02-chapter-knowledge/chapter-facts.md` if you prefer to fill it in by hand.

---

```markdown
# Chapter facts — {{CHAPTER}}

Last checked: YYYY-MM-DD · Kept by: Chapter Manager · Source of each line in brackets

## 1 · Chapter
- Name:
- City / area:
- Members (approx.):
- Chapter domain for role addresses (e.g. chapter-domain.org):

## 2 · Chapter year
- Term runs from: to:
- Officers change on:
- Chapter Manager contract scope (hours, event work separate?):

## 3 · Officers
| Role | Name | Elect (name, from, status) | Role email | Term | Status | Source |
| --- | --- | --- | --- | --- | --- | --- |
| Chapter Chair | | | chair@ | | | |
| Chair Elect | | | | | | |
| Past Chair | | | | | | |
| Learning Officer | | | | | | |
| Assistant Learning Officer | | | | | | |
| Forum Officer | | | | | | |
| Membership Officer | | | | | | |
| Other officers (e.g. finance) | | | | | | |
| Chapter Manager | | | manager@ | | | |

Status is `confirmed` when the chapter has decided, `provisional` when it has not, and `[verify]` when you do not know. Keep a provisional role provisional. *Elect* holds the person chosen for the next term, the date they start and their own status (`confirmed`, `provisional`, or `open` while the chapter has not chosen yet). The Status column is for the current holder.

## 4 · Standard events
| Month | Event | One line | Playbook file |
| --- | --- | --- | --- |
| | | | 02-chapter-knowledge/... |

## 5 · Budget
- Budget file:
- Budget lines:
- Who approves spending (and up to which amount):
- Event work paid from:

## 6 · Channels
- Members — email:
- Members — WhatsApp (groups / one-to-one):
- The ONE channel officers use to reach the Chapter Manager:
- Response target (e.g. answer or a date within 24 h):

## 7 · Deadlines
| Date | What | Owner (role) | Source |
| --- | --- | --- | --- |
| | | | |

## 8 · Templates and sources
- Templates (mail, invitations):
- Logos and design (e.g. Canva):
- Past event files:
- Bylaws and operating guidelines:

## Open points
| Field | What is missing | Who can confirm |
| --- | --- | --- |
| | | |
```

---

## Step 3 — Check it once

Read the page yourself. Correct anything wrong in the file, not in the chat.
Then ask your assistant: *"Using only chapter-facts.md, who approves a spend for the next standard event, and by when is the next deadline?"*
If the answer quotes your page, the assistant is working from your facts.

Keep it alive: when an officer changes or a date moves, update the line the same day and add a line to `00-handover/log.md`.
The monthly check in [`../04-knowledge-base/keeping-it-true.md`](../04-knowledge-base/keeping-it-true.md) catches the rest.
