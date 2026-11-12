# Changelog

Purpose: what changed between versions of this kit, and what is planned next.

> Community resource by a YPO member, not an official YPO resource.
> **Maintainer:** see [`README.md`](README.md) · **last checked:** 10 Nov 2026 · menus move — every tool page carries an as-of date.

## v0.3 — November 2026

- **AI use in our chapter — one clear document:** Part B is now the chapter's **tool list** — only the tools on it are used for chapter work and chapter data; anything new (an app, a plugin, a custom GPT, a connector, a self-built app) goes on the list first, with the Chair's OK. Forum short form: chapter matters, a conduct case too, are chapter business.
- **Your own mini CRM:** module [`12-mini-crm`](12-mini-crm/) — a build guide for a small contact and event list in one SQLite file on your laptop, no packages, only on your own computer; add-ons for a photo book, mailing drafts, WhatsApp links and a check-in list. AI guide: optional Station 13. A wish from the Chapter Managers in Edinburgh.
- **YPO Data or chapter data?** in [`where-your-data-lives.md`](01-foundations/where-your-data-lives.md#ypo-data-or-chapter-data): data from YPO's systems versus what your chapter collects itself, after YPO's AI guidance (October 2026). Guidance, not a rule.
- **Five settings worth checking** in [`business-plan-checklist.md`](01-foundations/business-plan-checklist.md), starting with two-factor sign-in.
- **Meetings: record them** — knowledge base § 8: YPO's Zoom, announced at the start, never a Forum meeting.
- Member data the role needs now names email, mobile number and business details for invoicing.
- Lab B: one of your own chapter emails can replace the practice email.

## v0.2 — 22 Oct 2026 (draft)

- Public release (Nov 2026): one file, [`_kit.zip`](https://github.com/kirchbergcapital/ypo-chapter-manager-best-practice/releases/latest/download/_kit.zip), always the latest; it unzips as `_kit`. Update: README.
- From the first pilots (26 Oct 2026): prompt 40 *Incoming work sweep* over mail and chosen chats (40 prompts in all); `incoming-work.md` gets *Source* and *Last sweep*; prompts 27 and 28 say when they are worth it; a folder that already works gets `folder-map.md` instead of a copy; the AI guide: a link that fails is not a missing file.
- From the second pilot (26 Oct 2026): an *Elect* column in the officer table; budget lines explained; Claude Code first start and a Mac PATH fix; no hours line for setup steps; the thread checked before a reply draft; areas from an existing job description; project files are copies; connector test never with a Forum mail.
- Chapter moments: module [`11-chapter-moments`](11-chapter-moments/) — complaints, sad news and event emergencies, renewals, Gold or leaving, elections, the year review, a merger. Each page: who decides, what is yours, first steps. Prompts 32–39; they answer in the chat first and change a file only after your yes.
- Situations: [`SITUATIONS.md`](SITUATIONS.md) starts from what is on your desk and names the file and prompt for each situation.
- Presentation for trainers in [`trainer/presentation/`](trainer/presentation/README.md): workshop deck (PDF + PPTX, 21 slides), sketchnote series (12 images) and the 2:58 sketchnote video; speaker notes left out.
- New module [`10-time-by-area`](10-time-by-area/): where your hours go, by area of work. Your assistant offers one hours line per finished task; only confirmed hours count. The log lives in your own folder; you share the month report. Optional: build prompt for your own hours app (no install).
- House rules: rule 19 now reads "You may suggest minutes for a finished task, marked suggested; only hours I confirm count; never fill in hours I did not confirm"; new rule 20 *Hours line*.
- Prompt library: new group I · Time by area with prompts 23 Areas interview, 24 Hours line round-up, 25 Month report by area and 26 Workload assessment; new 27 Request check (group E) and 28 Procedure change summary (group C).
- Less typing twice, clearer handovers: prompts 29 *Incoming work list*, 30 *Platform field map* and 31 *Membership pipeline step* (initials only); process playbooks in the knowledge base; officers marked `provisional` or `confirmed` in chapter facts, kept so by prompts 9 and 27; prompt 28 offers a playbook where none exists; long forms filled from the field map.
- Time by area: optional task starts "for region:" and "for global:" show who asked for the work (house rule 20); new section *When someone asks about your workload*.
- AI guide: optional Station 12 — time by area; the hours line can start any day after Station 3. Stations 1–11 keep their numbers; Station 2 may start on your own drive (the bridge), each check now says saved or drafted, and the clock times are optional.
- "Test it with your own week — your log will tell you" now points to the module as the measuring tool; the event comms log keeps its hours as before (you write them, or confirm the assistant's suggestion).
- House rules as a file: `house-rules.md` at the top of the chapter folder (rules 1–20 unchanged), with `AGENTS.md`/`CLAUDE.md` pointers. Instructions fields get a short core (about 1,000 characters), so it fits every tool.
- Desktop apps first: ChatGPT Work and Claude Cowork work in a folder on your laptop and save every file themselves — the easiest way, now named first in Way 1. Memory: leave the tool's default; in ChatGPT, project-only memory switches off Work.
- Workshop in the desktop app: format, labs, demos and the pre-workshop check run in the ChatGPT or Claude desktop app with one folder (`CM-Workspace`, the kit in `_kit`); the assistant saves every file itself; every lab has a *Browser path*.
- Chat files: a small starter (`KIT-START.txt`, about 100 KB) and seven more files by station (`KIT-2-…` to `KIT-8-…`); your AI asks for the one a step needs. Attach the file; don't paste its text.
- From early use: one-message practice pack for Lab B, file names with extension, 'drafted' vs 'saved' in every check, bridge first, success checklist after each lab.

## v0.1 — October 2026 (draft)

- First draft, built as the companion to the Chapter Manager workshop format.
- One fixed workshop format for both workshops, built around three questions: **reach** your members, **know** your chapter, **persist** through officer changes.
- Ten modules (`00`–`09`), a trainer folder, a glossary and the fictional "Lakeside Chapter" in `examples/`.
- Drafted with several AI agents in separate roles (content, hands-on lab, governance, demos, audience) and consolidated by the author.
  Tool facts are stated as of October 2026; anything marked `[verify]` still needs a check.

### v0.1 corrections (21 Oct 2026)

- Paid plans only; Chapter Managers work for their chapter, self-employed or employed ([`what-stays-yours.md`](05-officer-handover/what-stays-yours.md)); WhatsApp on your own number; Chapter Commitments copied from CMH; tool facts re-checked; wording softened.

### v0.1 round 2 (21 Oct 2026)

- Forum: one rule, quoted word for word wherever the kit states it in full; short forms point to it — AI for Forum logistics only (dates, places, headcounts, costs, deadlines), never for Forum content; a name next to a topic is content.
- Game plan: a page on keeping the chapter's goals alive through the year (`05-officer-handover/game-plan-keeping.md`), a goals line in the Chapter Manager and Chair handovers and in the officer briefing, and a "Game plan" group of prompts.
- Events: an event template folder, an event lifecycle page and a group of event prompts.
- A weekly officer note as a prompt; a half-page charter for WhatsApp groups.
- "Measure one workflow first" in `START-HERE.md`: time one task before and after four weeks.
- Handover: unfinished risks and open promises as their own line; the handover meeting at least two weeks before the term ends, recorded or with notes.
- Wording: "a stand-in or the next officer can continue" instead of "the next Chapter Manager inherits"; "without more hours" is now a bet you test with your own log, not a promise.
- Before the workshop: two questions for the week before; your plan and self-test status is collected with the check, not asked in the room.
- README: "Further viewing" and "Contributions from Chapter Managers".

### v0.1 round 3 (21 Oct 2026)

- Format name: the workshop is now called **Operational AI Excellence for Chapter Managers**. The idea behind it stays: chairs and officers rotate every year; the Chapter Manager stays.
- WhatsApp: the bundled helper code is replaced by a build guide ([`09-whatsapp-app-build-guide`](09-whatsapp-app-build-guide/)). With your AI tool you build your own small app that reads your chats, summarises them and drafts replies; sending is optional and needs your OK for every single message.
- License: no program code in the repository any more — everything, including the prompts in the build guide, is CC BY 4.0.
- Trainer material and module pages are generic for every trainer; author background lines removed.

### v0.1 round 4 (21 Oct 2026)

- AI-guided setup: [`AI-GUIDE.md`](AI-GUIDE.md), [`CLAUDE.md`](CLAUDE.md)/[`AGENTS.md`](AGENTS.md), [`setup/`](setup/) for Windows and macOS, three no-account ways to give the kit to your AI, `KIT-FOR-CHAT.txt` bundle.
- Two prerequisites: a paid AI plan, and chapter accounts in Microsoft 365 or Google Workspace for at least the Chapter Manager and the Chair (`manager@`, `chair@`) — required, not recommended, so the handover works and the Chair can read the chapter folder.

## Contributions from Chapter Managers

This list starts with v0.2. No entries yet. Each entry follows one format:
`{{what changed, as a pattern}} · {{version}} · contributed by {{"a Chapter Manager in <region>", or a name on request}}`
Names appear only if the contributor asks for it. How to contribute: write to the maintainer, or open an issue in this
repository if you already use GitHub; for prompts, see "Share a prompt" in [`08-prompts/prompt-library.md`](08-prompts/prompt-library.md).

## Planned

- Workshop feedback folded into the next version — every "that won't work for us" from the wall, with its reason.
- Re-check every `[verify]` and "as of Oct 2026" line against current tool and YPO information.

Feedback and corrections: write to the maintainer (see [`README.md`](README.md)), or open an issue in this repository if you already use GitHub.
