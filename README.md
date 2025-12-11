# dbot-domain-recon

Welcome to **dbot-domain-recon**, a Discord bot designed for domain investors and enthusiasts. This bot provides fast, reliable domain information including ownership, registrar, RDAP details. Many domainers face fragmented tools for domain data; this bot centralizes it into a single, stateless solution.

## Overview

**dbot-domain-recon** is open-source, modular, and stateless. It can be hosted on Cloudflare Workers or any stateless environment. The bot interacts via Discord slash commands and provides instant domain information for any TLD. The structure allows developers to add or customize commands easily.

## Features

* Fetch RDAP information for domains
* Instant interaction through Discord commands
* Stateless design with optional Cloudflare hosting
* Open-source and fully modular

## Folder Structure

```
/sample-app
│
├─ /src
│   ├─ server.ts        # Cloudflare Worker entry
│   ├─ commands.js      # Discord commands
│   └─ helpers/
│       ├─ rdap.js      # RDAP lookup helpers
│       └─ whois.js     # WHOIS fallback helpers
│
├─ example.dev.vars      # Example environment variables
├─ package.json
├─ tsconfig.json         # TypeScript configuration (if used)
└─ README.md
```

* **Development:** Use local testing to validate commands and modules.
* **Production:** Deploy to Cloudflare Workers or another stateless environment.

## Configuration

Before running the bot, configure your Discord application:

* Bot with **Send Messages** and **Use Slash Command** permissions
* Scope: **applications.commands**
* Configure OAuth2 URL to install your bot in a server

Set environment variables in `example.dev.vars` with your real values:

```
DISCORD_TOKEN=your_bot_token
DISCORD_PUBLIC_KEY=your_public_key
DISCORD_APPLICATION_ID=your_app_id
```

## Installation

Clone the repository and install dependencies:

```bash
cd sample-app
npm install
```

Register Discord Slash Commands (Dev)

```bash
npm run register
```

Watch for success logs — if registration fails, debug the errors first. This step ensures all slash commands are live in your server before running the bot.

## Running the Bot

**Development:**

```bash
npm run dev
```

**Production:**

```bash
npm run prod
```

* Set the interaction endpoint in your Discord application settings.
* Once the Discord ping succeeds, your bot will be online.

## Hosted Option

If you prefer not to host the bot yourself, you can invite the fully-hosted bot for free:

[Invite dbot-domain-recon](https://discord.com/oauth2/authorize?client_id=YOUR_CLIENT_ID&scope=bot+applications.commands)

Want to join the domainer community? Here you go: [discord.gg/domainers](https://discord.gg/domainers)

## References

* Discord Developer Documentation: [https://discord.com/developers/docs](https://discord.com/developers/docs)
* Cloudflare Workers Documentation: [https://developers.cloudflare.com/workers/](https://developers.cloudflare.com/workers/)

**dbot-domain-recon** simplifies domain information retrieval for domainers, investors, and developers, all through Discord, open-source, and stateless hosting.
