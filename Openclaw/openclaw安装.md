Last login: Sun Feb  1 22:42:39 on console
fomalhaut@LawrencedeMacBook-Air ~ % curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.3/install.sh | b
zsh: command not found: b
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
 98 16631   98 16384    0     0  10604      0  0:00:01  0:00:01 --:--:-- 10604
curl: (56) Failure writing output to destination, passed 247 returned 0
fomalhaut@LawrencedeMacBook-Air ~ % curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.3/install.sh | b
zsh: command not found: b
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
 98 16631   98 16384    0     0   6857      0  0:00:02  0:00:02 --:--:--  6858
curl: (56) Failure writing output to destination, passed 247 returned 0
fomalhaut@LawrencedeMacBook-Air ~ % curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.3/install.sh | bash

  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100 16631  100 16631    0     0  74153      0 --:--:-- --:--:-- --:--:-- 74245
=> Downloading nvm from git to '/Users/fomalhaut/.nvm'
=> Cloning into '/Users/fomalhaut/.nvm'...
remote: Enumerating objects: 403, done.
remote: Counting objects: 100% (403/403), done.
remote: Compressing objects: 100% (332/332), done.
remote: Total 403 (delta 56), reused 168 (delta 43), pack-reused 0 (from 0)
Receiving objects: 100% (403/403), 404.19 KiB | 38.00 KiB/s, done.
Resolving deltas: 100% (56/56), done.
* (HEAD detached at FETCH_HEAD)
  master
=> Compressing and cleaning up git repository

=> Appending nvm source string to /Users/fomalhaut/.zshrc
=> Appending bash_completion source string to /Users/fomalhaut/.zshrc
=> Close and reopen your terminal to start using nvm or run the following to use it now:

export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion
fomalhaut@LawrencedeMacBook-Air ~ % \. "$HOME/.nvm/nvm.sh"
fomalhaut@LawrencedeMacBook-Air ~ % nvm install 24
Downloading and installing node v24.13.0...
Downloading https://nodejs.org/dist/v24.13.0/node-v24.13.0-darwin-arm64.tar.xz...
################################################################################################################# 100.0%
Computing checksum with sha256sum
Checksums matched!
Now using node v24.13.0 (npm v11.6.2)
Creating default alias: default -> 24 (-> v24.13.0)
fomalhaut@LawrencedeMacBook-Air ~ % node -v # Should print "v24.13.0".
v24.13.0
fomalhaut@LawrencedeMacBook-Air ~ % npm -v # Should print "11.6.2".
11.6.2
fomalhaut@LawrencedeMacBook-Air ~ % npm i -g openclaw
npm warn deprecated gauge@4.0.4: This package is no longer supported.
npm warn deprecated are-we-there-yet@3.0.1: This package is no longer supported.
npm warn deprecated npmlog@6.0.2: This package is no longer supported.
npm warn deprecated tar@6.2.1: Old versions of tar are not supported, and contain widely publicized security vulnerabilities, which have been fixed in the current version. Please update. Support for old versions may be purchased (at exorbitant rates) by contacting i@izs.me
npm warn deprecated node-domexception@1.0.0: Use your platform's native DOMException instead
npm warn deprecated glob@10.5.0: Old versions of glob are not supported, and contain widely publicized security vulnerabilities, which have been fixed in the current version. Please update. Support for old versions may be purchased (at exorbitant rates) by contacting i@izs.me
npm warn deprecated glob@11.1.0: Old versions of glob are not supported, and contain widely publicized security vulnerabilities, which have been fixed in the current version. Please update. Support for old versions may be purchased (at exorbitant rates) by contacting i@izs.me
npm error process terminated
npm error signal SIGINT
npm notice
npm notice New minor version of npm available! 11.6.2 -> 11.9.0
npm notice Changelog: https://github.com/npm/cli/releases/tag/v11.9.0
npm notice To update run: npm install -g npm@11.9.0
npm notice
npm error A complete log of this run can be found in: /Users/fomalhaut/.npm/_logs/2026-02-06T08_05_10_313Z-debug-0.log
fomalhaut@LawrencedeMacBook-Air ~ % npm i -g openclaw
npm warn deprecated npmlog@6.0.2: This package is no longer supported.
npm warn deprecated are-we-there-yet@3.0.1: This package is no longer supported.
npm warn deprecated gauge@4.0.4: This package is no longer supported.
npm warn deprecated tar@6.2.1: Old versions of tar are not supported, and contain widely publicized security vulnerabilities, which have been fixed in the current version. Please update. Support for old versions may be purchased (at exorbitant rates) by contacting i@izs.me
npm warn deprecated node-domexception@1.0.0: Use your platform's native DOMException instead
npm warn deprecated glob@11.1.0: Old versions of glob are not supported, and contain widely publicized security vulnerabilities, which have been fixed in the current version. Please update. Support for old versions may be purchased (at exorbitant rates) by contacting i@izs.me
npm warn deprecated glob@10.5.0: Old versions of glob are not supported, and contain widely publicized security vulnerabilities, which have been fixed in the current version. Please update. Support for old versions may be purchased (at exorbitant rates) by contacting i@izs.me

added 672 packages in 3m

125 packages are looking for funding
  run `npm fund` for details
fomalhaut@LawrencedeMacBook-Air ~ % openclaw onboard

🦞 OpenClaw 2026.2.3-1 (d84eb46) — Shell yeah—I'm here to pinch the toil and leave you the glory.

▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄
██░▄▄▄░██░▄▄░██░▄▄▄██░▀██░██░▄▄▀██░████░▄▄▀██░███░██
██░███░██░▀▀░██░▄▄▄██░█░█░██░█████░████░▀▀░██░█░█░██
██░▀▀▀░██░█████░▀▀▀██░██▄░██░▀▀▄██░▀▀░█░██░██▄▀▄▀▄██
▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀
                  🦞 OPENCLAW 🦞                    
 
┌  OpenClaw onboarding
│
◇  Security ──────────────────────────────────────────────────────────────────────────────╮
│                                                                                         │
│  Security warning — please read.                                                        │
│                                                                                         │
│  OpenClaw is a hobby project and still in beta. Expect sharp edges.                     │
│  This bot can read files and run actions if tools are enabled.                          │
│  A bad prompt can trick it into doing unsafe things.                                    │
│                                                                                         │
│  If you’re not comfortable with basic security and access control, don’t run OpenClaw.  │
│  Ask someone experienced to help before enabling tools or exposing it to the internet.  │
│                                                                                         │
│  Recommended baseline:                                                                  │
│  - Pairing/allowlists + mention gating.                                                 │
│  - Sandbox + least-privilege tools.                                                     │
│  - Keep secrets out of the agent’s reachable filesystem.                                │
│  - Use the strongest available model for any bot with tools or untrusted inboxes.       │
│                                                                                         │
│  Run regularly:                                                                         │
│  openclaw security audit --deep                                                         │
│  openclaw security audit --fix                                                          │
│                                                                                         │
│  Must read: https://docs.openclaw.ai/gateway/security                                   │
│                                                                                         │
├─────────────────────────────────────────────────────────────────────────────────────────╯
│
◇  I understand this is powerful and inherently risky. Continue?
│  Yes
│
◇  Onboarding mode
│  QuickStart
│
◇  QuickStart ─────────────────────────╮
│                                      │
│  Gateway port: 18789                 │
│  Gateway bind: Loopback (127.0.0.1)  │
│  Gateway auth: Token (default)       │
│  Tailscale exposure: Off             │
│  Direct to chat channels.            │
│                                      │
├──────────────────────────────────────╯
│
◇  Model/auth provider
│  Google
│
◇  Google auth method
│  Google Gemini API key
│
■  Enter Gemini API key
│
└  Setup cancelled.

fomalhaut@LawrencedeMacBook-Air ~ % openclaw obboard
error: unknown command 'obboard'
(Did you mean onboard?)
fomalhaut@LawrencedeMacBook-Air ~ % openclaw onboard

🦞 OpenClaw 2026.2.3-1 (d84eb46) — Ship fast, log faster.

▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄
██░▄▄▄░██░▄▄░██░▄▄▄██░▀██░██░▄▄▀██░████░▄▄▀██░███░██
██░███░██░▀▀░██░▄▄▄██░█░█░██░█████░████░▀▀░██░█░█░██
██░▀▀▀░██░█████░▀▀▀██░██▄░██░▀▀▄██░▀▀░█░██░██▄▀▄▀▄██
▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀
                  🦞 OPENCLAW 🦞                    
 
┌  OpenClaw onboarding
│
◇  Security ──────────────────────────────────────────────────────────────────────────────╮
│                                                                                         │
│  Security warning — please read.                                                        │
│                                                                                         │
│  OpenClaw is a hobby project and still in beta. Expect sharp edges.                     │
│  This bot can read files and run actions if tools are enabled.                          │
│  A bad prompt can trick it into doing unsafe things.                                    │
│                                                                                         │
│  If you’re not comfortable with basic security and access control, don’t run OpenClaw.  │
│  Ask someone experienced to help before enabling tools or exposing it to the internet.  │
│                                                                                         │
│  Recommended baseline:                                                                  │
│  - Pairing/allowlists + mention gating.                                                 │
│  - Sandbox + least-privilege tools.                                                     │
│  - Keep secrets out of the agent’s reachable filesystem.                                │
│  - Use the strongest available model for any bot with tools or untrusted inboxes.       │
│                                                                                         │
│  Run regularly:                                                                         │
│  openclaw security audit --deep                                                         │
│  openclaw security audit --fix                                                          │
│                                                                                         │
│  Must read: https://docs.openclaw.ai/gateway/security                                   │
│                                                                                         │
├─────────────────────────────────────────────────────────────────────────────────────────╯
│
◇  I understand this is powerful and inherently risky. Continue?
│  Yes
│
◇  Onboarding mode
│  QuickStart
│
◇  QuickStart ─────────────────────────╮
│                                      │
│  Gateway port: 18789                 │
│  Gateway bind: Loopback (127.0.0.1)  │
│  Gateway auth: Token (default)       │
│  Tailscale exposure: Off             │
│  Direct to chat channels.            │
│                                      │
├──────────────────────────────────────╯
│
◇  Model/auth provider
│  Google
│
◇  Google auth method
│  Google Gemini API key
│
◇  Enter Gemini API key
│  AIzaSyAvj3_SxbeC9gLXKy_Fr929mAgDIaxls30
│
◇  Model configured ─────────────────────────────────╮
│                                                    │
│  Default model set to google/gemini-3-pro-preview  │
│                                                    │
├────────────────────────────────────────────────────╯
│
◇  Default model
│  Keep current (google/gemini-3-pro-preview)
│
◇  Channel status ────────────────────────────╮
│                                             │
│  Telegram: not configured                   │
│  WhatsApp: not configured                   │
│  Discord: not configured                    │
│  Google Chat: not configured                │
│  Slack: not configured                      │
│  Signal: not configured                     │
│  iMessage: not configured                   │
│  Feishu: install plugin to enable           │
│  Google Chat: install plugin to enable      │
│  Nostr: install plugin to enable            │
│  Microsoft Teams: install plugin to enable  │
│  Mattermost: install plugin to enable       │
│  Nextcloud Talk: install plugin to enable   │
│  Matrix: install plugin to enable           │
│  BlueBubbles: install plugin to enable      │
│  LINE: install plugin to enable             │
│  Zalo: install plugin to enable             │
│  Zalo Personal: install plugin to enable    │
│  Tlon: install plugin to enable             │
│                                             │
├─────────────────────────────────────────────╯
│
◇  How channels work ─────────────────────────────────────────────────────────────────────╮
│                                                                                         │
│  DM security: default is pairing; unknown DMs get a pairing code.                       │
│  Approve with: openclaw pairing approve <channel> <code>                                │
│  Public DMs require dmPolicy="open" + allowFrom=["*"].                                  │
│  Multi-user DMs: set session.dmScope="per-channel-peer" (or "per-account-channel-peer"  │
│  for multi-account channels) to isolate sessions.                                       │
│  Docs: start/pairing                  │
│                                                                                         │
│  Telegram: simplest way to get started — register a bot with @BotFather and get going.  │
│  WhatsApp: works with your own number; recommend a separate phone + eSIM.               │
│  Discord: very well supported right now.                                                │
│  Google Chat: Google Workspace Chat app with HTTP webhook.                              │
│  Slack: supported (Socket Mode).                                                        │
│  Signal: signal-cli linked device; more setup (David Reagans: "Hop on Discord.").       │
│  iMessage: this is still a work in progress.                                            │
│  Feishu: Feishu/Lark bot via WebSocket.                                                 │
│  Nostr: Decentralized protocol; encrypted DMs via NIP-04.                               │
│  Microsoft Teams: Bot Framework; enterprise support.                                    │
│  Mattermost: self-hosted Slack-style chat; install the plugin to enable.                │
│  Nextcloud Talk: Self-hosted chat via Nextcloud Talk webhook bots.                      │
│  Matrix: open protocol; install the plugin to enable.                                   │
│  BlueBubbles: iMessage via the BlueBubbles mac app + REST API.                          │
│  LINE: LINE Messaging API bot for Japan/Taiwan/Thailand markets.                        │
│  Zalo: Vietnam-focused messaging platform with Bot API.                                 │
│  Zalo Personal: Zalo personal account via QR code login.                                │
│  Tlon: decentralized messaging on Urbit; install the plugin to enable.                  │
│                                                                                         │
├─────────────────────────────────────────────────────────────────────────────────────────╯
│
◇  Select channel (QuickStart)
│  Telegram (Bot API)
│
◇  Telegram bot token ───────────────────────────────────────────────────────────────────╮
│                                                                                        │
│  1) Open Telegram and chat with @BotFather                                             │
│  2) Run /newbot (or /mybots)                                                           │
│  3) Copy the token (looks like 123456:ABC...)                                          │
│  Tip: you can also set TELEGRAM_BOT_TOKEN in your env.                                 │
│  Docs: https://docs.openclaw.ai/telegram  │
│  Website: https://openclaw.ai                                                          │
│                                                                                        │
├────────────────────────────────────────────────────────────────────────────────────────╯
│
■  Enter Telegram bot token
│
└  Setup cancelled.

fomalhaut@LawrencedeMacBook-Air ~ % openclaw onboard

🦞 OpenClaw 2026.2.3-1 (d84eb46) — Siri's competent cousin.

▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄
██░▄▄▄░██░▄▄░██░▄▄▄██░▀██░██░▄▄▀██░████░▄▄▀██░███░██
██░███░██░▀▀░██░▄▄▄██░█░█░██░█████░████░▀▀░██░█░█░██
██░▀▀▀░██░█████░▀▀▀██░██▄░██░▀▀▄██░▀▀░█░██░██▄▀▄▀▄██
▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀
                  🦞 OPENCLAW 🦞                    
 
┌  OpenClaw onboarding
│
◇  Security ──────────────────────────────────────────────────────────────────────────────╮
│                                                                                         │
│  Security warning — please read.                                                        │
│                                                                                         │
│  OpenClaw is a hobby project and still in beta. Expect sharp edges.                     │
│  This bot can read files and run actions if tools are enabled.                          │
│  A bad prompt can trick it into doing unsafe things.                                    │
│                                                                                         │
│  If you’re not comfortable with basic security and access control, don’t run OpenClaw.  │
│  Ask someone experienced to help before enabling tools or exposing it to the internet.  │
│                                                                                         │
│  Recommended baseline:                                                                  │
│  - Pairing/allowlists + mention gating.                                                 │
│  - Sandbox + least-privilege tools.                                                     │
│  - Keep secrets out of the agent’s reachable filesystem.                                │
│  - Use the strongest available model for any bot with tools or untrusted inboxes.       │
│                                                                                         │
│  Run regularly:                                                                         │
│  openclaw security audit --deep                                                         │
│  openclaw security audit --fix                                                          │
│                                                                                         │
│  Must read: https://docs.openclaw.ai/gateway/security                                   │
│                                                                                         │
├─────────────────────────────────────────────────────────────────────────────────────────╯
│
◇  I understand this is powerful and inherently risky. Continue?
│  Yes
│
◇  Onboarding mode
│  QuickStart
│
◇  QuickStart ─────────────────────────╮
│                                      │
│  Gateway port: 18789                 │
│  Gateway bind: Loopback (127.0.0.1)  │
│  Gateway auth: Token (default)       │
│  Tailscale exposure: Off             │
│  Direct to chat channels.            │
│                                      │
├──────────────────────────────────────╯
│
◇  Model/auth provider
│  MiniMax
│
◇  MiniMax auth method
│  MiniMax M2.1
│
◇  Enter MiniMax API key
│  sk-api-NCoej27PrU52YHuJnH4brDY65bm6AJg3VBz4s-CwiW592nUAdqYOqBSBYhzo08RvFqmlKmDiKD6oHKVsrFJyM4M7VO3XoqZWS57LH4CjpwvNLN
e4jolYggY
│
◇  Default model
│  Keep current (minimax/MiniMax-M2.1)
│
◇  Channel status ────────────────────────────╮
│                                             │
│  Telegram: not configured                   │
│  WhatsApp: not configured                   │
│  Discord: not configured                    │
│  Google Chat: not configured                │
│  Slack: not configured                      │
│  Signal: not configured                     │
│  iMessage: not configured                   │
│  Feishu: install plugin to enable           │
│  Google Chat: install plugin to enable      │
│  Nostr: install plugin to enable            │
│  Microsoft Teams: install plugin to enable  │
│  Mattermost: install plugin to enable       │
│  Nextcloud Talk: install plugin to enable   │
│  Matrix: install plugin to enable           │
│  BlueBubbles: install plugin to enable      │
│  LINE: install plugin to enable             │
│  Zalo: install plugin to enable             │
│  Zalo Personal: install plugin to enable    │
│  Tlon: install plugin to enable             │
│                                             │
├─────────────────────────────────────────────╯
│
◇  How channels work ─────────────────────────────────────────────────────────────────────╮
│                                                                                         │
│  DM security: default is pairing; unknown DMs get a pairing code.                       │
│  Approve with: openclaw pairing approve <channel> <code>                                │
│  Public DMs require dmPolicy="open" + allowFrom=["*"].                                  │
│  Multi-user DMs: set session.dmScope="per-channel-peer" (or "per-account-channel-peer"  │
│  for multi-account channels) to isolate sessions.                                       │
│  Docs: start/pairing                  │
│                                                                                         │
│  Telegram: simplest way to get started — register a bot with @BotFather and get going.  │
│  WhatsApp: works with your own number; recommend a separate phone + eSIM.               │
│  Discord: very well supported right now.                                                │
│  Google Chat: Google Workspace Chat app with HTTP webhook.                              │
│  Slack: supported (Socket Mode).                                                        │
│  Signal: signal-cli linked device; more setup (David Reagans: "Hop on Discord.").       │
│  iMessage: this is still a work in progress.                                            │
│  Feishu: Feishu/Lark bot via WebSocket.                                                 │
│  Nostr: Decentralized protocol; encrypted DMs via NIP-04.                               │
│  Microsoft Teams: Bot Framework; enterprise support.                                    │
│  Mattermost: self-hosted Slack-style chat; install the plugin to enable.                │
│  Nextcloud Talk: Self-hosted chat via Nextcloud Talk webhook bots.                      │
│  Matrix: open protocol; install the plugin to enable.                                   │
│  BlueBubbles: iMessage via the BlueBubbles mac app + REST API.                          │
│  LINE: LINE Messaging API bot for Japan/Taiwan/Thailand markets.                        │
│  Zalo: Vietnam-focused messaging platform with Bot API.                                 │
│  Zalo Personal: Zalo personal account via QR code login.                                │
│  Tlon: decentralized messaging on Urbit; install the plugin to enable.                  │
│                                                                                         │
├─────────────────────────────────────────────────────────────────────────────────────────╯
│
◇  Select channel (QuickStart)
│  Feishu (Lark Open Platform)
│
◇  Install Feishu plugin?
│  Download from npm (@openclaw/feishu)
Downloading @openclaw/feishu…
Extracting /var/folders/c2/m4k7fg9d0l7g_9437bdbdmjc0000gn/T/openclaw-npm-pack-EriWOi/openclaw-feishu-2026.2.2.tgz…
Installing to /Users/fomalhaut/.openclaw/extensions/feishu…
14:11:23 [plugins] feishu failed to load from /Users/fomalhaut/.openclaw/extensions/feishu/index.ts: Error: Cannot find module 'zod'
Require stack:
- /Users/fomalhaut/.openclaw/extensions/feishu/src/config-schema.ts
│
◇  Channel setup ───────────────────────────╮
│                                           │
│  feishu does not support onboarding yet.  │
│                                           │
├───────────────────────────────────────────╯
Config warnings:
- plugins.entries.feishu: plugin feishu: duplicate plugin id detected; later plugin may be overridden (/Users/fomalhaut/.nvm/versions/node/v24.13.0/lib/node_modules/openclaw/extensions/feishu/index.ts)
Updated ~/.openclaw/openclaw.json
Workspace OK: ~/.openclaw/workspace
Sessions OK: ~/.openclaw/agents/main/sessions
│
◇  Skills status ────────────╮
│                            │
│  Eligible: 3               │
│  Missing requirements: 47  │
│  Blocked by allowlist: 0   │
│                            │
├────────────────────────────╯
│
◇  Configure skills now? (recommended)
│  Yes
│
◇  Preferred node manager for skill installs
│  npm
│
◇  Install missing skill dependencies
│  🐙 github, 📊 model-usage, 💎 obsidian
│
◇  Install failed: obsidian — Error: Failed to download https://formulae.brew.sh/api/formula.jws.json!
==> Auto-updating Homebrew...
Adjust how often this is run with `$HOMEBREW_AUTO_UPDATE_SECS` or disable with
`$HOMEBREW_NO_AUTO_UPDATE=1`. Hide these hints with `$HOMEBREW_NO_ENV_HINTS=1` (see `man brew`).
Error: Failed to download https://formulae.brew.sh/api/formula.jws.json!
==> Auto-updated Homebrew!
Updated 2 taps (homebrew/core and homebrew/cask).
==> New Formulae
agent-browser: Browser automation CLI for AI agents
cargo-features-manager: TUI like cli tool to manage the features of your rust-project dependencies
codex-acp: Use Codex from ACP-compatible clients such as Zed!
cozyhr: Cozy wrapper around Helm and Flux CD for local development
dbcsr: Distributed Block Compressed Sparse Row matrix library
go-air: Live reload for Go apps
ic-wasm: CLI tool for performing Wasm transformations specific to ICP canisters
icp-cli: Development tool for building and deploying canisters on ICP
jqfmt: Opinionated formatter for jq
litra: Control Logitech Litra lights from the command-line
mac-cleanup-go: TUI macOS cleaner that scans caches/logs and lets you select what to delete
tpix: Simple terminal image viewer using the Kitty graphics protocol
yap: On-device audio transcription using Speech.framework
==> New Casks
clash-mi: Another Mihomo GUI based on Flutter
codex-app: OpenAI's Codex desktop app for managing coding agents
codexbar: Menu bar usage monitor for Codex and Claude
commander: AI agent operator
elegoo-slicer: Open-source slicer for FDM 3D printers
ethui: Ethereum development toolkit with wallet and anvil support
infinidesk: Create multiple virtual desktops, each with unique files, wallpaper and widgets
luxury-yacht: Desktop app for managing Kubernetes clusters
middledrag: Middle-click and middle-drag via three-finger trackpad gestures
plasticity: 3D modeling software for concept artists and designers
posturr: Posture monitoring app
repobar: Menu bar dashboard for GitHub repository health
retrace: Local-first screen recording and search application
seam-app: Productivity-first Dynamic Island for your Notch
tana: Knowledge management workspace with AI-powered outlining
thaw: Menu bar manager
trimmy: Paste-once, run-once clipboard cleaner for terminal snippets
tritium: Integrated drafting environment for legal professionals
yandextelemost: Yandex video calls and meetings platform

==> Tapping yakitrak/yakitrak
Cloning into '/opt/homebrew/Library/Taps/yakitrak/homebrew-yakitrak'...
fatal: unable to access 'https://github.com/yakitrak/homebrew-yakitrak/': Error in the HTTP2 framing layer
Tip: run `openclaw doctor` to review skills + requirements.
Docs: https://docs.openclaw.ai/skills
│
◇  Install failed: github — ✔︎ Bottle Manifest gh (2.86.0)
✔︎ Bottle Manifest gh (2.86.0)
Tip: run `openclaw doctor` to review skills + requirements.
Docs: https://docs.openclaw.ai/skills
│
◇  Install failed: model-usage — missing brew formula
Tip: run `openclaw doctor` to review skills + requirements.
Docs: https://docs.openclaw.ai/skills
│
◇  Set GOOGLE_PLACES_API_KEY for goplaces?
│  No
│
◇  Set GOOGLE_PLACES_API_KEY for local-places?
│  No
│
◇  Set GEMINI_API_KEY for nano-banana-pro?
│  No
│
◇  Set NOTION_API_KEY for notion?
│  No
│
◇  Set OPENAI_API_KEY for openai-image-gen?
│  No
│
◇  Set OPENAI_API_KEY for openai-whisper-api?
│  No
│
◇  Set ELEVENLABS_API_KEY for sag?
│  No
│
◇  Hooks ──────────────────────────────────────────────────────────╮
│                                                                  │
│  Hooks let you automate actions when agent commands are issued.  │
│  Example: Save session context to memory when you issue /new.    │
│                                                                  │
│  Learn more: https://docs.openclaw.ai/hooks                      │
│                                                                  │
├──────────────────────────────────────────────────────────────────╯
│
◇  No Hooks Available ─────────────────────────────────────────────────────╮
│                                                                          │
│  No eligible hooks found. You can configure hooks later in your config.  │
│                                                                          │
├──────────────────────────────────────────────────────────────────────────╯
Config warnings:
- plugins.entries.feishu: plugin feishu: duplicate plugin id detected; later plugin may be overridden (/Users/fomalhaut/.nvm/versions/node/v24.13.0/lib/node_modules/openclaw/extensions/feishu/index.ts)
│
◇  Gateway service runtime ────────────────────────────────────────────╮
│                                                                      │
│  QuickStart uses Node for the Gateway service (stable + supported).  │
│                                                                      │
├──────────────────────────────────────────────────────────────────────╯
│
◓  Installing Gateway service…..
Installed LaunchAgent: /Users/fomalhaut/Library/LaunchAgents/ai.openclaw.gateway.plist
Logs: /Users/fomalhaut/.openclaw/logs/gateway.log
◇  Gateway service installed.
Config warnings:\n- plugins.entries.feishu: plugin feishu: duplicate plugin id detected; later plugin may be overridden (/Users/fomalhaut/.nvm/versions/node/v24.13.0/lib/node_modules/openclaw/extensions/feishu/index.ts)
Config warnings:\n- plugins.entries.feishu: plugin feishu: duplicate plugin id detected; later plugin may be overridden (/Users/fomalhaut/.nvm/versions/node/v24.13.0/lib/node_modules/openclaw/extensions/feishu/index.ts)
Config warnings:\n- plugins.entries.feishu: plugin feishu: duplicate plugin id detected; later plugin may be overridden (/Users/fomalhaut/.nvm/versions/node/v24.13.0/lib/node_modules/openclaw/extensions/feishu/index.ts)
Config warnings:\n- plugins.entries.feishu: plugin feishu: duplicate plugin id detected; later plugin may be overridden (/Users/fomalhaut/.nvm/versions/node/v24.13.0/lib/node_modules/openclaw/extensions/feishu/index.ts)
Config warnings:\n- plugins.entries.feishu: plugin feishu: duplicate plugin id detected; later plugin may be overridden (/Users/fomalhaut/.nvm/versions/node/v24.13.0/lib/node_modules/openclaw/extensions/feishu/index.ts)
Config warnings:\n- plugins.entries.feishu: plugin feishu: duplicate plugin id detected; later plugin may be overridden (/Users/fomalhaut/.nvm/versions/node/v24.13.0/lib/node_modules/openclaw/extensions/feishu/index.ts)
Config warnings:\n- plugins.entries.feishu: plugin feishu: duplicate plugin id detected; later plugin may be overridden (/Users/fomalhaut/.nvm/versions/node/v24.13.0/lib/node_modules/openclaw/extensions/feishu/index.ts)
│
◇  
Agents: main (default)
Heartbeat interval: 30m (main)
Session store (main): /Users/fomalhaut/.openclaw/agents/main/sessions/sessions.json (0 entries)
Missing Control UI assets. Build them with `pnpm ui:build` (auto-installs UI deps).
│
◇  Optional apps ────────────────────────╮
│                                        │
│  Add nodes for extra features:         │
│  - macOS app (system + notifications)  │
│  - iOS app (camera/canvas)             │
│  - Android app (camera/canvas)         │
│                                        │
├────────────────────────────────────────╯
│
◇  Control UI ─────────────────────────────────────────────────────────────────────╮
│                                                                                  │
│  Web UI: http://127.0.0.1:18789/                                                 │
│  Web UI (with token):                                                            │
│  http://127.0.0.1:18789/?token=905dc3ba14e41908bf84a118ec179b1ed220f5460aa48941  │
│  Gateway WS: ws://127.0.0.1:18789                                                │
│  Gateway: reachable                                                              │
│  Docs: https://docs.openclaw.ai/web/control-ui                                   │
│                                                                                  │
├──────────────────────────────────────────────────────────────────────────────────╯
│
◇  Start TUI (best option!) ─────────────────────────────────╮
│                                                            │
│  This is the defining action that makes your agent you.    │
│  Please take your time.                                    │
│  The more you tell it, the better the experience will be.  │
│  We will send: "Wake up, my friend!"                       │
│                                                            │
├────────────────────────────────────────────────────────────╯
│
◇  Token ────────────────────────────────────────────────────────────────────────────────╮
│                                                                                        │
│  Gateway token: shared auth for the Gateway + Control UI.                              │
│  Stored in: ~/.openclaw/openclaw.json (gateway.auth.token) or OPENCLAW_GATEWAY_TOKEN.  │
│  Web UI stores a copy in this browser's localStorage (openclaw.control.settings.v1).   │
│  Get the tokenized link anytime: openclaw dashboard --no-open                          │
│                                                                                        │
├────────────────────────────────────────────────────────────────────────────────────────╯
│
◇  How do you want to hatch your bot?
│  Hatch in TUI (recommended)
Config warnings:\n- plugins.entries.feishu: plugin feishu: duplicate plugin id detected; later plugin may be overridden (/Users/fomalhaut/.nvm/versions/node/v24.13.0/lib/node_modules/openclaw/extensions/feishu/index.ts)
 openclaw tui - ws://127.0.0.1:18789 - agent main - session main                                                        

 session agent:main:main                                                                                                

                                                                                                                        
 Wake up, my friend!                                                                                                    
                                                                                                                        

 (no output)                                                                                                            

                                                                                                                        
 hello                                                                                                                  
                                                                                                                        

 (no output)                                                                                                            

                                                                                                                        
 hello                                                                                                                  
                                                                                                                        

 (no output)                                                                                                            

                                                                                                                        
 hello                                                                                                                  
                                                                                                                        

 (no output)                                                                                                            
 connected | press ctrl+c again to exit                                                                                 
 agent main | session main (openclaw-tui) | minimax/MiniMax-M2.1 | tokens 0/200k (0%)                                   
────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
                                                                                                                        
────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
fomalhaut@LawrencedeMacBook-Air ~ % ls -la > output.txt
fomalhaut@LawrencedeMacBook-Air ~ % ls
Applications	Documents	Library		Music		Pictures
Desktop		Downloads	Movies		output.txt	Public
fomalhaut@LawrencedeMacBook-Air ~ % cd ~/.openclaw/extensions/feishu

fomalhaut@LawrencedeMacBook-Air feishu % pnpm config set registry https://registry.npmmirror.com
zsh: command not found: pnpm
fomalhaut@LawrencedeMacBook-Air feishu % npm config set registry https://registry.npmmirror.com
fomalhaut@LawrencedeMacBook-Air feishu % npm install -g pnpm

added 1 package in 1s

1 package is looking for funding
  run `npm fund` for details
fomalhaut@LawrencedeMacBook-Air feishu % pnpm config set registry https://registry.npmmirror.com
fomalhaut@LawrencedeMacBook-Air feishu % pnpm install
 ERR_PNPM_WORKSPACE_PKG_NOT_FOUND  In : "openclaw@workspace:*" is in the dependencies but no package named "openclaw" is present in the workspace

This error happened while installing a direct dependency of /Users/fomalhaut/.openclaw/extensions/feishu

Packages found in the workspace: 
fomalhaut@LawrencedeMacBook-Air feishu % 
