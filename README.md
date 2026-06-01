# AskLocation

A lightweight [Paper](https://papermc.io/) plugin for Minecraft 1.21+ that lets players request each other's coordinates.
Requests are sent as a roleplay-themed carrier pigeon message with clickable accept / decline buttons powered by MiniMessage.

**Compatible with:** Paper 1.21.1 · 1.21.4 · 1.21.5 · 1.21.6 (API 1.21+)

---

## Features

- `/cord verzoek <player>` - send a coordinate request to another player
- Clickable **[Accept]** / **[Decline]** buttons in the request message
- Rate-limiting: **2 requests per Minecraft day (20 min)** — fully configurable
- Per-player timers - accepting a request never affects the recipient's own limit
- Request timeout: unanswered requests expire automatically (default 60 s)
- Multi-language: **Dutch (nl), English (en), German (de), French (fr)**
- All messages editable via lang YAML files
- No external dependencies - runs on vanilla Paper

---

## Commands

| Command | Description |
|---|---|
| `/cord verzoek <player>` | Send a location request |
| `/cord accept` | Accept an incoming request (shares your XYZ) |
| `/cord weiger` / `/cord decline` | Decline an incoming request |
| `/cord info` | Show plugin info and links |
| `/cord reload` | Reload config + lang files *(requires `asklocation.admin`)* |

**Aliases:** `/asklocation`, `/locatie`, `/coords`, `/loc`

---

## Permissions

| Permission | Default | Description |
|---|---|---|
| `asklocation.use` | everyone | Use the `/cord` command |
| `asklocation.admin` | op | Use `/cord reload` |

---

## Configuration

`plugins/AskLocation/config.yml`

```yaml
# Supported languages (bundled): nl, en, de, fr
language: nl

# Rate-limit window in minutes (one Minecraft day = 20 minutes).
cooldown-minutes: 20

# Maximum number of location requests a player may send within the window above.
max-requests: 2

# How long (seconds) before an unanswered request expires.
timeout-seconds: 60
```

---

## Language files

On first run the plugin saves the bundled lang files to `plugins/AskLocation/lang/`.
You can edit them freely or add new languages — set `language: <code>` in `config.yml` and create the matching `lang/<code>.yml`.

---

## Installation

1. Download the latest release JAR from the [Releases](../../releases) page.
2. Drop it into your server's `plugins/` folder.
3. Restart the server.
4. Edit `plugins/AskLocation/config.yml` to your liking.
5. Run `/cord reload` in-game after any config change (no restart needed).

---

## Requirements

| Requirement | Version |
|---|---|
| Server software | [Paper](https://papermc.io/) 1.21.1 or newer |
| Java | 21 or newer |

> **Note:** Spigot / CraftBukkit are **not** supported. Paper is required for the MiniMessage and Adventure APIs.

---

## Credits

Made by **JoopDev**

- Website: [joopdev.com](https://joopdev.com)
- GitHub: [github.com/joopdev](https://github.com/joopdev)
