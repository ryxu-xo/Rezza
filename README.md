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
| `LAVALINK_HOST` | Lavalink host |
| `LAVALINK_PORT` | Lavalink port |
| `LAVALINK_PASSWORD` | Lavalink password |
| `LAVALINK_SECURE` | `true` / `false` |
| `LAVALINK_NAME` | Node name label |
| `LAVALINK_REST_VERSION` | Lavalink REST version (`v3`/`v4`) |
| `LAVALINK_SEARCH_PLATFORM` | Default search platform (e.g. `ytmsearch`) |
| `LAVALINK_AUTOPLAY` | Enable autoplay when queue ends |

## 🎵 Commands

<details>
   <summary><strong>▶ Music Commands</strong></summary>

   <br />

| Command | Description |
|---|---|
| `/play query:<text>` | Play track/playlist from URL or search query |
| `/search query:<text>` | Join your VC, search top 10 tracks, then pick from dropdown |
| `/nowplaying` | Show current track with live timing info and progress |
| `/queue` | Show current song + queued tracks (paginated) |
| `/seek seconds:<number>` | Jump to a specific position in the current song |
| `/pause` | Pause playback (or resume if already paused) |
| `/resume` | Resume playback if paused |
| `/skip` | Skip currently playing track |
| `/stop` | Stop playback and destroy player |

</details>

<details>
   <summary><strong>▶ Utility Commands</strong></summary>

   <br />

| Command | Description |
|---|---|
| `/ping` | Show bot diagnostics and quick interaction actions |

</details>

<details>
   <summary><strong>▶ Admin Commands</strong></summary>

   <br />

| Command | Description |
|---|---|
| `/stats` | Show developer-only runtime statistics |

</details>

## 🛡️ Notes

- Slash commands are loaded recursively and registered globally on startup.
- Components are routed through dedicated handlers (no bloated `interactionCreate`).
- Components V2 is used for modern panel-style bot responses.
- Logs are written to `logs/` with rotation for production observability.

## 👤 Author

Built by **ryxu-xo**

- GitHub: https://github.com/ryxu-xo
