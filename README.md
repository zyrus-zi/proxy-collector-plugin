# Proxy Collector

[🇷🇺 Русская версия](README.ru.md)

A plugin for [exteraGram](https://exteragram.app) and [AyuGram](https://ayugram.one) that collects proxies from public Telegram channels, chats, posts, and topics — and checks their availability using Telegram's native ping engine.

---

## Features

- 🔍 Collects proxies from public channels, group chats, specific posts, and forum topics
- ⚡ Checks proxies using the same native method Telegram uses internally
- 🌍 Optional country detection via [ipwho.is](https://ipwho.is)
- 📅 Configurable search depth: 1 day to all time, or a custom number of days
- 📁 Load proxies from GitHub files (one link per line)
- 🗂 History of the last 10 collection runs, saved on disk
- 🌐 Results viewable as a formatted HTML page in the built-in browser
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
| Specific post | `t.me/channel/123` |
| Forum topic | `t.me/LowiKForum/10805` |
| GitHub file | `github.com/user/repo/blob/main/proxies.txt` |

---

## Supported Proxy Formats

- `https://t.me/proxy?server=...&port=...&secret=...` (MTProto)
- `https://t.me/socks?server=...&port=...&user=...&pass=...` (SOCKS5)
- `Server: ... Port: ... Secret: ...` (text block)
- `IP:PORT:USER:PASS`
- `USER:PASS@IP:PORT`
- `IP:PORT`

> ⚠️ **Important:** To collect proxies from Telegram sources, you must be **subscribed** to the channels, chats, or topics you use as sources. Correct operation without a subscription is not guaranteed.

VPN configs (`ss://`, `vless://`, `vmess://`, `trojan://`, etc.) are automatically filtered out.

GitHub files support only `t.me/proxy?` and `t.me/socks?` links.

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
| Check timeout | Max wait time per proxy (sec) | 5 |
| Detect country | Extra request to ipwho.is per live proxy | ✅ On |

---

## Compatibility

| App | Supported |
|---|---|
| exteraGram | ✅ |
| AyuGram | ✅ |

---

## Author

[@zyrus-zi](https://github.com/zyrus-zi)

---

## License

[MIT](LICENSE)
