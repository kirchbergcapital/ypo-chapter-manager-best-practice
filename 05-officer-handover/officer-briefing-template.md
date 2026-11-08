# Officer briefing — one page from the CM to every new officer

New officers arrive motivated and with little time. One page from you on their first day saves both of you
weeks of back-and-forth: what the role covers, which deadlines matter, how to reach you, and where things live.

Use the template as it is, or let your assistant fill it from the folder (prompt below). Keep it to one page.

---

## Template

```markdown
# Welcome, {{OFFICER_ROLE}} — {{CHAPTER}}, FY {{YEAR}}

Prepared by {{YOUR_NAME}}, Chapter Manager · {{DATE}}

## Your role in one line
{{ONE_LINE_PURPOSE}}

## Your year at a glance
| When | What | Commitment / deadline |
|---|---|---|
| {{MONTH}} | {{TASK}} | {{DEADLINE_OR_DASH}} |
| {{MONTH}} | {{TASK}} | {{DEADLINE_OR_DASH}} |
| {{MONTH}} | {{TASK}} | {{DEADLINE_OR_DASH}} |

## Your goals this year
From our game plan ({{LINK_TO_GAME_PLAN_FILE}}) — the goals this role owns:
| ID | Goal | Metric | Status |
|---|---|---|---|
| {{GOAL_ID}} | {{GOAL}} | {{METRIC_WITH_DENOMINATOR}} | {{STATUS}} |

## How we work together
- **One channel:** requests to me go via {{CHANNEL}} (for example: email to manager@{{chapter-domain}}, or via the Chair).
  I keep a prioritised list and tell you where your request sits.
- **Lead time:** updates and material for an event or the ExCo one week before the date.
- **Response:** I answer within 24 hours or give you a date. I'm grateful for the same when I need a decision from you.
- **Fixed dates:** ExCo dates and deadlines are in our chapter calendar ({{CALENDAR_LINK}}) and stay put.

## Where things live
- Chapter folder: {{FOLDER_LINK}} — start with `00-handover/` and `02-chapter-knowledge/`
- Your role address: {{ROLE_ADDRESS_OR_DASH}}
- Logins: in the chapter password manager — {{ADMIN_NAME_OR_ROLE}} adds you

## What your predecessor handed over
- {{OPEN_ITEM_1}} — owner, date, what "done" looks like
- {{OPEN_ITEM_2}}

## AI in our chapter
We use AI for drafts, summaries and checklists. Our five simple rules are on one page: {{LINK_TO_AI_ONE_PAGER}}.
The short version (the Forum rule in full: [START-HERE.md](../START-HERE.md)): Forum logistics yes, Forum content never; paid AI plans only, training off; a human sends; our own files are the truth.

## Your first 30 days
1. Handover call with {{PREDECESSOR_ROLE}} and me — {{DATE}}
2. Officer training — {{TRAINING_DATE_OR_HOW_TO_BOOK}}
3. {{FIRST_CONCRETE_TASK}}

Questions? {{CHANNEL}} — I'm glad you're on board.
```

---

## Which deadlines go into "Your year at a glance"

Take them from your commitments calendar (`01-role-and-calendar/commitments-calendar.md`, template:
[commitments-calendar.md](commitments-calendar.md)), which you fill from the official source in the Chapter Management Hub
or from your Regional Manager. Pick the deadlines this role owns — your bylaws and your Chair decide how they are split
between officers. Add the role's own fixed dates (events, ExCo meetings) from `03-events/` and the chapter calendar.

## Which goals go into "Your goals this year"

The goals with this role as owner in `02-chapter-knowledge/game-plan.md` — how that file is kept, and the prompts for
goal status and the goals handover (group "Game plan" in [../08-prompts/prompt-library.md](../08-prompts/prompt-library.md)):
[game-plan-keeping.md](game-plan-keeping.md). If the role owns no goal, delete the section.

---

## Prompt: let your assistant write the briefing

```
Write the one-page officer briefing for the incoming {{OFFICER_ROLE}}, using the template in
05-officer-handover/officer-briefing-template.md.

Read first: 00-handover/handover.md, 00-handover/log.md, 01-role-and-calendar/ (officer list, the one channel,
commitments calendar), 02-chapter-knowledge/chapter-facts.md, 02-chapter-knowledge/game-plan.md and 03-events/.

Rules:
- Facts only from these files. Name the file for each deadline. Anything you cannot find: [verify].
- Goals: copy the goals this role owns from game-plan.md word for word, with metric and status. Do not reword a goal.
- Names and roles only from the officer list — never from an email address.
- Keep it to one page. Plain, warm, short. Language: {{LANGUAGE}}.
- Draft only — I review and send it myself.

At the end, list separately: what you could not check, and which open items have no owner yet.
```

After you send it, add one line to `00-handover/log.md`:
`YYYY-MM-DD · officer briefing · {{OFFICER_ROLE}} · sent by CM · next step: handover call on {{DATE}}`
