Purpose: one folder structure for the whole chapter, so you, your assistant, a stand-in and every new officer always know where a thing lives.
Copy [`template-folder/`](template-folder/) into the chapter's cloud storage. That is the whole setup. Already have a structure that works? Keep it — see [*Already have a folder structure that works?*](#already-have-a-folder-structure-that-works) below.

## The idea in one line

**The folder belongs to the chapter, not to you.** You run it. Your assistant keeps it true. A stand-in or the next officer can continue from it.
What stays yours — your know-how, your own templates and method, your own WhatsApp number and chats — is set out in [`../05-officer-handover/what-stays-yours.md`](../05-officer-handover/what-stays-yours.md).
Your hours log lives outside the chapter folder, in your own folder — see [`../10-time-by-area/`](../10-time-by-area/).

## Where it lives and who owns it

| Point | How |
| --- | --- |
| One storage | One cloud storage for all chapter work — Google Drive or OneDrive. Not three. See [`../01-foundations/where-your-data-lives.md`](../01-foundations/where-your-data-lives.md) |
| Owner | An account that belongs to the **role**, in the chapter's Microsoft 365 or Google Workspace — required: at least `manager@<chapter-domain>` and `chair@<chapter-domain>`. The folder belongs to `manager@` and `chair@` can open it, so it passes on with the role. See [`../05-officer-handover/role-accounts.md`](../05-officer-handover/role-accounts.md) |
| Two admins | The Chapter Chair and the Chapter Manager both have full rights. The Past Chair is the reserve. Nobody is the only key |
| On your laptop | Level 1 needs no sync app — you upload files to your AI project. From Level 2 on, install the storage's desktop sync app, so the same folder is also on your laptop; Level 2 and Level 3 tools work in that local copy — see [`../01-foundations/three-levels.md`](../01-foundations/three-levels.md) |
| Sharing | Share sub-folders with officers when they need them (for example `03-events` with the Learning Officer). Keep `05-finance` to the Chair, the finance officer and you |

**Project files are copies.** Files you upload to a ChatGPT or Claude project do not follow changes in your folder — after a change you upload again. Keep the project small (`house-rules.md`, `chapter-facts.md`, the bylaws). Where the desktop app has access to your folder, do the daily work there — nothing to upload. Without folder access, upload a changed file again the same day and ask the assistant which version it has.

Every prompt in this kit works the same with OneDrive: where a prompt says "Drive", read your cloud storage — Google Drive or OneDrive.

No chapter accounts yet? Ask your Chair for `manager@` and `chair@`, and meanwhile start in your own Drive or OneDrive — the structure moves into `manager@` in one step once it exists.

## The tree

```text
{{CHAPTER}}-chapter/
├── house-rules.md             the full house rules — your assistant reads them first
├── AGENTS.md · CLAUDE.md      two short pointers to house-rules.md, for Codex and Claude Code
├── 00-handover/               handover.md · log.md · decisions.md
├── 01-role-and-calendar/      your role, the chapter year, deadlines · incoming-work.md
├── 02-chapter-knowledge/      chapter-facts.md · game-plan.md · bylaws · guidelines · FAQ.md · event playbooks · learnings · platform-fields.md
├── 03-events/                 one folder per event: YYYY-MM-DD_event-name
│   └── _event-template/       copy it for each new event
├── 04-members-and-prospects/  pipeline.md · onboarding, attendance
├── 05-finance/                budget, invoices, receipts list
├── 06-communication/
│   ├── inbox-filed/           emails worth keeping
│   ├── drafts/                drafts waiting for you
│   ├── templates/             mail and message patterns
│   └── whatsapp/              summaries that belong to no event
├── 07-reporting/              ExCo reports and exports, unchanged
├── 08-prompts/                prompts that work
└── 09-archive/                closed years, finished events
```

## Each folder: what goes in, what stays out

| Folder | What goes in | What does NOT go in |
| --- | --- | --- |
| `00-handover` | `handover.md` (current state, open items), `log.md` (one line per change, append-only), `decisions.md` (one line per decision) | Long notes and drafts — they go in the topic folder; the log points to them |
| `01-role-and-calendar` | Your role description and contract scope, the chapter year, commitment deadlines (see [`../05-officer-handover/commitments-calendar.md`](../05-officer-handover/commitments-calendar.md)) · `incoming-work.md` | Personal calendar entries; private contract details you would not hand over |
| `02-chapter-knowledge` | `chapter-facts.md`, `game-plan.md` (the chapter's goals, sources unchanged in `game-plan-sources/`), bylaws, operating guidelines, `FAQ.md`, one playbook per standard event, one learnings file per role · `platform-fields.md`. See [`../04-knowledge-base/knowledge-base.md`](../04-knowledge-base/knowledge-base.md) | Drafts and one-off emails — knowledge here is what is true and reusable |
| `03-events` | One folder per event, copied from `_event-template/`: `brief.md`, `budget.md`, `run-of-show.md`, `speaker.md`, `venue.md`, `rsvps.md`, `comms-log.md`, `debrief.md`. The steps from first idea to archive: [`../04-knowledge-base/event-lifecycle.md`](../04-knowledge-base/event-lifecycle.md) | Member private data beyond name and attendance; Forum content (rule below) |
| `04-members-and-prospects` | Prospect pipeline, onboarding steps, who came to which event, mentor matches the chapter allows — the member data your role needs · `pipeline.md` | A copy of the member directory (link to YPO Connect instead); private details: home addresses, private phone numbers, ID or passport copies, health or family details |
| `05-finance` | Budget file, invoices, receipts list (CSV), sponsor agreements | Bank logins, card numbers, PINs — they belong in the chapter's password manager |
| `06-communication` | Filed emails (`inbox-filed`), drafts (`drafts`), patterns (`templates`), WhatsApp summaries that belong to no event, e.g. open conversations at a handover (`whatsapp`) — an event's summary goes into its event folder. See [`../03-communication/email-handoff.md`](../03-communication/email-handoff.md) and [`../03-communication/whatsapp.md`](../03-communication/whatsapp.md) | Bulk lists for mass messages; WhatsApp exports — they stay on your phone or outside the chapter folder; nothing from Forum groups or any chat with Forum content |
| `07-reporting` | ExCo reports, exports from YPO tools, saved unchanged in a dated file | Edited exports — keep the original, put your analysis next to it |
| `08-prompts` | Prompts that already work for you. Start from [`../08-prompts/prompt-library.md`](../08-prompts/prompt-library.md) | Prompts with real member names or numbers inside — use `{{PLACEHOLDERS}}` |
| `09-archive` | Closed years (`FY25-26/`) and finished events, moved here whole | Nothing gets deleted to get here — move, never delete |

Two things never go anywhere in the folder: **passwords** and **Forum content**.
Passwords have a better place: the chapter's password manager. For Forum, one rule:

> Forum is sacred. We use AI for Forum logistics only: dates, places, headcounts, costs, deadlines. Never for what is said in or around a Forum: topics, stories, notes, retreat conversations, anything shared in confidence, or any link between a name and a topic. If in doubt, leave it out.

Forum logistics belong in the folder like any other logistics: Forum dates, training registrations, retreat travel and costs.
Forum content stays in the Forum: a retreat agenda with topics or exercises, a moderator's mail about a topic, parking-lot sheets, flipcharts, notes and minutes.

## File names

`YYYY-MM-DD_topic.md` — date first, lower case, hyphens, no spaces, and **always with the extension**: `.md` for text, `.csv` for tables, the original's own for PDFs and photos.

| Kind | Example |
| --- | --- |
| Note or document | `2026-11-12_venue-options.md` |
| Filed email | `2026-11-12_learning-officer_speaker-confirmation.md` (`date_sender-role_topic.md`) |
| Event folder | `2026-12-04_holiday-dinner/` |
| Export | `2026-10-01_commitments-status-export.pdf` |
| WhatsApp summary (in the event folder) | `2026-11-14_whatsapp-summary.md` |

Roles in file names, not member names. The date sorts the folder for you. Living files keep a plain name: `chapter-facts.md`, `FAQ.md`, `handover.md`, `log.md`, `decisions.md`.

## Let your assistant set it up

At Level 2 or 3 (your assistant can write files):

```
Read 02-your-assistant/folder-structure.md.
Create this folder structure in the folder we are working in, with a one-line README.md in each folder.
Create 00-handover/handover.md, log.md and decisions.md from 02-your-assistant/template-folder/00-handover/.
Add one line to 00-handover/log.md: today's date · setup · folder-structure.md · structure created · fill chapter-facts.md.
Show me the tree when you are done.
```

At Level 1 (chat project only): copy `template-folder/` into your cloud storage by hand. It takes two minutes.

## Already have a folder structure that works?

Keep it. Copying the template next to it would give you two places for the same thing. Your assistant writes one small map instead:

```
Read 02-your-assistant/folder-structure.md, then look at the folder names in my existing chapter folder -
names only, not the files inside. Skip any Forum folder entirely, and leave out any folder named after a member.
1) Map each of the ten kit folders to the folder of mine that holds that kind of file, as a table:
   kit folder | my folder | note. Where nothing fits, write "new" and suggest a name in the style of my folders.
   Ask me where my handover note, log and decision list live, and anything else the names do not show; put my answers
   in the table - none yet: "new 00-handover" with handover.md, log.md and decisions.md.
2) Create nothing and move nothing yet. Show me the table with everything you would add.
After my yes: save it as folder-map.md at the top of my chapter folder; put house-rules.md, AGENTS.md and CLAUDE.md
from 02-your-assistant/template-folder/ next to it, with {{YOUR_NAME}}, {{CHAPTER}} and {{YEAR}} replaced;
create only what the table marks "new";
add one line to 00-handover/log.md.
```

From then on `folder-map.md` tells your assistant where the kit's paths live in your folder: a prompt that says `01-role-and-calendar/incoming-work.md` means the folder the map names. Nothing of yours is copied, moved or renamed for the kit. For a stand-in, the map is also the quickest guide to your folder. Two chapters: one folder, one map each.
At Level 1, type your top-level folder names into the chat (or attach a screenshot of them, Forum folders left out), ask for the table, save `folder-map.md` yourself and add it to your project files next to `house-rules.md`.
