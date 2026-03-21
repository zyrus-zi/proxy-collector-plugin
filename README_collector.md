# Proxy Collector

[🇷🇺 Русская версия](README.ru.md)

A plugin for [exteraGram](https://exteragram.app) and [AyuGram](https://ayugram.one) that collects proxies from public Telegram channels, chats, posts, and topics — and checks their availability using Telegram's native ping engine.

<div align="center">

[![GitHub](https://img.shields.io/badge/GitHub-zyrus--zi%2Fproxy--collector--plugin-181717?style=for-the-badge&logo=github)](https://github.com/zyrus-zi/proxy-collector-plugin)
[![Releases](https://img.shields.io/github/v/release/zyrus-zi/proxy-collector-plugin?style=for-the-badge&label=Latest%20Release)](https://github.com/zyrus-zi/proxy-collector-plugin/releases)

</div>

---

## Features

- 🔍 Collects proxies from public channels, group chats, specific posts, and forum topics
- ⚡ Checks proxies using the same native method Telegram uses internally
- 🌍 Optional country detection via [ipwho.is](https://ipwho.is)
- 📅 Configurable search depth: 1 day to all time, or a custom number of days
- 📁 Load proxies from GitHub files (multiple links supported)
- 📂 Import proxies from a TXT file on the device — via the built-in browser (file manager)
- 🗂 History of the last 10 collection runs, saved on disk
- 🌐 Results viewable as a formatted HTML page in the built-in browser — with filters, export to TG, and send to Proxy Vault
- 📋 Copy all proxy links to clipboard
- 🛑 Cancel button during collection and checking
- 📌 Quick access button in the side drawer menu

---

## Two modes

The plugin has two independent modes, each with its own sources, settings, and history:

| Mode | Description |
|---|---|
| **Regular proxies** | Standard proxies for everyday use |
| **Proxies with whitelist bypass** | Proxies that work when content filtering (whitelist) is active |

> ⚠️ Whitelist bypass proxies must be checked **only with whitelists enabled**. Checking without active whitelists may produce incorrect results — working proxies may appear dead.

---

## Supported Source Formats

| Format | Example |
|---|---|
| Channel | `t.me/proxy_channel` |
| Group chat | `t.me/GoodbyeWLChat` |
| Specific post | `t.me/channel/910` |
| Forum topic | `t.me/LowiKForum/10805` |
| Post in a topic | `t.me/LowiKForum/10805/32871` |
| GitHub file | `github.com/user/repo/blob/main/proxies.txt` |
| TXT file on device | Selected via built-in browser |

---

## Supported Proxy Formats

- `https://t.me/proxy?server=...&port=...&secret=...` (MTProto)
- `tg://proxy?server=...&port=...&secret=...` (MTProto, converted automatically)
- `https://t.me/socks?server=...&port=...&user=...&pass=...` (SOCKS5)
- `tg://socks?server=...&port=...&user=...&pass=...` (SOCKS5, converted automatically)
- `Server: ... Port: ... Secret: ...` (text block)
- `IP:PORT:USER:PASS`
- `USER:PASS@IP:PORT`
- `IP:PORT`

> ⚠️ **Important:** To collect proxies from Telegram sources, you must be **subscribed** to the channels, chats, or topics you use as sources.

VPN configs (`ss://`, `vless://`, `vmess://`, `trojan://`, etc.) are automatically filtered out.

GitHub and TXT files support only `t.me/proxy?` and `t.me/socks?` links (including `tg://` variants).

---

## Importing from a file on the device

Starting from version 2.2.0, TXT file import works via the built-in browser:

1. Enable the **"TXT file from device"** toggle in the mode settings
2. Tap **"Open file picker in browser"** — a page opens in the TG browser
3. Tap **"Choose file"** → select one or more TXT files via the file manager
4. Tap **"Send"** — proxies are passed to the plugin
5. Return to the plugin and tap **"Start collection and check"**

> This method was introduced because newer versions of exteraGram and AyuGram no longer grant the `MANAGE_EXTERNAL_STORAGE` permission, making direct file access by path unavailable.

---

## Results page (browser)

After collection, results open in the built-in browser with:

- **Ping filter** — show only proxies below a specified latency
- **📲 Add to Telegram** — add proxies to TG with optional ping limit
- **🗄 Send to Proxy Vault** — send to an existing or new tab in [Proxy Vault](https://github.com/zyrus-zi/proxy-vault-plugin)
- **⭐ Send to Saved Messages** — as text or TXT file
- **📨 Share via Telegram** — open chat selector dialog
- **📋 Copy all links** — copy to clipboard
- **📄 Share TXT file** — send file via Telegram

---

## Installation

1. Download the latest `.plugin` file from [Releases](../../releases)
2. Open exteraGram or AyuGram
3. Go to **Settings → Plugins → Install from file**
4. Select the downloaded file and enable the plugin

---

## Requirements

- exteraGram `11.12.0`+ or AyuGram (full version only — Lite does not support plugins)

---

## Settings

Each mode has its own independent settings:

| Setting | Description | Default |
|---|---|---|
| Telegram sources | Links to channels, chats, posts or topics | — |
| Search depth | How far back to look for posts | 7 days |
| GitHub files | Links to GitHub files with proxies (one per line) | — |
| TXT file from device | Import via browser | — |
| Check timeout | Max wait time per proxy (sec) | 5 |
| Detect country | Extra request to ipwho.is per live proxy | ✅ On |

---

## Compatibility

| App | Supported |
|---|---|
| exteraGram | ✅ |
| AyuGram | ✅ |

---

## Related plugins

- [Proxy Vault](https://github.com/zyrus-zi/proxy-vault-plugin) — store and manage proxies in named tabs

---

## Author

[@zyrus-zi](https://github.com/zyrus-zi) · [GitHub](https://github.com/zyrus-zi/proxy-collector-plugin)

---

## License

[MIT](LICENSE)
