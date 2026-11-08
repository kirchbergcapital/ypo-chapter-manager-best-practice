# Setup on Windows

Purpose: install what the optional steps of the kit need on Windows 10 or 11 — with a check after every install and the usual bumps.
Time: 5–10 minutes per program. Install only what your station needs ([`README.md`](README.md)).

Tool facts: as of 21 Oct 2026, with sources. `[verify]` marks what we could not confirm on the provider's own page.

## 0 · Open PowerShell

1. Click **Start**, type `PowerShell`, open **Windows PowerShell** (or **Terminal**, which opens PowerShell).
2. A normal window is enough. When an installer needs admin rights, Windows asks you itself — click **Yes**.
3. Paste a command with right-click or **Ctrl+V**, then press **Enter**.

**winget** is the Windows package manager many commands below use. Check it: `winget --version`.
The first time, winget may ask you to agree to the source terms — type `Y` and press Enter.
If `winget` is not recognised, use the installer link given for each program instead `[verify: winget comes with "App Installer" from the Microsoft Store]`.

## 1 · Your storage's desktop app

So the chapter folder is also on your laptop (Level 2 and 3). See [`../01-foundations/where-your-data-lives.md`](../01-foundations/where-your-data-lives.md).

| Storage | How |
|---|---|
| **OneDrive** | Usually already on Windows: look for the cloud icon at the bottom right, or Start → `OneDrive`. Sign in with the account that owns the chapter folder |
| **Google Drive** | Install *Google Drive for desktop* from Google's download page `[verify: google.com/drive/download]` |

**Check:** File Explorer shows the folder (OneDrive in the left column, Google Drive as its own drive), and your chapter folder is inside.

## 2 · The Claude desktop app (the way without a terminal)

Download it from the Claude website `[verify: claude.ai/download]` and install it like any other program.
It offers Claude Code with a normal window ([source](https://code.claude.com/docs/en/setup)) and Cowork for your local folder
(paid plans; the app stays open while it works — [source](https://support.claude.com/en/articles/13345190)).

## 3 · Node.js (LTS)

Needed for your own WhatsApp app ([`../09-whatsapp-app-build-guide/`](../09-whatsapp-app-build-guide/)).

**Install — one of the two:**

```powershell
winget install OpenJS.NodeJS.LTS
```

or the **Windows Installer (.msi)**, LTS version, from [nodejs.org/en/download](https://nodejs.org/en/download): double-click, Next, Next, done.
If the installer offers to install extra "tools for native modules", you can leave that box unticked; your AI tool will say if a step needs them `[verify wording]`.

**Check** (in a **new** PowerShell window):

```powershell
node --version
npm --version
```

`node --version` should show `v20` or higher.

## 4 · Claude Code

Level 3, and the tool that builds your WhatsApp app. Needs Claude Pro, Max, Team or Enterprise — not Free ([source](https://code.claude.com/docs/en/setup)).

**Install — one of the two** (no admin rights needed; [source](https://code.claude.com/docs/en/setup)):

```powershell
irm https://claude.ai/install.ps1 | iex
```

```powershell
winget install Anthropic.ClaudeCode
```

**Check** (new window): `claude --version`. Then go to your chapter folder and start it: `cd "<path to your chapter folder>"`, then `claude`.
The first start asks a few setup questions `[verify: wording and order change]`: a colour theme (any is fine), how to log in (your Claude subscription account, then the browser login — you do that yourself), and whether you trust this folder (check the path it shows; yes only for your chapter folder). These are setup steps, not chapter tasks — no hours line for them.

If Claude Code asks for **Git for Windows**, install Git first (§ 5) and open a new window `[verify: code.claude.com/docs/en/setup]`.

## 5 · Git (needed for the WhatsApp app)

Your own WhatsApp app (station 10) needs Git while it installs: one library is downloaded from GitHub. You do **not** need a GitHub account. For everything else in this kit Git is optional.


For a private repository of your chapter folder (Level 3, optional) — and if Claude Code asks for it.

```powershell
winget install Git.Git
```

or the installer from [git-scm.com/downloads](https://git-scm.com/downloads) (the default options are fine).
**Check** (new window): `git --version`.

## 6 · Python (only if a step needs it)

Nothing in the kit's path needs Python. Install it only if your AI tool asks for it for a specific step.

```powershell
winget install Python.Python.3.12
```

or the installer from [python.org/downloads](https://www.python.org/downloads/) — tick **"Add python.exe to PATH"** on the first screen `[verify wording]`.
**Check** (new window): `python --version` (or `py --version`).

## Typical bumps

| You see | What helps |
|---|---|
| `… is not recognized as the name of a cmdlet` right after an install | Close PowerShell and open a new window. Still there? Restart the laptop once — the PATH updates then |
| `npm.ps1 cannot be loaded because running scripts is disabled on this system` | Windows blocks script files by default. Allow them for your own user: `Set-ExecutionPolicy -Scope CurrentUser RemoteSigned`, confirm with `Y`, open a new window. Only needed if you see this message |
| `irm https://claude.ai/install.ps1 \| iex` stops with an error | Use the alternative `winget install Anthropic.ClaudeCode`, or the Claude desktop app (§ 2). Paste the error into your AI tool if both fail |
| Typing `python` opens the Microsoft Store | Python is not installed yet, or the window is older than the install — install it (§ 6) and open a new window |
| winget: `No package found matching input criteria` | Check the spelling of the command; otherwise use the installer link of that program |
| An installer asks for admin rights | Normal for installs you started from these pages — click Yes |
