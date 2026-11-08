# Paid plan, training off

Purpose: work in an AI plan that can do the chapter's real work, and make sure your chats do not train the provider's models.
Time: 20 minutes once, then 2 minutes a quarter.

**Facts on this page: as of 21 Oct 2026.** Every tool fact links to its source. Facts we could not confirm on the
provider's own page are marked `[verify]`. **Check this once a quarter — menus move.**

## Why a paid plan

This kit assumes a paid plan. Free plans are not part of it. **A business plan is ideal** — no training by default, a data processing agreement,
an admin who adds and removes people, connectors switched on once for everyone. Which one to buy, prices and seat minimums, and a 10-point check:
[business-plan-checklist.md](business-plan-checklist.md).

A paid plan is a working tool, and the features this kit uses most sit there:

| You want | Needs | Source |
|---|---|---|
| A project with your house rules and files, so every chat starts informed | Claude Projects (files up to 30 MB each). ChatGPT Projects: 25 files per project on Go and Plus, 40 on Pro, Business, Enterprise and Edu (Free: 5) | [Claude](https://support.claude.com/en/articles/8241126) · [ChatGPT](https://help.openai.com/en/articles/10169521-projects-in-chatgpt) |
| Your AI reads mail and drafts replies in your mailbox | Connectors — see [`../07-connectors-and-browser/email-connectors.md`](../07-connectors-and-browser/email-connectors.md) | [Claude](https://support.claude.com/en/articles/10166901) |
| Your AI fills your Canva designs | Canva connector in Claude: available in Claude's connector directory; check which plans include it there; on Team and Enterprise the owner enables it first | [Claude help](https://support.claude.com/en/articles/11176164) · [Claude connector](https://claude.com/connectors/canva) |
| An assistant in your browser for portals | Claude in Chrome — all paid plans | [Claude](https://support.claude.com/en/articles/12012173) |
| Your AI works in your local folder (Level 2 and 3) | Claude Cowork (paid plans, desktop app) · Claude Code (Pro, Max, Team, Enterprise — not Free) · ChatGPT Work in the ChatGPT desktop app (which plans `[verify]`) | [Cowork](https://support.claude.com/en/articles/13345190) · [Claude Code](https://code.claude.com/docs/en/setup) · [ChatGPT Work](https://help.openai.com/en/articles/6825453-chatgpt-release-notes) |

**Who pays?** The chapter, ideally — the AI does chapter work, and a business plan in the chapter's name comes with the data processing agreement. The one-page AI rules in
[`../06-chapter-rules/ai-use-one-pager.md`](../06-chapter-rules/ai-use-one-pager.md) give your Chair a ready decision for the next ExCo.

## Switch training off — tool by tool

| Tool | Where the switch is | Default | Business plans | Source |
|---|---|---|---|---|
| **Claude** (Pro, Max) | Settings → Privacy → **"Help improve our AI models"** → off. Direct: claude.ai/settings/data-privacy-controls | Check yours `[verify]` | Team and Enterprise: no training by default | [Setting](https://privacy.claude.com/en/articles/12109829) · [Retention](https://privacy.claude.com/en/articles/10023548) · [Business](https://privacy.claude.com/en/articles/7996868) |
| **ChatGPT** (Plus, Pro) | Settings → Data controls → **"Improve the model for everyone"** → off | On (Free, Plus, Pro on a personal workspace) | Business, Enterprise, Edu: no training by default | [How your data is used](https://help.openai.com/en/articles/5722486-how-your-data-is-used-to-improve-model-performance) · [Keep history, stop training](https://help.openai.com/en/articles/8983130-what-if-i-want-to-keep-my-history-on-but-disable-model-training) |
| **Microsoft Copilot** with a work account (Entra ID) | Nothing to switch: no training of the base models, Enterprise Data Protection applies | Protected | This *is* the business plan. "Microsoft 365 Copilot" is now called "Microsoft Copilot" | [Microsoft Learn](https://learn.microsoft.com/en-us/copilot/microsoft-365/enterprise-data-protection) |
| **Microsoft Copilot** with a personal account | Privacy → **"Training on conversation activity"** and the voice equivalent → off | On `[verify]` | Use a work account instead | [Microsoft support](https://support.microsoft.com/en-us/microsoft-copilot/microsoft-copilot-privacy-controls) |
| **Gemini** (personal Google account) | **"Keep Activity"** → off. Future chats are not used for training; they are kept 72 hours | On `[verify]` | Gemini in Google Workspace (the chapter accounts): no training without permission — this switch is for personal accounts; leave activity on there so Gems can read the chapter's Drive ([where-your-data-lives.md](where-your-data-lives.md)) | [Google help](https://support.google.com/gemini/answer/13594961) · [Workspace](https://support.google.com/a/answer/15706919) |

Good to know for Claude:
- Switch it off first, then start working. Switching it off also stops future training on chats you have stored; data already used in training is not removed.
- With training on, data can be kept up to 5 years. Deleted chats leave the backend within 30 days. Incognito chats are never used for training. [Source](https://privacy.claude.com/en/articles/10023548)

## Do it now (5 minutes)

1. Open your AI tool's settings and find the switch in the table above.
2. Switch it off. Take a screenshot.
3. Save the screenshot on your desktop for now, named `YYYY-MM-DD_ai-training-off.png`. Once your chapter folder exists, move it into `01-role-and-calendar/`.
4. Add a line to `00-handover/log.md`: `YYYY-MM-DD · ai-settings · screenshot · training off in {{TOOL}} · check again in 3 months`.
5. Put a quarterly reminder in your calendar: *"AI settings check — menus move."*

## Quarterly check (2 minutes)

```
I use {{TOOL}} on the {{PLAN}} plan. Today is {{DATE}}.
Tell me where the setting that controls training on my chats is today and what its name is.
Give me the link to the provider's own help page. If you are not sure, say so — I will check the page myself.
```

Then open the provider's page yourself. The page is the source, not the answer.

## What stays out, whatever the plan

Two things never go into any AI tool or the chapter folder: **Forum content** and **passwords**.
Forum is sacred. We use AI for Forum logistics only: dates, places, headcounts, costs, deadlines. Never for what is said in or around a Forum: topics, stories, notes, retreat conversations, anything shared in confidence, or any link between a name and a topic. If in doubt, leave it out.
Passwords go into the chapter's password manager. Everything else your role works with — bylaws,
events, budgets, mails — is exactly what the assistant is for. If your chapter has its own AI rules, they apply;
[`../06-chapter-rules/ai-use-one-pager.md`](../06-chapter-rules/ai-use-one-pager.md) is a ready proposal.

Next: [where-your-data-lives.md](where-your-data-lives.md).
