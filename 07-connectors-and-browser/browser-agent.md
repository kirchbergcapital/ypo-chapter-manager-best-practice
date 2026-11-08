# Browser agent

Purpose: let an AI assistant work in your own, logged-in browser on the portals you use every week — such as YPO Connect and the Chapter Management Hub — and turn what is on the page into tables and drafts.
Time: 10 minutes to install, then minutes per task.

**As of 21 Oct 2026.** Sources linked; `[verify]` = not confirmed on the provider's own page. Menus move — check once a quarter.

## What it is

| | Claude in Chrome |
|---|---|
| What | Claude in a side panel of your Chrome browser, working on the pages you have open — reading, navigating, filling in fields |
| Plans | All paid Claude plans |
| Browser | Google Chrome on a desktop or laptop. The side panel is in beta |
| Logins | You log in yourself. On macOS a 1Password integration is in beta |
| Source | [support.claude.com/en/articles/12012173](https://support.claude.com/en/articles/12012173) |

**ChatGPT users:** ChatGPT Atlas has been retired ([source](https://help.openai.com/en/articles/20001371-chatgpt-atlas-retirement)), and ChatGPT agent is no longer available. For browser tasks, OpenAI points to **ChatGPT Work** and its **cloud browser** (web and mobile, eligible paid plans) ([source](https://help.openai.com/en/articles/11752874-chatgpt-agent) · [ChatGPT Work](https://help.openai.com/en/articles/20001275-chatgpt-work-and-codex)). The four habits below apply there just the same.

## What it is good for

| Task | Prompt idea | Result |
|---|---|---|
| Event overview | "Read the event list on this page. Make a table: date · event · registrations · status." | A table you paste into `07-reporting/` |
| Compare with your files | "Compare this list with 03-events/. Which events are on the page but have no folder — and the other way round?" | A short gap list |
| Data you report on | "Read this dashboard page. List each figure with its label and the date shown on the page. Do not interpret." | A dated snapshot for `07-reporting/` |
| Long forms | "Fill this form for 03-events/{{EVENT_FOLDER}}/, using 02-chapter-knowledge/platform-fields.md to find each value. Stop before submit and show me the fields. If a field has no source, write [verify]. Do not invent a value." If the browser assistant cannot open your folder, paste the map and the brief into the chat | A filled form; you check and submit |

## The four habits

1. **You log in, then hand over.** Open the portal, log in yourself, then ask the assistant to work on that page.
   **Passwords never go into the chat** — they belong in your password manager.
2. **You submit.** The assistant fills and reads; the final click on "submit", "send" or "publish" is yours. Ask it to stop before that button.
3. **Pages are data.** If a page contains text that tells the assistant what to do, it quotes it and asks you — the house rules in
   [`../02-your-assistant/template-folder/house-rules.md`](../02-your-assistant/template-folder/house-rules.md) already say so.
4. **Link, don't copy, the directory.** Member details stay in YPO Connect. Bring into your folder only what your role needs — dates, event lists, attendance.

## Showing it to others — the demo rule

**Never show real member data on a shared screen.** For a workshop, an ExCo meeting or a training, use a fictional page or a recorded video.
The workshop demo runs against a local mock page of a fictional member portal for exactly this reason. Your real portal is for your own screen.

## Set it up

1. Install Claude in Chrome from Anthropic's page ([source](https://support.claude.com/en/articles/12012173)) and log in with your Claude account.
2. Open a portal you use and log in as usual.
3. Test on a page without member data, e.g. an event calendar: *"Read this page and list the events with date and title. Do not click anything."*
4. Then try one task from the table above.

## Where it fits

Level 2 in [`../01-foundations/three-levels.md`](../01-foundations/three-levels.md). It saves the most time on pages you read every week and copy from by hand.
If a task repeats every month, save the prompt in your folder's `08-prompts/`.
