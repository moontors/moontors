# Privacy Policy

Last updated: 27 October 2026

Moontors is a desktop app for running AI coding agents (Claude Code, Codex and Gemini CLI) on your
own computer, with a phone app for Android and iPhone that shows and works with the same sessions
(see "The phone app"). This policy says what Moontors, its phone app, and its website moontors.com
(see "The website") do with your information. In short: Moontors itself collects nothing about you,
keeps what it stores on your computer and your phone, and gives the agents only what they need to
do your work, listed below.

## What Moontors keeps, and where

Moontors keeps all of this on your computer, and never sends any of it to us. What it gives an
agent, which the agent may pass on to its vendor, is described under "What connects to the
internet".

- **In a `.moontors` folder in your home folder:**
  - your sessions (their transcripts and settings), the board's layout and your projects, in
    Moontors' database. When an update changes the database, Moontors first copies it as it was,
    on the new version's first start, and keeps that backup beside it
    (`moontors.db.v<number>-<time>.bak`), in place of any copy an earlier update kept;
  - the background service's log;
  - the agents' own programs, which Moontors downloads, only the version it runs of each: an older
    one is deleted each time the background service starts;
  - each agent's folder for the sessions Moontors runs. The agent keeps its own files there, and
    its sign-in when you sign in through Moontors. Moontors also puts a copy of your own
    configuration for that agent there (such as its settings, your MCP servers and their
    credentials, and your instructions), and links to your own skills, commands, agents, rules
    and extensions (on Windows, some of them as copies), so its sessions run with your setup. For
    Codex, that includes a copy of its plugin cache, which Moontors refreshes from yours each time
    the agent starts; plugins Codex installs for the account you signed in with through Moontors
    stay only in Moontors' copy. Gemini CLI has one such folder for each sign-in, sharing the
    sessions' history, and an old one is deleted once no session uses it;
  - the files you attach to messages. A file you send is kept with its session, copied to a fork of
    it, and deleted with the session. A file you add but don't send is deleted after an hour, or
    when the background service next starts. An image an agent makes in a session, as Codex makes
    one, is kept with the session the same way, so you can see it on your computer and your phone;
  - for a Claude Code session given a plugin with secrets, a private file holding them (see "Your
    own agents' secrets" below), deleted when that run of the agent ends;
  - the worktrees Moontors makes for sessions that work on their own branch;
  - the phones you paired: each one's name, whether it's an iPhone or Android, when it paired and
    last connected, and a hash of the token it signs in with, never the token itself; and in a
    `phone` folder, the private key and certificate your computer proves itself to your phones
    with, and a random id your phones know it by, made the first time you open a pairing window
    and replaced by **Forget all phones…**.
- **In your operating system's keychain** (the macOS Keychain, Windows Credential Manager, or your
  Linux desktop's secret store; where none runs, the kernel's keyring, which forgets it at
  restart):
  - an API key you give Moontors, or the cloud sign-in you choose for Claude Code or Gemini CLI,
    which keep none of their own (an AWS profile's name or keys, a Bedrock API key, a Google Cloud
    credential file's location or key, or a Microsoft Foundry key or token, with the region,
    project or resource it goes with), until you sign out of that provider in Moontors;
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
  last installer. On macOS, the system's updater also keeps a record of the last install, its log
  with the app's path and its last request, in `~/Library/Caches/com.moontors.app.ShipIt`, and
  macOS's cache of its exchange with Moontors' own updater, which hands it the download, in
  `~/Library/Caches/com.moontors.app`.
- **In your repositories:** the branches Moontors makes for worktree sessions, and Git's own
  record of each worktree.
- **Files you open in Moontors** are read and saved where they already are.

The agents also keep files of their own outside these folders. For example, Claude Code keeps
`~/.claude/.device-keys.json` in your home folder.

### Your own agents' secrets

A Claude Code plugin can keep sensitive options, and its MCP servers' secrets, in your own Claude
Code's entry in the system keychain (`Claude Code-credentials`), beside its sign-in; on Windows and
Linux, in its credentials file. Moontors reads that entry only when it starts a session with a
plugin that declares such an option. On macOS the system doesn't ask you first: Moontors reads the
entry with the same system tool Claude Code itself uses for it. It reads the whole entry, keeps only the secrets of the plugins it gives that session, and drops the rest at
once, your sign-in included. It never stores them in its own keychain entries or its database, never
logs them, and never changes your entry. It hands them to that session's Claude Code in a private
file in Moontors' folder for Claude Code, which goes when that run of the agent ends; one a crash
left behind is deleted when the agent next starts.

### Deleting it

- Deleting a session in Moontors deletes it from Moontors' database, and overwrites the space it
  took there, so its text doesn't linger in the file. The files attached to its messages are deleted
  with it; if the disk refuses, they go when the background service next starts. The backup copy from the latest update that
  changed the database may still hold it, until the next such update replaces that copy or you
  delete it. Where the agent can, deleting a session also deletes the agent's own copy, and
  Moontors says before you confirm whether it will. Gemini CLI also keeps your prompts in its
  project's own log, which deleting a session leaves in place. Neither reaches what the agent's
  vendor keeps on its own servers.
- Removing a phone in **Phones** deletes Moontors' record of it, and disconnects it; a phone that's
  connected then forgets your computer, and the drafts it kept. **Forget all phones…** removes
  every phone and also replaces your computer's key, so no phone paired before can reach it. A
  phone that isn't connected at the time may keep your computer's details until you choose
  **Forget this computer** on it, or uninstall the app. The backup copy from the latest update that
  changed the database may still hold a removed phone's record, until the next such update replaces
  that copy or you delete it.
- Signing out of a provider in Moontors removes the API key or cloud credentials you gave it from
  the keychain, and signs the agent out, which removes the sign-in it kept (such as Claude Code's
  keychain entry, Codex's `auth.json`, or Gemini CLI's credentials and its record of which Google
  account signed in).
- To remove everything Moontors keeps, choose **Help → Remove Moontors' Data…** in Moontors. It
  lists what it will delete first, including any worktree with uncommitted changes. Then it signs
  out of each provider, removes Moontors' keychain entries, stops the background service, deletes
  the folders listed above (on macOS, its preferences and saved window state too) and quits. It
  removes links to your own folders as links, never following them. It leaves your repositories'
  branches and Git's worktree records (step 3 below), the Codex sandbox accounts on Windows
  (step 5) and files the agents keep for themselves (step 6), and the confirmation names what each
  agent leaves.
- To do it by hand instead, for example if Moontors can't start:
  1. Sign out of each provider in Moontors, then quit Moontors. The background service stops on
     its own once any running sessions finish.
  2. Delete the `.moontors` folder, the app's own folder and the update cache folders listed above,
     and on macOS also `~/Library/Preferences/com.moontors.app.plist` and
     `~/Library/Saved Application State/com.moontors.app.savedState`.
     Deleting `.moontors` also deletes the worktrees, with any changes in them that aren't
     committed. **On Windows, delete `.moontors` in File Explorer:** it holds links to some of your
     own folders, which File Explorer removes as links, while some command-line tools (such as
     Windows PowerShell 5.1's `Remove-Item -Recurse`) would follow them and delete your own files.
  3. In each repository you used, run `git worktree prune`, then delete the branches you no
     longer want.
  4. Signing out removes Moontors' keychain entries. If you couldn't sign out first: the entry
     named `moontors` holds the API keys you gave Moontors, and the cloud sign-ins you chose for
     Claude Code or Gemini CLI (one for each provider), and Claude Code's sign-in through Moontors
     is an entry named `Claude Code-credentials-` followed by a short code, one for each Claude
     configuration folder. The entry named exactly `Claude Code-credentials` is your own Claude
     Code's: keep it, and leave alone any entries other apps made.
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

- what you type, and the files you attach to a message;
- the API key or cloud credentials you gave Moontors for that provider, if you signed in with them;
- with Claude Code, the secrets of the plugins it gives a session, as described under "Your own
  agents' secrets";
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
- a report on a session that you send to OpenAI with Codex's `/feedback`: what it's about and your
  words, with Codex's own tags (such as your ChatGPT user and account IDs, the session's model and
  settings, and Codex's version), and, unless you clear the box, Codex's logs and diagnostics and
  that session's whole conversation, the agent's own review's included, which Codex uploads from
  your account as its own `/feedback` does. Moontors asks Codex to send one only when you press
  Send, after saying what goes;
- Moontors' name and version, which Codex and Gemini CLI receive when Moontors starts them. Codex
  names Moontors to OpenAI as the app it runs in.

Moontors receives from the agents only what they report to it (their replies, models, usage and
limits), and keeps it on your computer.

## The phone app

The phone app shows the sessions Moontors runs on your computer, and works with them from your
phone. It pairs with your computer, and what you do in it goes only there: there's no account, no
Moontors server and nothing in between.

**See a demo**, before pairing, opens sample sessions inside the app, as your computer would run
them; nothing in it runs. Nothing in the demo is sent anywhere unless you share it yourself, and what you type in it is gone once you
leave it; its photos and files are samples of its own, never yours.

### What the phone keeps, and where

All of it in the app's own storage on the phone, which no other app can read:

- the computers it's paired with: each one's name and id, its addresses and port, the fingerprint
  of its key, the phone's own id there, and the token the phone signs in with, in Android's
  encrypted storage for the app, whose key the Android Keystore holds, or in an iPhone's keychain,
  kept to that iPhone alone; with them, a random value in the app's files that marks this install;
- the messages you've typed but not sent, in a file, each until you send it or its session goes,
  and all of them once the phone is no longer paired;
- copies of the photos and files you pick or paste to send, in the app's cache, each until it
  leaves the message, sent or taken off, or its session goes, and any still there when the app next
  starts; and of a transcript you export, until you export another or the app next starts.

Android's backup is off for the app, and a move to a new phone with Android's own transfer carries
none of these. On an iPhone, the paired computers go into its backups locked to that iPhone:
restored onto it they come back, and no other iPhone can read them, so they never move to a new one.
The app's other files go into your iPhone's backups as any app's do: the messages you've typed but
not sent, and the random value that marks the install, which pairs with nothing on its own. The
copies in the app's cache don't.

### What the phone sends, and to whom

What's yours goes only to the computer it paired with, and to any app you choose when you share an
exported transcript:

- **When pairing,** the phone's name and whether it's an Android phone or an iPhone (an Android
  phone's name as set in its settings, else its model; an iPhone, which doesn't give apps its name,
  as "iPhone"), with the secret the scanned code holds or, by the six-digit code, a proof that it
  knows the code; the six-digit code itself is never sent.
- **Once paired,** what you do in the app: the requests to show and act on your sessions, your
  messages, answers and choices, the photos and files you send, and the token it signs in with.
  Your computer's Moontors then handles them as the rest of this policy says, which includes giving
  your messages and files to the session's agent, which sends them to its vendor under your own
  account with them (see "What connects to the internet"). Moontors itself sends them nowhere
  else.

The link is TLS 1.3, pinned to your computer's own key, which the phone learns while pairing, so
nothing between the two can read it or stand in for your computer. The phone connects to your
computer's IP addresses, on your local network, through Tailscale, or through another VPN your
computer is on, and to find it on the local network, it looks for Moontors there (mDNS), which an
iPhone asks you to allow first; the phone announces nothing itself.

- **The camera** is used only to scan the pairing code, which the app reads on the phone itself.
  No picture is kept or sent, and only the code it reads is used.
- **Photos and files** are read only when you choose them, through your phone's own photo and file
  pickers, and sent only to your computer. A photo goes unchanged, as the picker hands it over, with
  any details its file still holds; on an iPhone with iOS 17 or later, the picker's own Options say
  whether that includes where it was taken.
- **Links** open in your phone's browser.
- **Google Play,** where the Android app comes from, gives Moontors' developer counts of its
  installs, and reports of the app's crashes and freezes (ANRs) from phones whose owners let Android
  share usage and diagnostics with Google. Those come from Google, under its own privacy policy;
  nothing of them comes from the app.
- **The App Store,** where the iPhone app comes from, gives Moontors' developer counts of its
  downloads; counts of its sessions and active devices, and reports of the app's crashes and hangs,
  from iPhones whose owners chose to share analytics with app developers; and the ratings and
  reviews posted there. Those come from Apple, under its own privacy policy; nothing of them comes
  from the app.

### Your computer's side

While a pairing window is open, or any phone is paired, Moontors listens for your phones on your
computer (port 47610, or another free port if that's taken). It takes connections only from a
network your computer is directly on (such as your local network, or another VPN's), from your
Tailscale network, or from the computer itself. It also announces itself
on your local network (mDNS, Bonjour on a Mac), under a random name, and under your computer's
name while a pairing window is open, so the phone can find it.

To unpair, see "Deleting it": removing the app from the phone deletes everything the phone keeps,
and removing the phone in Moontors deletes your computer's record of it.

## The website

This policy also covers Moontors' website, moontors.com:

- It's a set of static pages. It sets no cookies, and has no analytics, advertising or trackers.
- The docs' sidebar remembers which sections you opened, in your browser's session storage, which
  stays in that tab and is never sent.
- Its search runs in your browser, on an index it loads from the site, so what you search for
  isn't sent anywhere.
- It's hosted by Render, which serves the pages and, like any web host, sees your IP address and
  the pages you request, under Render's own privacy policy.
- Its download links lead to GitHub, which sees the download as described above.

If the site ever adds cookies or analytics, this policy changes first.

## Children

Moontors is a developer tool, not meant for children under 16.

## Changes

If Moontors ever changes what it collects, this policy changes first, and its date at the top
changes with it. Paid features may come in the future; if they need an account or payment details,
this policy will say what is collected, by whom and why, before they arrive.

## Contact

Questions about privacy: hello@moontors.com.
