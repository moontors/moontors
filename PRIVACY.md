# Privacy Policy

Last updated: 5 November 2026

Moontors is a desktop app for running AI coding agents (Claude Code, Codex, Gemini CLI and
Grok Build) on your own computer, with a phone app for Android and iPhone that shows and works with
the same sessions (see "The phone app"). This policy says what Moontors, its phone app, and its
website moontors.com (see "The website") do with your information. In short: Moontors keeps what it
stores on your computer and your phone, and gives the agents only what they need to do your work,
listed below. Unless you turn it off, the desktop and phone apps send PostHog counts of how they're
used and reports of their errors, under a random id for the install, never tied to your account,
and never your prompts, code, files or names (see "Usage numbers and error reports"). A Moontors
account is yours to make or not: Moontors works without one, and one keeps your email, how you sign
in and, if your plan gives push or reaching your computer from anywhere, your phones' push tokens and
your computers' and phones' names (see "Your Moontors account").

## What Moontors keeps, and where

Moontors keeps all of this on your computer, and never sends any of it to us. What it gives an
agent, which the agent may pass on to its vendor, is described under "What connects to the
internet".

- **In a `.moontors` folder in your home folder:**
  - your sessions (their transcripts and settings), the board's layout, your projects and the
    folders you've trusted for the agents, in
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
  - when the background service makes way for a newer version's, or restarts to update, the
    terminals that were running: each one's folder, name and size, and what it showed with its
    scrollback, in a file only you can read, which the next start reads and deletes at once.
    **Remove Moontors' Data…** keeps none;
  - the MCP servers you add in Moontors for one project's folder or for all projects, in the same
    database: each one's name, the agents and the folder it's for, and its command and arguments or
    its URL, with the names its environment variables and headers are set under, never their values,
    until you remove it;
  - the phones you paired: each one's name, whether it's an iPhone or Android, when it paired and
    last connected, and a hash of the token it signs in with, never the token itself; and in a
    `phone` folder, the private key and certificate your computer proves itself to your phones
    with, and a random id your phones know it by, made the first time you open a pairing window
    and replaced by **Forget all phones…**;
  - if your Moontors account's plan gives push or reaching your computer from anywhere, in the same
    database: this computer as the relay knows it (the account it registered under, the id
    Moontors' server gave it and its relay's address), until **Forget all phones…** or the server
    removes it, and in another's place once it registers under another account; and,
    until the server has taken them, which phones were unpaired, by the id your computer gave each,
    and that every phone was forgotten, so the server drops their push tokens and relay credentials
    even after a restart.
- **In your operating system's keychain** (the macOS Keychain, Windows Credential Manager, or your
  Linux desktop's secret store; where none runs, the kernel's keyring, which forgets it at
  restart):
  - an API key you give Moontors, or the cloud sign-in you choose for Claude Code or Gemini CLI,
    which keep none of their own (an AWS profile's name or keys, a Bedrock API key, a Google Cloud
    credential file's location or key, or a Microsoft Foundry key or token, with the region,
    project or resource it goes with), until you sign out of that provider in Moontors;
  - an agent's sign-in made through Moontors, when the agent keeps its sign-in there (as Claude
    Code does on macOS);
  - the values of each MCP server you add in Moontors for one project's folder or for all projects
    (its environment variables or its headers), one entry for each server, until you remove the
    server;
  - your Moontors account's sign-in on this computer, if you signed in: the server's token for it,
    and the account as it was last read (its id, email, sign-in methods, plan and what the plan
    gives, its Pro subscription's state, monthly or yearly, when it renews or ends and until when
    its first payment may be refunded, and whether Pro is on sale for it), until you sign out.
- **In a project's own files, only when you add an MCP server to that project:** the server, its
  values included, in the agent's own project file (such as `.mcp.json`), where everyone who opens
  the project shares it, and which Moontors changes again only to remove that server. Moontors
  keeps none of it.
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
  project's own log, and Grok Build in its own prompt history, which deleting a session leaves in
  place. Neither reaches what the agent's vendor keeps on its own servers.
- Removing a phone in **Phones** deletes Moontors' record of it, and disconnects it; a phone that's
  connected then forgets your computer, and the drafts it kept. **Forget all phones…** removes
  every phone and also replaces your computer's key, so no phone paired before can reach it. A
  phone that isn't connected at the time may keep your computer's details until you choose
  **Forget this computer** on it, or uninstall the app. The backup copy from the latest update that
  changed the database may still hold a removed phone's record, until the next such update replaces
  that copy or you delete it.
- **Sign out**, on **Profile**'s **Account** tab in Moontors, ends this computer's sign-in at
  Moontors' server and removes it from the keychain, and **Delete account…** there deletes the
  account from the server (see "Your Moontors account").
- Removing an MCP server you added in Moontors removes it from Moontors' database and its values
  from the keychain; removing one from a project's own file takes it out of that file.
- Signing out of a provider in Moontors removes the API key or cloud credentials you gave it from
  the keychain, and signs the agent out, which removes the sign-in it kept (such as Claude Code's
  keychain entry, Codex's and Grok Build's `auth.json`, or Gemini CLI's credentials and its record
  of which Google account signed in).
- To remove everything Moontors keeps, choose **Help → Remove Moontors' Data…** in Moontors. It
  lists what it will delete first, including any worktree with uncommitted changes. Then it signs
  out of each provider and of your Moontors account, removes Moontors' keychain entries (the MCP
  servers' values among them), stops the
  background service, deletes the folders listed above (on macOS, its preferences and saved window
  state too) and quits. It removes links to your own folders as links, never following them. It
  leaves your repositories' branches and Git's worktree records (step 3 below), the Codex sandbox
  accounts on Windows (step 5) and files the agents keep for themselves (step 6), and the
  confirmation names what each agent leaves.
- To do it by hand instead, for example if Moontors can't start:
  1. Sign out of your Moontors account (Profile, the **Account** tab, **Sign out**) and of
     each provider in Moontors, then quit Moontors. The background service stops on its own once
     any running sessions finish.
  2. Delete the `.moontors` folder, the app's own folder and the update cache folders listed above,
     and on macOS also `~/Library/Preferences/com.moontors.app.plist` and
     `~/Library/Saved Application State/com.moontors.app.savedState`.
     Deleting `.moontors` also deletes the worktrees, with any changes in them that aren't
     committed. **On Windows, delete `.moontors` in File Explorer:** it holds links to some of your
     own folders, which File Explorer removes as links, while some command-line tools (such as
     Windows PowerShell 5.1's `Remove-Item -Recurse`) would follow them and delete your own files.
  3. In each repository you used, run `git worktree prune`, then delete the branches you no
     longer want.
  4. Signing out removes Moontors' keychain entries, but not the MCP servers' values. If you
     couldn't sign out first, or for those: the entry named `moontors` holds the API keys you gave
     Moontors, and the cloud sign-ins you chose for Claude Code or Gemini CLI (one for each
     provider), and the values of each MCP server you added (one for each server, its account
     starting `mcp/`), the entry named `moontors-account` holds
     your Moontors account's sign-in on this computer, and Claude Code's sign-in through Moontors
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

- No account needed: Moontors works without one, and a Moontors account is yours to make or not
  (see "Your Moontors account").
- No tracking across other apps or sites, and no advertising identifier. The usage numbers and
  error reports, which you can turn off, carry a random id for the install alone (see "Usage numbers
  and error reports"); beside it, no identifier but a Moontors account's own: its id, its computers'
  and phones' ids, its phones' push tokens and relay credentials, and the random id each call to its
  server carries (see "Your Moontors account"). Once you turn a phone's notifications on, Firebase's
  own software in the app sends Google what "Push notifications" says, which Moontors never sees.
- No advertising, and nothing is sold or shared.

## What connects to the internet

Moontors itself connects only to:

- **GitHub,** to check for a newer version of Moontors when it starts and every 4 hours, and to
  download one. GitHub sees your computer's IP address and the request, as with any download,
  under GitHub's own privacy policy. Moontors sends no identifier with it.
- **The npm registry** (registry.npmjs.org), to download the agents' own programs the first time
  you use each one, and when Moontors moves to a newer version of them. npm sees your IP address.
- **Moontors' server** (api.moontors.com), only while you're signed in to a Moontors account, or
  signing in to one; see "Your Moontors account".
- **PostHog** (eu.i.posthog.com), with the usage numbers and error reports, unless you turn them off;
  see "Usage numbers and error reports".

**Git, when Moontors makes a worktree,** runs your repository's own hooks and filters (such as Git
LFS), which may connect to the servers they name, as they would for any checkout.

**Links open in your browser.** A sign-in page (an agent vendor's, or an MCP server's), a page a
command opens (for example to upgrade your plan), and any web link you click in Moontors open in
your browser, which connects to that site.

**The agents are separate programs.** When you use Claude Code, Codex, Gemini CLI or Grok Build
through Moontors, your prompts, the files the agent reads and its replies go between that agent
and its vendor (Anthropic, OpenAI, Google or xAI), or the cloud service you set the agent up with
(such as Amazon Bedrock, Google Vertex AI or Microsoft Foundry), and to any MCP servers you add to
it, and its own tools (such as web fetches, shell commands and hooks) reach whatever sites they're
pointed at, exactly as when you use the agent on its own. That is governed by those services' own
terms and privacy policies, and by the agent's own settings, including any usage data the agent
itself sends.

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
- once the first turn of a session you didn't name is over, that session's first message once
  more, with an instruction to give the session a title: Claude Code's own title request, a short
  thread of Codex's own (on its small model for titles where your ChatGPT account lists it) or a
  separate run of Gemini CLI, none of which the agent keeps;
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
- Moontors' name and version, which Codex, Gemini CLI and Grok Build receive when Moontors starts
  them. Codex names Moontors to OpenAI as the app it runs in.

Moontors receives from the agents only what they report to it (their replies, models, usage and
limits), and keeps it on your computer.

## Usage numbers and error reports

Unless you turn it off, the desktop app and the phone app send PostHog counts of how they're used and
reports of their errors, so we can see what to improve and what breaks. Each app's are its own, under
a random id for the install, never tied to your Moontors account, your email or any other id of
yours, and PostHog keeps no profile of you.

- **What the desktop app sends:** Moontors installed, updated, and opened on a day; a session
  started, by its agent, mode and model, whether in a worktree and whether from the phone; a mode or
  a model chosen; the most sessions running at once on a day, as a range; each feature used on a day;
  an agent or the Moontors account signed in, Upgrade clicked, and the checkout opened; a turn that
  ended on an error, by its code; an agent, a window or Moontors itself that crashed, and an update
  that failed; and an error in Moontors' own code, by its kind and where in that code it was. With
  each: Moontors' version, your computer's system, its version and chip, and your Moontors account's
  plan. A model is named only on its vendor's own route (Anthropic's, OpenAI's, Google's or xAI's),
  and only by the vendor's own name for it; on a cloud, a gateway, another endpoint or a custom model
  option it goes as "other", whatever it's named.
- **What the phone app sends:** the app installed and updated; a pairing finished, by whether it
  worked; how it reached your computer, on a day; notifications turned on; a permission or a question
  answered; a message sent, on a day; the layout it showed, on a day; and the demo opened. With each:
  the app's version, the phone's system, its version, maker and model (never the name you gave it),
  its screen's size, whether notifications are on, and whether it's paired; on an iPhone, also the
  languages the phone prefers, in order, which its system adds to every request. And an error in the
  app, by its kind and where in the app's code it was. On Android, a crash in the app's Java or Kotlin
  code that happens while sharing is on is reported by PostHog's crash reporting in the app, which
  sends the crash's reason or message as the system gives it, which Moontors can't remove: Moontors'
  own code puts none of your text there, but another part of the app or the system rarely may; and
  the phone's carrier and its user agent. A crash caught while sharing was on and not yet sent stays
  on the phone, and goes only once sharing is on again, with the random id the app had when it
  crashed. The app reports no other crash of its native code, and no crash of its native code on an
  iPhone.
- **Never sent:** your prompts, code or files, the paths on your computer, the names of your
  projects, sessions, branches, repositories or computers, session titles, emails, keys, anything an
  agent writes, a pairing code or link, or a notification token. An error goes without its message,
  but for an Android crash's, as above.
- **Where you are:** PostHog finds the country and continent from your IP address, then discards the
  address, and keeps no city or finer place.
- **Turning it off:** in the desktop app, **Settings → Privacy**; in the phone app, the Accounts
  sheet, or the pairing screen before it's paired. Off, nothing more is sent from that app, what was
  still waiting to go is dropped (but for a crash already caught on an Android phone, which waits,
  as above), and its random id is forgotten, so turning it on again starts a new one. On your
  computer, `DO_NOT_TRACK=1` in the environment Moontors starts in, or in your shell's startup
  files, keeps it off whatever the switch says.
- **How long:** PostHog keeps them for up to 12 months, then deletes them.
- **Why:** our legitimate interest (the GDPR's article 6(1)(f)) in seeing how Moontors is used and
  what goes wrong, so we can fix and improve it. The switch is your objection, and it takes effect at
  once.
- **Who:** PostHog, Inc., in the United States, on its EU cloud, hosted in Frankfurt, Germany. It
  processes them for us alone, under its data processing agreement, which we've signed (see "Where
  it's processed").

Moontors' server also sends PostHog counts of its own, its errors and its log's lines, never naming
you (see "What reaches the server, and what it logs").

## Your Moontors account

A Moontors account is optional: Moontors and its phone app work without one. It's Moontors' own,
apart from your agents' sign-ins: signing in to it with Google never signs Gemini CLI in, and no
agent's sign-in ever reaches it. You make it, and sign in to it, in your browser, on Moontors'
server at api.moontors.com, which Render hosts in Frankfurt, Germany, with the server's database
there. Your sessions, your code and anything a session holds never reach the server.

### What the server keeps

- Your email address, verified: an account is made only once a code mailed to it is entered, or
  once Google, Apple or GitHub says it has verified it.
- Each way the account signs in: a password as its hash, never the password itself, and for Google,
  Apple or GitHub, the id that provider gives your account there. It keeps none of the provider's
  tokens, nor the name or picture the provider gives. An Apple sign-in goes once Apple tells the
  server you've stopped using your Apple Account with Moontors, or deleted it.
- Each sign-in, one for each browser and each computer signed in: a random token, when it was made
  and when it ends, 30 days after it was last used, and once ended it's deleted within a day. Never
  the IP address it came from, nor the browser it was made in.
- The settings your computers sync, as each signed in does unless you turn it off there: each
  agent's defaults for a new session, the agents' order, the quick actions, what **Rephrase** does,
  what the Git view's network button does and whether **Files** saves as you leave a file, each with
  when it last changed, until the account is deleted. Never a project, a folder, a sign-in or a key.
- If your plan gives push, as Pro does, or the developer allows your account: each phone your
  computers send its notifications to, by the id your computer gave it, with its push token from
  Google's Firebase, until the phone is unpaired, the account deleted, or 60 days pass without your
  computer sending the token again, as it does each day the phone connects with notifications on
  (see "Push notifications" under "The phone app").
- If your plan reaches your computer from anywhere, as Pro does, or the developer allows your
  account, and registered only while it does: each of your computers, by the id the server gave it
  and the random id Moontors on it made, with its name as your system names it, the region whose
  relay it uses and when it was last connected; each phone given a credential to reach it through
  the relay, from the moment it's given one, used or not, by the id your computer gave it, with its
  name, its credential as a hash, never the credential itself, when it was paired and when it last
  reached the computer; a pairing window's one-time meeting place, as its hash, until it's used or
  the next pairing window replaces it; and how many bytes your phones' links passed through the
  relay each day, for the caps, never what they held. A phone goes once it's unpaired or revoked, a
  computer with every phone it has once you forget all phones on it, and all of it once the account
  is deleted.
- From your first checkout for Pro, paid or not: your customer id at Paddle, which sells Pro, and
  the id of each checkout's transaction there, so that only a subscription bought through one of
  them is ever yours. Once you buy it: your subscription's id there, and its state as Paddle last told the server: whether
  it's active, past due, paused or canceled, monthly or yearly, when it renews, when a cancel you
  scheduled ends it, and when it was first paid for, so that deleting the account within 14 days of
  that refunds it. Never a card, an address, an invoice or an amount, which Paddle keeps. Each is
  kept until the account is deleted, a canceled subscription with them.
- While a step is under way, for no longer than it lasts: a sign-up's code, as its hash, with the
  email it was mailed to, for ten minutes; when each code was mailed to an email, by a hash of the
  address, for a day, so that no more than ten a day go to one address; a link to set a new
  password, for an hour; a sign-in in your browser for your computer, for up to an hour, and the
  code that hands it to Moontors, as its hash, for five minutes; and a sign-in with Google, Apple or
  GitHub, or a method being linked, for ten minutes. Each goes once it's used, or once it has
  expired, when the server next clears what has.

### What the server sends, and to whom

- **Your mail, through Resend:** a sign-up's code and a link to set a new password go to your email
  from Moontors' own address, sent by Resend from its EU region, in Ireland. Resend receives your
  email address and the mail's text, the code or the link with it, and keeps its record of what it
  sent, under its own privacy policy and data processing terms.
- **Google, Apple and GitHub, when you sign in with them:** your browser goes to the provider's
  sign-in page, and the provider tells Moontors' server your email, whether it has verified it and
  the id of your account there, with a name and picture the server drops. The provider learns that
  you signed in to Moontors, under its own privacy policy. Sign in with Apple can give a private
  relay address in place of your email, and mail to it passes through Apple.
- **Push, through Google's Firebase:** if your plan gives push, the server hands Google's Firebase
  Cloud Messaging each notification your computer sealed for a phone, with that phone's push token,
  and Firebase passes an iPhone's on to Apple's push service. They carry only the token, the sealed
  notification, which they can't read, and, for an iPhone, an alert in Moontors' own words that says
  nothing of your sessions, under their own privacy policies.
- **Pro, through Paddle:** Paddle sells Pro as its merchant of record. The server gives it your
  email, to make your customer at Paddle once, at your first checkout, and your account's id with
  each checkout, so the subscription it makes is yours; it asks Paddle for Pro's prices, your
  invoices and the customer portal's links as you open them, and cancels and refunds as deleting
  the account says. At checkout you give Paddle your card, your address and what tax needs
  yourself, and Paddle keeps them and its record of each purchase under its own
  [privacy notice](https://www.paddle.com/legal/privacy). Paddle tells the server each change to
  your subscription, by its id and state.
- Nothing else: the server sells nothing, shares nothing and shows no advertising.

### What reaches the server, and what it logs

- **The relay**, if your plan reaches your computer from anywhere: your phone's link to your
  computer passes through the server when the phone can't reach your computer directly, encrypted
  between them with your computer's own key, so the server can't read it
  (see "Through the relay"). It sees only how much passes and when, and counts each day's bytes.
  Your computer keeps a connection open to it while your plan gives it.

- Each request reaches it through Render's network, which passes it through Cloudflare first, and
  both see your IP address, as any website's host does, under their own privacy policies.
- The server reads the IP address only to limit how often one address tries something, a relay
  credential or meeting place it got wrong among them, how often it asks for Pro's prices, and how
  many sign-up codes and password links it mails for one address in a day: it counts in the
  server's memory alone, never stored, each try going within ten seconds after its minute has
  passed, and each mail after its day.
- The server's log, which Render keeps for up to 30 days, holds each request's method, the route it
  matched, its status and how long it took, and a random id for the request, which the desktop's own
  log of a failed call to the server carries too. The relay's own lines, for an account reaching a
  cap or a count the relay couldn't write, billing's, for each change to an account's subscription
  Paddle told the server of, with its state, and the one for an Apple sign-in taken off, with what
  Apple said, also carry the account's id, kept as long. Never an email address, a token, a code,
  a password, an IP address, what a page held or what passed through the relay.
- The server sends PostHog, in its EU cloud, how many Moontors accounts are made, by the way each
  signed up, and deleted, by its plan; how many Pro subscriptions start, renew and end, by how often
  each bills or why it ended; and the server's own failures, by where in the server each happened,
  its error's codes and the request's random id. Never your account's id, an email address, a
  payment's id, an amount, an IP address or what a request held. PostHog keeps them up to 12 months.
  It also sends PostHog the server's log, each line as the log above holds it but without the
  account's id, and PostHog keeps those lines 14 days.
- Its pages set two cookies, to sign you in and for nothing else: `__Secure-moontors.session_token`,
  your browser's sign-in, which lasts while it's used, until 30 days without, and
  `__Secure-moontors.state`, for five minutes while a sign-in with Google, Apple or GitHub is under
  way. They run no script, load nothing from any other site, and have no analytics or trackers.

### What your computer sends it

Moontors on your computer keeps the account's sign-in in your keychain (see
"What Moontors keeps, and where") and calls the server only while signed in, or signing in, but to
ask for Pro's prices: it reads the account once a day, which keeps its sign-in alive, and again each
time its **Account** or **Subscription** tab in **Profile** shows, and sends what you ask on the
**Account** tab, to sign out, link a method or delete the account, each with the account's token and
a random id for the call. While your plan isn't Pro, signed in or not, the **Subscription** tab asks
the server for Pro's prices and whether Pro is on sale each time it shows, with no token and nothing
of you or your computer. Unless you turn syncing settings off on the **Account** tab,
it sends the settings it syncs (see "What the server keeps") when one changes, as it signs in or
starts, when its window comes to the front, at most once a minute, and hourly, and takes back those
your other computers changed.
If your plan gives push, it also sends each paired phone's push token, which the server forgets once the phone is unpaired or once 60 days pass without it, and the notifications
for phones that aren't connected with the app open, each sealed on your computer so that only its
phone can read it.
If your plan reaches your computer from anywhere, it also registers your computer, by its random id
and its name as your system names it; asks the server for a one-time meeting place each time you
open a pairing window, good until the window ends, for a phone to pair through the relay; asks it
for a credential for each phone it pairs, which it hands to that phone alone over their encrypted
link; tells the server when a phone is unpaired, and when you forget all phones; and reads the
phones on your account and this month's use for its tab.
As that tab shows, it also asks the server for Pro's prices and your invoices, and, as you ask for
them, a checkout, which it opens in your browser, and the customer portal's links.

### Why the server keeps it

- **To give you the account and the features you asked for**, the contract between us (the
  GDPR's article 6(1)(b)): your email, your sign-in methods and sign-ins, the settings your
  computers sync, the steps under way, the mail Resend sends; if your plan gives push, your phones' push tokens and the notifications
  Firebase carries; and if it reaches your computer from anywhere, your computers, their phones'
  relay credentials, the pairing windows' meeting places and each day's bytes through the relay;
  from your first checkout, your customer at Paddle and your checkouts' transactions; and once you
  buy Pro, your subscription there and its state. Each is kept as long as this policy says above, the account until you delete it.
- **To keep the server and its accounts safe and working**, our legitimate interest (article
  6(1)(f)): the server's log, which never names you, and its count of each address's tries, in its
  memory for a minute after the address's last try, or a day after the last mail it asked for.
- **To see how Moontors is used and what goes wrong**, our legitimate interest too: the counts and
  errors the server sends PostHog, and its log's lines there, none of which names you (see "What
  reaches the server, and what it logs").
- Nothing is kept or sent on consent, for marketing or for anyone else's use. Everything else
  Moontors keeps, on your computer and your phone, stays there and never reaches us.

### Where it's processed

The server, its database and its log are at Render in Frankfurt, and Resend sends your mail from its
EU region in Ireland. But the companies behind them, and the others below, are in the United States:
Render's and Resend's terms say their primary processing takes place there. Each names the basis its
transfers of personal data out of the EU rest on:

- **Render** (Render Services, Inc.), which hosts the server and this website: the EU-U.S. Data
  Privacy Framework, under which it's certified, and the EU's standard contractual clauses where the
  framework doesn't apply or stops being available (its
  [data processing addendum](https://render.com/dpa), section 6, and its
  [privacy policy](https://render.com/privacy)).
- **Resend** (Plus Five Five, Inc.), which sends your mail: the EU's standard contractual clauses,
  and it's certified under the EU-U.S. Data Privacy Framework too (its
  [data processing addendum](https://resend.com/legal/dpa), sections 6 and 11).
- **Cloudflare** (Cloudflare, Inc.), which Render's network passes each request to the server
  through: its certification under the EU-U.S. Data Privacy Framework, and the standard contractual
  clauses should it lapse (its [privacy policy](https://www.cloudflare.com/privacypolicy/)).
- **Google** (Google LLC), whose Firebase Cloud Messaging carries push: the EU-U.S. Data Privacy
  Framework, and the standard contractual clauses where it isn't available (Firebase's
  [data processing terms](https://firebase.google.com/terms/data-processing-terms), section 10, and
  Google's [data transfer frameworks](https://policies.google.com/privacy/frameworks)). Firebase may
  process what it carries in any country where Google or its subprocessors have facilities.
- **Apple**, whose push service carries an iPhone's notifications on from Firebase: standard
  contractual clauses, and it generally stores personal data in the United States (its
  [privacy policy](https://www.apple.com/legal/privacy/en-ww/)).
- **PostHog** (PostHog, Inc.), which takes the apps' usage numbers and error reports and the
  server's own, and its log's lines, on its EU cloud, hosted by Amazon Web Services in Frankfurt: the EU's standard
  contractual clauses, in its [data processing agreement](https://posthog.com/dpa), which we've
  signed; its subprocessors, Cloudflare among them, are listed there, and it gives notice before it
  adds one.
- **Paddle** (Paddle.com Market Limited, in the United Kingdom, with its companies in the United
  States, Ireland and Canada), which sells Pro: a country an EU or UK adequacy decision covers, and
  the standard contractual clauses for any other (its
  [privacy notice](https://www.paddle.com/legal/privacy), section F).

### Deleting your account

- **Sign out**, on **Profile**'s **Account** tab in Moontors, ends this computer's sign-in at the
  server and removes it from your keychain. **Help → Remove Moontors' Data…** signs out too.
- **Delete account…**, on the same tab, deletes the account from the server at once: its email, its
  sign-in methods, every sign-in, the settings your computers synced, its phones' push tokens, its computers with their phones and the
  relay's counts, and what it keeps of Pro. The server may ask you to sign in again first. If you
  pay for Pro, it first cancels the subscription at Paddle at once, refunding its first payment in
  full within 14 days of it; if Paddle can't be reached, nothing is deleted. A step under way goes
  once it has expired, when the server next clears what has. Resend keeps its record of the mail it
  sent by its own terms, Paddle its record of each purchase, as a seller must, Render keeps the
  server's log for its days, and PostHog its lines for 14; the log never names you. If your address signs up for a Moontors
  account again later, the server moves your old customer's email at Paddle to an address no mail
  reaches before the new account checks out, so the new account never sees your purchases.
- Questions about your account's data: moontors@moontors.com.

## The phone app

The phone app shows the sessions Moontors runs on your computer, and works with them from your
phone. It pairs with your computer, and what you do in it goes only there: the phone signs in to no
account, and nothing is in between but Moontors' relay, where your computer's Moontors account has
it, which carries the link without reading it (see "Through the relay"). Push notifications, which
you can turn on, go through your computer's Moontors account too (see "Push notifications").

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
- copies of the photos and files you pick or paste to send, in the app's cache, each until it leaves
  the message, sent or taken off, or its session goes, and any still there when the app next starts;
  and of a transcript you export, until you export another or the app next starts;
- where your computer's Moontors account has the relay, the phone's relay credential for each
  computer, with the relay's address and the server's id for the computer, kept as the paired
  computers are but apart from them;
- once push notifications are on, the key each paired computer's notifications open with, in
  storage sealed by the Android Keystore, or in an iPhone's keychain, kept to that iPhone alone and
  shared only with the app's own extension that opens notifications; and Firebase's token for the
  app, which Firebase keeps in the app's storage;
- whether you've turned usage sharing off, and, while it's on, PostHog's random id for the app and
  what's waiting to be sent, which PostHog's software keeps in the app's storage.

Android's backup is off for the app, and a move to a new phone with Android's own transfer carries
none of these. On an iPhone, the paired computers and their relay credentials go into its backups
locked to that iPhone: restored onto it they come back, and no other iPhone can read them, so they
never move to a new one. The app's other files go into your iPhone's backups as any app's do: the
messages you've typed but not sent, and the random value that marks the install, which pairs with
nothing on its own. The copies in the app's cache don't.

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
computer is on, or through Moontors' relay, and to find it on the local network, it looks for
Moontors there (mDNS), which an iPhone asks you to allow first; the phone announces nothing itself.

- **The camera** is used only to scan the pairing code, which the app reads on the phone itself.
  No picture is kept or sent, and only the code it reads is used.
- **Photos and files** are read only when you choose them, through your phone's own photo and file
  pickers, and sent only to your computer. A photo goes unchanged, as the picker hands it over, with
  any details its file still holds; on an iPhone with iOS 17 or later, the picker's own Options say
  whether that includes where it was taken.
- **Links** open in your phone's browser.
- **Moontors' relay,** where your computer's Moontors account has it, as "Through the relay" says.
- **Firebase,** only once you turn push notifications on, as "Push notifications" says.
- **PostHog,** the usage numbers and error reports, unless you turn them off, as "Usage numbers and
  error reports" says. PostHog's software also asks PostHog for the app's settings as the app
  starts, naming only Moontors' project.
- **Google Play,** where the Android app comes from, gives Moontors' developer counts of its
  installs, and reports of the app's crashes and freezes (ANRs) from phones whose owners let Android
  share usage and diagnostics with Google. Those come from Google, under its own privacy policy;
  nothing of them comes from the app.
- **The App Store,** where the iPhone app comes from, gives Moontors' developer counts of its
  downloads; counts of its sessions and active devices, and reports of the app's crashes and hangs,
  from iPhones whose owners chose to share analytics with app developers; and the ratings and
  reviews posted there. Those come from Apple, under its own privacy policy; nothing of them comes
  from the app.

### Through the relay

Where your computer's Moontors account has the relay, as Pro does, or the developer allows your
account, the phone can reach your computer from anywhere through Moontors' server:

- **Its credential:** when the phone pairs from a code that names the relay, or, paired before, the
  first time it reaches your computer once the account has the relay, your computer registers the
  phone with Moontors' server, by the id it gave the phone and the phone's name, and hands the phone
  the relay credential the server issued for it, with the relay's address and the server's id for
  your computer. The phone keeps them as "What the phone keeps, and where" says.
- **Each link through it:** the phone sends the relay its credential and the server's id for your
  computer, or, pairing, the code's one-time meeting place, and the relay sees the phone's IP
  address.
  Inside, the link is the same TLS pinned to your computer's own key, with the phone's token: the
  relay passes it on and can't read it, nor stand in for your computer.
- **Removing it:** forgetting the computer on the phone, or the phone being unpaired, deletes its
  relay credential from the phone; the relay saying it no longer takes the credential does too.

### Push notifications

Push notifications work through your computer's Moontors account: your computer signed in to it,
with a plan that gives push, as Pro does, or the developer allows your account. The phone itself
signs in to nothing. They're off until you turn them on in the app, which asks your phone's
permission first. Until then, the app never contacts Firebase. Once they're on:

- The phone asks Firebase Cloud Messaging, the Google service that delivers notifications to Android
  phones, and to iPhones through Apple's own service, for a token that addresses this app on this
  phone. Firebase sees your IP address and makes an installation ID for the app, and its software in
  the app sends Google the app's version, the phone's model, brand and system, and which Firebase
  software it runs, with, on an iPhone, its language and time zone, and on Android, the store that
  installed the app, which Google uses to count the versions in use and to keep the service
  working, never linked to you, under Google's own privacy policy.
- The phone gives that token to each computer it's paired with, over the paired link, with a random
  key for that computer alone, each time it connects. Your computer registers the token with
  Moontors' server under its account, to send your computer's notifications to your phone, and
  "Your Moontors account" says how long the server keeps it. The key never leaves your phone and
  your computer.
- Your computer seals each notification's words (the session's title and what happened) with that
  key before they leave it, so Moontors' server, Firebase and Apple carry only ciphertext, which only
  your phone opens. On an iPhone, Apple's notification says "Moontors needs you" until the phone has
  opened it, and keeps saying it if it can't.
- With notifications off, in your phone's settings, by your account's plan or by your computer
  signing out, nothing sends the token again, so the server deletes it within 60 days.
- Unpairing the phone deletes the token from the server, at once while your computer is signed in,
  and within 60 days in any case. As it unpairs, the phone gives up that computer's key, and the
  token too once no computer it's paired with has notifications on.
- Forgetting a computer on the phone, which that computer doesn't hear of, gives up its key and the
  token at once, and the phone takes a new token for its other computers as it next links to each.
  The server deletes the old token the next time that computer sends to it, as Firebase answers that
  it's gone, or within 60 days.

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

- It's a set of static pages. Moontors sets no cookies on them, and has no advertising or trackers;
  the pay pages' Paddle.js is Paddle's (below).
- It counts its visits with PostHog, in its EU cloud, without cookies and keeping nothing in your
  browser. Once a page has loaded, it sends PostHog:
  - the page's address, keeping of its query only a campaign's tags, those named `utm_` and on;
  - where you came from, by its site alone;
  - your browser and its version, your system, the size of your screen and window, your language and
    your time zone;
  - how fast the page loaded;
  - a download or store badge you click: which file or store it was, where on the page it was, and
    whether it was the download suggested for your system;
  - that the pricing came into view;
  - a docs search that found nothing, its words lowercased, with no digits or email address;
  - a missing page's address, the same way;
  - an error in the site's own scripts, by its kind and where in them it happened, never its
    message.
- PostHog gets your IP address with each request, as any site's host does. It counts a day's
  visitors by a hash of your IP address, your browser, the site and a salt it deletes each day, then
  discards the address. No location is kept, no profile of you is made, and nothing links your
  visits from one day to the next.
- A browser that sends Do Not Track or Global Privacy Control sends nothing and loads nothing of
  PostHog's, and the pay pages never do.
- The site counts visits for our legitimate interest in knowing which pages people read and what
  they download (the GDPR's article 6(1)(f)). PostHog keeps them up to 12 months.
- The docs' sidebar remembers which sections you opened, in your browser's session storage, which
  stays in that tab and is never sent.
- Its search runs in your browser, on an index it loads from the site, so what you search for
  isn't sent anywhere, but for a search that finds nothing, as above.
- It's hosted by Render, which serves the pages and, like any web host, sees your IP address and
  the pages you request, under Render's own privacy policy.
- Its download links lead to GitHub, which sees the download as described above.
- Moontors' sign-in pages, at api.moontors.com, are the server's (see "Your Moontors account").
- Its pay pages, moontors.com/pay and, for testing, moontors.com/pay/sandbox, are where Paddle's
  checkout for Moontors Pro opens, from **Upgrade** in Moontors or a link in one of Paddle's emails.
  They load Paddle.js from Paddle, which opens Paddle's checkout over the page, so Paddle sees your
  IP address and your browser. Paddle, which sells Pro as its merchant of record, collects what you
  enter in its checkout (your email address, your country and address details, a tax number if you
  give one, and your card or other payment details) under its own
  [privacy notice](https://www.paddle.com/legal/privacy). Moontors never sees your payment details.
  Paddle's documents don't say what Paddle.js or its checkout keep in your browser: the cookies
  section of its privacy notice and its
  [Cookie Notice](https://www.iubenda.com/privacy-policy/83216669/cookie-policy) cover paddle.com
  alone ("This policy relates solely to this Website"). No other page of the site loads anything
  from Paddle.

If the site ever sets cookies or sends more, this policy changes first.

## Your rights

Under the GDPR, and laws like it where you live, you can ask us about what Moontors' server keeps
about you, and:

- **access** it: a copy of all of it;
- **rectify** it: the account's email can't be changed in Moontors, so ask us; you can link another
  sign-in method on **Profile**'s **Account** tab yourself;
- **erase** it: **Delete account…** on that tab deletes it at once (see "Deleting your account"), or
  ask us;
- **take it with you**: a copy in a machine-readable form;
- **object** to what the server keeps for our legitimate interest, its log and its count of tries.

The usage numbers and error reports aren't tied to your account or your email: we can't find an
app's by either. To object to them, turn them off in the app (see "Usage numbers and error reports"), which
also forgets the app's random id, so nothing sent before can be linked to what it sends after (but
for an Android phone's crash caught before and sent later, which keeps the id it had then).

Ask at moontors@moontors.com, from your account's email address so we know it's yours. You can also
complain to a data protection supervisory authority, such as the one where you live or work.

## Children

Moontors is a developer tool, not meant for children under 16.

## Changes

If Moontors ever changes what it collects, this policy changes first, and its date at the top
changes with it.

## Contact

Roi Dayan, Moontors' developer, decides what Moontors does with the personal data this policy
describes, and is its controller under the GDPR. Questions about privacy, and the requests in
"Your rights", go to moontors@moontors.com.
