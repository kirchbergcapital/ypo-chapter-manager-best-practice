# Setup on a Mac

Purpose: install what the optional steps of the kit need on macOS 13 or newer — with a check after every install and the usual bumps.
Time: 5–10 minutes per program. Install only what your station needs ([`README.md`](README.md)).

Tool facts: as of 21 Oct 2026, with sources. `[verify]` marks what we could not confirm on the provider's own page.

## 0 · Open Terminal

1. Press **Cmd + Space**, type `Terminal`, press Enter. (Or Finder → Applications → Utilities → Terminal.)
2. Paste a command with **Cmd + V**, then press **Enter**.
3. When an install asks for your **password**, type your Mac login password. The Terminal shows nothing while you type — that is normal. Press Enter.

**Homebrew** is optional — a package manager some people like. You do not need it for this kit; every program below also has a normal installer.
If you already use it, the `brew` lines are the short way. Install it only from [brew.sh](https://brew.sh).

## 1 · Your storage's desktop app

So the chapter folder is also on your laptop (Level 2 and 3). See [`../01-foundations/where-your-data-lives.md`](../01-foundations/where-your-data-lives.md).

| Storage | How |
|---|---|
| **Google Drive** | Install *Google Drive for desktop* from Google's download page `[verify: google.com/drive/download]` |
| **OneDrive** | Install OneDrive from the Mac App Store or Microsoft's download page `[verify]`, and sign in with the account that owns the chapter folder |

**Check:** Finder shows the storage in the sidebar (under *Locations* or *Favorites*), and your chapter folder is inside.

## 2 · The Claude desktop app (the way without a terminal)

Download it from the Claude website `[verify: claude.ai/download]`, open the downloaded file and drag Claude into *Applications*.
It offers Claude Code with a normal window ([source](https://code.claude.com/docs/en/setup)) and Cowork for your local folder
(paid plans; the app stays open while it works — [source](https://support.claude.com/en/articles/13345190)).

## 3 · Node.js (LTS)

Needed for your own WhatsApp app ([`../09-whatsapp-app-build-guide/`](../09-whatsapp-app-build-guide/)).

**Install:** the **macOS Installer (.pkg)**, LTS version, from [nodejs.org/en/download](https://nodejs.org/en/download): double-click, Continue, Install, enter your password.

With Homebrew instead: `brew install node` (this installs the newest version rather than LTS — both work for the kit).

**Check** (in a **new** Terminal window):

```bash
node --version
npm --version
```

`node --version` should show `v20` or higher — `v24` or higher for the mini CRM (module 12).

## 4 · Claude Code

Level 3, and the tool that builds your WhatsApp app. Needs Claude Pro, Max, Team or Enterprise — not Free; macOS 13 or newer ([source](https://code.claude.com/docs/en/setup)).

**Install — one of the two** ([source](https://code.claude.com/docs/en/setup)):

```bash
curl -fsSL https://claude.ai/install.sh | bash
```

```bash
brew install --cask claude-code
```

**Check** (new window): `claude --version`. `command not found` after the first installer? Its folder is missing from your PATH — run `echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.zshrc`, quit Terminal (Cmd + Q), open it again, check again. Then go to your chapter folder and start it: `cd "<path to your chapter folder>"`, then `claude`.
Tip: type `cd ` (with a space) and drag the folder from Finder into the Terminal window — the path appears by itself.
The first start asks a few setup questions `[verify: wording and order change]`: a colour theme (any is fine), how to log in (your Claude subscription account, then the browser login — you do that yourself), and whether you trust this folder (check the path it shows; yes only for your chapter folder). These are setup steps, not chapter tasks — no hours line for them.

## 5 · Git (needed for the WhatsApp app)

Your own WhatsApp app (station 10) needs Git while it installs: one library is downloaded from GitHub. You do **not** need a GitHub account. For everything else in this kit Git is optional.


For a private repository of your chapter folder (Level 3, optional).

Type `git --version`. If Git is missing, macOS offers to install the *Command Line Developer Tools* — click **Install** and wait a few minutes `[verify]`.
With Homebrew instead: `brew install git`.
**Check** (new window): `git --version`.

## 6 · Python (only if a step needs it)

Nothing in the kit's path needs Python. Install it only if your AI tool asks for it for a specific step.

**Install:** the macOS installer from [python.org/downloads](https://www.python.org/downloads/).
**Check** (new window): `python3 --version`. On a Mac the command is `python3`, not `python`.

## Typical bumps

| You see | What helps |
|---|---|
| `command not found` right after an install | Close Terminal completely (Cmd + Q) and open it again. For Claude Code: read the last lines the installer printed — if they say to add a folder to your PATH, paste those lines into your AI tool and ask it to walk you through it |
| *"… can't be opened because Apple cannot check it"* or *"unidentified developer"* | Only for installers you downloaded from the sources on this page: System Settings → Privacy & Security → scroll down → **Open Anyway** `[verify the wording for your macOS version]` |
| The password prompt shows no characters | Normal in Terminal. Type the password and press Enter |
| `brew: command not found` | Homebrew is not installed — use the normal installer instead; Homebrew is optional |
| `zsh: permission denied` | You probably tried to run a file instead of a command. Copy the command again exactly, or paste the message into your AI tool |
