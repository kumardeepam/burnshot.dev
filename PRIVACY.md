# Privacy Policy — Burnshot

_Last updated: June 13, 2026_

## What this extension does

Burnshot uploads images you explicitly paste, drop, or select, and
returns a short-lived URL. The image is deleted after it is fetched once, or
after your chosen burn timer (30 seconds to 5 minutes) expires, whichever
comes first.

## Where images go

Images are uploaded to the extension's hosted backend (a Cloudflare Workers +
R2 service operated by the developer). They are stored **only** until first
fetch or timer expiry — at most 5 minutes — then permanently deleted. There
are no backups, no content logs, and the images are never viewed, analyzed,
sold, or shared.

## Data handled for abuse prevention

- **Install identifier**: a random UUID generated locally on install, sent
  with uploads solely to enforce per-user rate limits. It contains no
  personal information and is not linked to any identity.
- **IP address**: used transiently to enforce per-network rate limits.
  Rate-limit counters are short-lived (minutes to a day) and are then
  deleted. IP addresses are not stored with images or used for any other
  purpose.

## Data stored locally

Settings (burn timer and install identifier) are stored in Chrome's extension
storage (`chrome.storage.sync`), which Chrome may sync across your own
signed-in browsers.

## What is never collected

No analytics, no telemetry, no browsing history, no page content. The
extension only ever transmits images you explicitly provide.

## Changes

Material changes to this policy will be reflected in this document with an
updated date.

## Contact

Questions: [open an issue](https://github.com/kumardeepam/burnshot.dev/issues) on GitHub.
