# Privacy Policy

Last updated: 7 October 2026

Moontors is a desktop app for running AI coding agents (Claude Code, Codex and Gemini CLI) on your
own computer. This policy says what Moontors does with your information. In short: Moontors itself
collects nothing about you, keeps what it stores on your computer, and gives the agents only what
they need to do your work, listed below.

## What Moontors keeps, and where

Moontors keeps all of this on your computer, and never sends any of it to us. What it gives an
agent, which the agent may pass on to its vendor, is described under "What connects to the
internet".

- **In a `.moontors` folder in your home folder:**
  - your sessions (their transcripts and settings), the board's layout and your projects, in
    Moontors' database. Before an update that changes the database, Moontors keeps a backup copy
    of it beside it (`moontors.db.v<number>-<time>.bak`);
  - the background service's log;
  - the agents' own programs, which Moontors downloads;
  - each agent's folder for the sessions Moontors runs. The agent keeps its own files there, and
    its sign-in when you sign in through Moontors. Moontors also puts a copy of your own
    configuration for that agent there (such as its settings, your MCP servers and their
    credentials, and your instructions), and links to your own skills, commands, agents, rules
    and extensions (on Windows, some of them as copies), so its sessions run with your setup;
  - the worktrees Moontors makes for sessions that work on their own branch.
- **In your operating system's keychain** (the macOS Keychain, Windows Credential Manager, or your
  Linux desktop's secret store; where none runs, the kernel's keyring, which forgets it at
  restart):
  - an API key you give Moontors, until you sign out of that provider in Moontors;
  - an agent's sign-in made through Moontors, when the agent keeps its sign-in there (as Claude
    Code does on macOS).
- **In the app's own folder** (`~/Library/Application Support/Moontors` on macOS,
  `%APPDATA%\Moontors` on Windows, and `~/.config/Moontors` on Linux, or under `$XDG_CONFIG_HOME`):
  the window's preferences, the session last shown, and the caches the app's window keeps. On
  macOS, the system also keeps the app's preferences (`com.moontors.app`) and its saved window
  state.
- **In an update cache folder** (`~/Library/Caches/moontors-updater` on macOS,
  `%LOCALAPPDATA%\moontors-updater` on Windows, and `~/.cache/moontors-updater` on Linux, or under
  `$XDG_CACHE_HOME`): the last downloaded update, until the next one replaces it, and on Windows the
  last installer.
- **In your repositories:** the branches Moontors makes for worktree sessions, and Git's own
  record of each worktree.
- **Files you open in Moontors** are read and saved where they already are.

The agents also keep files of their own outside these folders. For example, Claude Code keeps
`~/.claude/.device-keys.json` in your home folder.

### Deleting it

- Deleting a session in Moontors deletes it from Moontors' database; a backup copy made before an
  earlier update still holds it until you delete that copy. Where the agent can, deleting a
  session also deletes the agent's own copy, and Moontors says before you confirm whether it will.
  Neither reaches what the agent's vendor keeps on its own servers.
- Signing out of a provider in Moontors removes the key you gave it from the keychain, and runs
  the agent's own sign-out, which removes the sign-in it kept (such as Claude Code's keychain
  entry, Codex's `auth.json` or Gemini CLI's credentials).
- To remove everything Moontors keeps:
  1. Sign out of each provider in Moontors, then quit Moontors. The background service stops on
     its own once any running sessions finish.
  2. Delete the `.moontors` folder, the app's own folder and the update cache folder listed above,
     and on macOS also `~/Library/Preferences/com.moontors.app.plist` and
     `~/Library/Saved Application State/com.moontors.app.savedState`.
     Deleting `.moontors` also deletes the worktrees, with any changes in them that aren't
     committed. **On Windows, delete `.moontors` in File Explorer:** it holds links to some of your
     own folders, which File Explorer removes as links, while some command-line tools (such as
     Windows PowerShell 5.1's `Remove-Item -Recurse`) would follow them and delete your own files.
  3. In each repository you used, run `git worktree prune`, then delete the branches you no
     longer want.
  4. Signing out removes Moontors' keychain entries. If you couldn't sign out first: the entry
     named `moontors` holds the API keys you gave Moontors (one for each provider), and Claude
     Code's sign-in through Moontors is an entry named `Claude Code-credentials-` followed by a
     short code, one for each Claude configuration folder. The entry named exactly
     `Claude Code-credentials` is your own Claude Code's: keep it, and leave alone any entries
     other apps made.
  5. If you ran Codex's Windows sandbox setup, Codex created local user accounts
     (`CodexSandboxOffline`, `CodexSandboxOnline`), a group (`CodexSandboxUsers`) and firewall
     rules (`codex_sandbox_offline_*`) on that computer. To remove them, run PowerShell as an
     administrator:
     `Remove-LocalUser CodexSandboxOffline,CodexSandboxOnline; Remove-LocalGroup CodexSandboxUsers; Remove-NetFirewallRule -DisplayName 'codex_sandbox_offline_*'`.
  6. Files an agent keeps for itself, such as Claude Code's, are that agent's; see its own
     documentation.

## What Moontors doesn't do

- No account: you don't sign up for Moontors.
- No analytics, telemetry, crash reporting, identifiers or tracking of any kind.
- No advertising, and nothing is sold or shared.

## What connects to the internet

Moontors itself connects only to:

- **GitHub,** to check for a newer version of Moontors when it starts and every 4 hours, and to
  download one. GitHub sees your computer's IP address and the request, as with any download,
  under GitHub's own privacy policy. Moontors sends no identifier with it.
- **The npm registry** (registry.npmjs.org), to download the agents' own programs the first time
  you use each one, and when Moontors moves to a newer version of them. npm sees your IP address.

**Git, when Moontors makes a worktree,** runs your repository's own hooks and filters (such as Git
LFS), which may connect to the servers they name, as they would for any checkout.

**Links open in your browser.** A sign-in page (an agent vendor's, or an MCP server's), a page a
command opens (for example to upgrade your plan), and any web link you click in Moontors open in
your browser, which connects to that site.

**The agents are separate programs.** When you use Claude Code, Codex or Gemini CLI through
Moontors, your prompts, the files the agent reads and its replies go between that agent and its
vendor (Anthropic, OpenAI or Google), or the cloud service you set the agent up with (such as Amazon
Bedrock, Google Vertex AI or Microsoft Foundry), and to any MCP servers you add to it, and its own
tools (such as web fetches, shell commands and hooks) reach whatever sites they're pointed at,
exactly as when you use the agent on its own. That is governed by those services' own terms and
privacy policies, and by the agent's own settings, including any usage data the agent itself sends.

What Moontors gives an agent goes only to that agent, which may pass it on to its vendor as above:

- what you type;
- the API key you gave Moontors for that provider, if you signed in with one;
- your shell's environment (such as `PATH`), as your terminal would give it to the agent;
- the choices you make for the session in Moontors: its folders, model, effort, fast mode,
  permission mode, output style, auto-compact threshold, switches, approved rules and sandbox
  settings;
- your own configuration for that agent, as described above, as the agent would read it itself;
- the prompts some Moontors commands write for you, such as /init and a review, and a recap, which
  repeats your recent messages and the agent's replies in that session;
- a subtask's answer, which Moontors passes to the session that started the subtask, together
  with your next prompt to it;
- short requests, with no conversation, for the models your account can use and its usage limits,
  so Moontors can show them;
- Moontors' name and version, which Codex and Gemini CLI receive when Moontors starts them. Codex
  names Moontors to OpenAI as the app it runs in.

Moontors receives from the agents only what they report to it (their replies, models, usage and
limits), and keeps it on your computer.

## Children

Moontors is a developer tool, not meant for children under 16.

## Changes

If Moontors ever changes what it collects, this policy changes first, and its date at the top
changes with it. Paid features may come in the future; if they need an account or payment details,
this policy will say what is collected, by whom and why, before they arrive.

## Contact

Questions about privacy: hello@moontors.com.
