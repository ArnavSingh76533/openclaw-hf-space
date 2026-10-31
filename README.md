---
title: OpenClaw
emoji: 🦞
colorFrom: red
colorTo: yellow
sdk: docker
app_port: 7860
pinned: false
short_description: OpenClaw AI assistant with a Telegram bot that works on HF
---

# OpenClaw on Hugging Face (Telegram works!)

Hugging Face blocks Telegram's Bot API and webhooks. This Space talks to
Telegram over **MTProto** (Telethon) instead, so your bot works on a free Space.
Source: [ArnavSingh76533/openclaw-telethon](https://github.com/ArnavSingh76533/openclaw-telethon).

## Set up

1. **Duplicate this Space** (⋮ menu → *Duplicate this Space*), or create a
   Docker Space and upload this repo's `Dockerfile` and `README.md`.
2. Add these **secrets** in *Settings → Variables and secrets*:

   | Secret | Value |
   |---|---|
   | `OPENCLAW_GATEWAY_TOKEN` | Long random password for the web UI |
   | `TELEGRAM_BOT_TOKEN` | From [@BotFather](https://t.me/BotFather) → `/newbot` |
   | `TELEGRAM_API_ID` | From <https://my.telegram.org> → API development tools |
   | `TELEGRAM_API_HASH` | Same page |
   | `TELEGRAM_ALLOW_FROM` | *(optional)* your numeric user ID from [@userinfobot](https://t.me/userinfobot) |
   | `TILION_LICENSE_KEY` | *(optional)* Fortress v3 browser key |

3. **Keep your data:** *Settings → Storage* → create a private bucket, mount it
   read/write at `/data/openclaw-backups`.
4. Open the Space, enter your gateway token, pick an AI model, message your bot.

Missing a secret? The Space shows a page telling you which one.

Full guide: [deploy/huggingface/README.md](https://github.com/ArnavSingh76533/openclaw-telethon/blob/main/deploy/huggingface/README.md).

> Never put tokens in a committed `.env` file: Space files are public. Use secrets.
> One bot token per Space; two Spaces on one bot fight over the session.
