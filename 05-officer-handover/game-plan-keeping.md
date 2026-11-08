# Game plan keeping — the goals stay alive after the Game Day

**In one sentence:** the chapter commits to its goals on the Game Day; the Chair owns delivery; you keep the file
current — so the goals are still visible in March, and the next Chair finds them where they belong.

Time: 30 minutes a quarter, plus one goals handover a year.

## Who does what

| Role | Part in the game plan |
|---|---|
| **The chapter** | Commits to the goals on the Game Day |
| **The Chair** | Owns delivery of every goal |
| **Officers** | Own the goals assigned to their role |
| **The Chapter Manager** | Tracks and prepares: keeps `game-plan.md` current, drafts the status and the quarterly report |

You do not write goals *for* the chapter, and you do not reword them. When a goal has no metric, no owner or no
tracking source, the file says so and marks it `[verify]` — the Chair decides how to close the gap.

## The file

`02-chapter-knowledge/game-plan.md` is the truth file for the goals. An empty template is in
[`../02-your-assistant/template-folder/02-chapter-knowledge/game-plan.md`](../02-your-assistant/template-folder/02-chapter-knowledge/game-plan.md).

- **Header:** plan year, Game Day date, where the dataset came from, date of the last update.
- **One row per goal:** ID · Goal (action and hard deadline) · Metric, including its denominator · Tracking (which file or source shows progress) · Owner (by role) · Chair owns delivery · Status · Evidence (file and line).
- **Sources stay as they came:** the playbook PDF and the dataset go unchanged into `02-chapter-knowledge/game-plan-sources/`.
- **Standing decisions** from the Game Day go into `00-handover/decisions.md`.

A meta-goal makes the year easy to read — for example *"80 % of the goals met by fiscal year end"* (fictional example;
your chapter sets its own).

## The quarterly slot — 30 minutes

Put four dates in your calendar, one per quarter. Then:

1. **Goal status** (prompt 19) — your assistant reads `game-plan.md`, `03-events/` and `04-members-and-prospects/` and
   proposes a status per goal: met · on track · at risk · UNCHECKED, each with the evidence. You accept or change it.
2. **Quarterly report** (prompt 20) — a one-page draft for the Chair: done, on track, at risk with the reason,
   decisions needed from the ExCo, share of goals met against the meta-goal. Owners named by role.
   Save it as `07-reporting/YYYY-MM-DD_game-plan-Qn.md`.
3. **You send it** to the Chair yourself.
4. **One log line** in `00-handover/log.md`:
   `YYYY-MM-DD · game plan · Q{{n}} status · report to Chair · {{N}} at risk · next check {{DATE}}`

The prompts are in [`../08-prompts/prompt-library.md`](../08-prompts/prompt-library.md), group **H · Game plan**:
19 goal status · 20 quarterly report · 21 goals handover.

## At the handover

When the Chair changes, the goals change owner too: the new Chair now owns delivery.

- **Goals handover** (prompt 21) — per goal: status, what was tried, what is open, next date, owner by role, and which
  goals should be re-confirmed at the first ExCo. No goal dropped, none reworded.
- **`00-handover/handover.md`** carries one line: `Goals: status as of {{DATE}}`.
- **Chair change** — "Goals re-confirmed, owners updated by role" is a line in
  [handover-checklist.md](handover-checklist.md), section C. For a Chapter Manager change, section B lists the goals file.
- **New officers** get the goals their role owns in their one-page briefing
  ([officer-briefing-template.md](officer-briefing-template.md)).

## Why this sits with you

Officers change every year, and the Game Day is one day. The game plan only works if someone keeps it alive after
the Game Day — the person who is still there in the fourth quarter. Thirty minutes a quarter, and the Chair walks into
every ExCo knowing where the chapter stands.
