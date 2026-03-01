<p align="center">
   <img src="https://capsule-render.vercel.app/api?type=waving&height=230&color=5865F2&text=Rezza©&fontColor=ffffff&fontSize=56&desc=Production-ready%20Discord%20Music%20Bot&descAlignY=64" alt="Rezza Banner" />
</p>

<p align="center">
   <img src="https://img.shields.io/badge/Node.js-20%2B-339933?logo=node.js&logoColor=white" alt="Node 20+" />
   <img src="https://img.shields.io/badge/discord.js-latest-5865F2?logo=discord&logoColor=white" alt="discord.js latest" />
   <img src="https://img.shields.io/badge/Modules-ESM-f59e0b" alt="ES Modules" />
   <img src="https://img.shields.io/badge/Riffy-Lavalink-blue" alt="Riffy Lavalink" />
   <img src="https://img.shields.io/badge/License-MIT-22c55e" alt="MIT" />
</p>

<p align="center">
   <a href="https://discord.com/oauth2/authorize?client_id=1477343460238561441&permissions=8&scope=bot%20applications.commands">
      <img src="https://img.shields.io/badge/Invite%20Rezza-5865F2?logo=discord&logoColor=white&style=for-the-badge" alt="Invite Rezza" />
   </a>
   <a href="https://github.com/ryxu-xo/Rezza#-quick-start">
      <img src="https://img.shields.io/badge/Docs-111827?logo=readthedocs&logoColor=white&style=for-the-badge" alt="Docs" />
   </a>
   <a href="https://discord.gg">
      <img src="https://img.shields.io/badge/Support%20Server-4f46e5?logo=discord&logoColor=white&style=for-the-badge" alt="Support Server" />
   </a>
</p>

<p align="center">
   Scalable Discord bot architecture with dynamic handlers, Components V2 UI, and Lavalink-powered music.
</p>

## ✨ Features

- Handler-based architecture with clean separation (`core`, `commands`, `events`, `components`, `utils`).
- Global slash command loader (recursive) with automatic registration.
- Components V2 message system (containers, sections, separators) for modern bot UI.
- Modular button/select/modal component routing using `customId` conventions.
- Integrated music system with `riffy` + Lavalink (`/play`, `/queue`, `/skip`, `/stop`).
- Structured logging with `pino` + pretty console output + rotating file logs.
- Process-level crash safety with global `unhandledRejection` / `uncaughtException` handlers.

## 🧱 Project Structure

```text
src/
├─ core/
│  ├─ BotClient.mjs
│  ├─ interactionRouter.mjs
│  ├─ loaders/
│  └─ music/
│     ├─ setupRiffy.mjs
│     └─ events/
├─ commands/
│  ├─ admin/
│  ├─ music/
│  └─ utility/
├─ components/
│  ├─ buttons/
│  ├─ select-menus/
│  └─ modals/
├─ config/
│  ├─ config.mjs
│  └─ theme/
│     ├─ colors.mjs
│     └─ emojis.mjs
└─ utils/
```

## 🚀 Quick Start

1. Install dependencies:

```bash
npm install
```

2. Create environment file:

```bash
copy .env.example .env
```

3. Fill your `.env` values (`DISCORD_TOKEN`, `DISCORD_CLIENT_ID`, Lavalink values).

4. Start the bot:

```bash
npm start
```

For development mode:

```bash
npm run dev
```

## ⚙️ Environment Variables

| Variable | Description |
|---|---|
| `DISCORD_TOKEN` | Discord bot token |
| `DISCORD_CLIENT_ID` | Discord application client ID |
| `DEVELOPER_IDS` | Comma-separated developer user IDs |
| `NODE_ENV` | `development` or `production` |
| `LOG_LEVEL` | Logger level (`debug`, `info`, etc.) |
| `REZZA_DOCS_URL` | Help panel Docs link button URL (optional) |
| `REZZA_INVITE_URL` | Help panel Invite link button URL (optional) |
| `REZZA_SUPPORT_URL` | Help panel Support link button URL (optional) |
| `LAVALINK_HOST` | Lavalink host |
| `LAVALINK_PORT` | Lavalink port |
| `LAVALINK_PASSWORD` | Lavalink password |
| `LAVALINK_SECURE` | `true` / `false` |
| `LAVALINK_NAME` | Node name label |
| `LAVALINK_REST_VERSION` | Lavalink REST version (`v3`/`v4`) |
| `LAVALINK_SEARCH_PLATFORM` | Default search platform (e.g. `ytmsearch`) |
| `LAVALINK_AUTOPLAY` | Enable autoplay when queue ends |

## 🎵 Commands

<!-- COMMANDS:START -->
<details>
  <summary><strong>▶ Music Commands</strong></summary>

  <br />

| Command | Description |
|---|---|
| `/filters preset:<text>` | Apply an audio filter preset to playback. |
| `/loop mode:<text>` | Set loop mode for the current player. |
| `/lyrics mode:<text>` | Show song lyrics from LRCLIB in synced or static mode. |
| `/move from:<number> to:<number>` | Move a queued track to a new position. |
| `/nowplaying` | Show the currently playing track with live timing info. |
| `/pause` | Pause playback, or resume if already paused. |
| `/play query:<text>` | Play a track or playlist from a search query or URL. |
| `/queue` | Show current song and queued tracks (10 per page). |
| `/remove position:<number>` | Remove a queued track by position. |
| `/resume` | Resume playback if the current song is paused. |
| `/search query:<text>` | Search tracks and pick one from a dropdown menu. |
| `/seek seconds:<number>` | Jump to a specific time in the current song (in seconds). |
| `/shuffle` | Shuffle all queued tracks. |
| `/skip` | Skip the currently playing track. |
| `/stop` | Stop playback, clear queue, and disconnect from voice. |
| `/volume level:<number>` | Set playback volume (0-200). |

</details>

<details>
  <summary><strong>▶ Utility Commands</strong></summary>

  <br />

| Command | Description |
|---|---|
| `/help category:<text>` | Show interactive help center with command categories. |
| `/ping` | Show bot latency and live health diagnostics. |

</details>

<details>
  <summary><strong>▶ Admin Commands</strong></summary>

  <br />

| Command | Description |
|---|---|
| `/stats` | Developer-only operational statistics command. |

</details>
<!-- COMMANDS:END -->

## 🛡️ Notes

- Slash commands are loaded recursively and registered globally on startup.
- Components are routed through dedicated handlers (no bloated `interactionCreate`).
- Components V2 is used for modern panel-style bot responses.
- Logs are written to `logs/` with rotation for production observability.

## 👤 Author

Built by **ryxu-xo**

- GitHub: https://github.com/ryxu-xo
