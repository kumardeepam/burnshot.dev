# Burnshot

**Screenshots your AI agent can actually reach.**

A Chrome extension that uploads a screenshot and returns a self-destructing URL — so AI coding agents running in remote SSH terminals can see your screen.

[![Install](https://img.shields.io/badge/Chrome%20Web%20Store-Install%20Free-f6821f?style=flat-square&logo=google-chrome&logoColor=white)](https://chromewebstore.google.com/detail/burnshot/kfcemebkapeanfhfjbfenhdpionmhmjn)
[![Website](https://img.shields.io/badge/Website-burnshot.dev-1a1a1a?style=flat-square)](https://chromewebstore.google.com/detail/burnshot/kfcemebkapeanfhfjbfenhdpionmhmjn)

---

## The problem

AI coding agents like Claude Code run in SSH sessions — they cannot access your local clipboard, screenshots, or filesystem. You have a bug on screen but no way to show your agent.

## The solution

1. **Drop or paste** a screenshot into the Burnshot side panel
2. **Copy the URL** — it lands in your clipboard automatically
3. **Paste into your agent** — Claude Code, Cursor, any SSH terminal
4. **It burns** — deleted after the first fetch, or when your timer runs out

No sign-up. No servers to run. No permanent storage.

---

## How it works

- Screenshots are uploaded to a Cloudflare R2 bucket via a hosted backend at `burnshot.dev`
- Each image gets a random 32-character hex ID — unguessable
- On the first `GET /i/<id>` the image is served **and immediately deleted**
- If never fetched, it is deleted when the burn timer (30 seconds to 5 minutes) expires
- A random UUID is generated on install to enforce per-user rate limits — no account required

## Abuse limits

| Limit | Value |
|---|---|
| Max image size | 5 MB |
| Formats accepted | PNG, JPEG, GIF, WebP |
| Uploads per minute (per install) | 10 |
| Uploads per day (per install) | 100 |
| Uploads per minute (per IP) | 20 |
| Uploads per day (global) | 5,000 |

## Privacy

Images are never viewed, analyzed, or shared. Full details: [burnshot.dev/privacy.html](https://burnshot.dev/privacy.html)

## Issues and feedback

Found a bug or have a feature idea? [Open an issue](https://github.com/kumardeepam/burnshot.dev/issues) — every report is read.
