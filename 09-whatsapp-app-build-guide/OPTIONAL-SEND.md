# Optional: send after you confirm

Purpose: an add-on prompt for later. It gives your app one more command — `send` — that sends **exactly one message to one chat**, and only after you have seen the text and typed `y`.
Time: about 15 minutes with your AI tool, once the read-only app works and [`CHECKLIST.md`](CHECKLIST.md) is ticked.

## Your decision first

Most Chapter Managers will not need this: your assistant drafts, you copy the draft into WhatsApp on your phone, done.
The send step saves that copy-and-paste when you are working at the laptop anyway.

Sending through an unofficial client is a bigger step for your own number than reading: WhatsApp's [messaging guidelines](https://www.whatsapp.com/legal/messaging-guidelines)
name unofficial clients, bulk messaging and auto-messaging among what they act against. One confirmed message at a time, to chats you already have,
at your own pace, stays close to how you write from your phone — whether you add it is your call.

Either way the chapter rule stays the same: **A human sends** — *"AI drafts; a person reads, edits and sends. No automatic sending, no bulk WhatsApp."*
([`../06-chapter-rules/ai-use-one-pager.md`](../06-chapter-rules/ai-use-one-pager.md)).

## What the send step does — and what it never does

| It does | It never does |
|---|---|
| Send **one** message to **one** chat that already exists in your saved chats | Send to several chats, to a list, or to a number you have never chatted with |
| Show you the chat, the full text and — for a group — the number of members, then wait for `y` | Send without your `y`, send on a timer, or send automatically in reply to anything |
| Take the text you type or paste in the terminal, or one `--text "…"` | Read the text from a file, a list or another program |
| Tell you if sending failed, without trying again on its own | Retry by itself (a retry could send the message twice) |

## The prompt

Open Claude Code in your `whatsapp-app` folder and paste everything inside the grey box.

```text
Please add ONE new command to this app: npm run send. Keep everything else exactly as it is, and keep all
existing tests passing.

WHAT SEND DOES
- npm run send -- --chat "<name>" [--text "<message>"]
- The chat must already exist in ./data. Use the same matching as export: exactly ONE exact name match (or "Me"
  for my own chat); otherwise list up to 10 names and stop; never more than one chat. No sending to a phone number
  that is not an existing chat.
- send is the one command that asks me something: the confirmation below. Everything else stays non-interactive.
- The never-export.txt words apply to send as well: refuse any chat whose name contains one of them.
- The message is ONE text. Either from --text, or - if --text is missing - typed or pasted at a prompt in the
  terminal (an empty line ends the input). No --file option, no reading from stdin when stdin is not a terminal,
  no lists, no templates with placeholders, no scheduling, no repeat.
- Before sending, show: the chat name, "group with N members" for a group, and the full text exactly as it will be
  sent. Then ask: "Send this one message to <chat>? Type y and press Enter." Only the single letter y sends.
  Anything else, or Ctrl-C, cancels and says "Nothing was sent."
- Refuse to run when stdout or stdin is not a terminal (so no other program or AI tool can confirm for me), and say
  "Run this in a terminal window - you confirm each message yourself."
- Send exactly once per run, then end the run. If sending fails, say so and do NOT retry; tell me to check my phone
  before I try again.
- Send needs the connection, so it takes the same lock as link and listen. If listen is running in another window,
  refuse with "Stop listen first (Ctrl-C in its window), then send."
- After a successful send, append one line to ./data/sent-log.jsonl: time, chat name, message id (no text).

WHAT STAYS FORBIDDEN
- sendMessage may appear in ONE place only: a function in src/send.js, called only after the y confirmation.
  Everything else from the "nothing is sent" rule stays forbidden: no read receipts (blue ticks), no typing state,
  no "online" presence, no reactions, no group or profile changes, no other network access.
  markOnlineOnConnect stays the literal false; the console stays muted during the connection.
- Update the tripwire test so it allows sendMessage only in src/send.js, exactly once, and still forbids it
  everywhere else.

TESTS (fictional data, temporary folders, mock socket)
- y sends exactly one message to exactly one chat; "n", empty input, "yes", "Y " and Ctrl-C send nothing.
- Not a terminal -> refused, nothing sent. --file or piped input -> refused.
- Unknown chat, a name that only partly matches, several exact matches, a never-export word, a phone number that
  is not a chat -> refused.
- A failed send is not retried. The lock is respected. sent-log.jsonl gets one line without the text.

README: add a short section "Sending one message" with the command, the confirmation, and one sentence that
sending through an unofficial client carries more risk for my number than reading, and that I can keep sending
from my phone instead.

When done, run the tests, show me every place in the code that sends anything, and then walk me through one test
send to my own chat with --chat "Me" - in a terminal window, while listen is stopped.
```

## Before you use it

Add four ticks to [`CHECKLIST.md`](CHECKLIST.md):

- [ ] Asked Claude Code *"show me every place that sends anything"* — the answer is **one** place, in `src/send.js`, behind the `y`.
- [ ] Test send with `--chat "Me"` reached your own chat; typing anything other than `y` sent nothing.
- [ ] The tripwire test (the one with "tripwire" in its name) still passes in `npm test`.
- [ ] I still send group posts and anything sensitive with a second look — one message, one chat, one `y`.
