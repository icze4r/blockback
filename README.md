# BlockBack 🦋

**A Bluesky tool to find accounts blocking you — filter them, and block them back.**

Made by Durandal

an [ICZE4R](https://bsky.app/profile/iczer.one) joint • [→ Open the tool](https://icze4r.github.io/blockback/)

---

## What it does

Bluesky doesn't show you who's blocking you in the app. BlockBack bridges that gap:

1. Fetches the list of accounts blocking you via [ClearSky](https://clearsky.app) (a public AT Protocol index)
2. Cross-references your own follows and existing blocks
3. Lets you filter — skip people you follow, skip people you've already blocked
4. Lets you select who to block back, individually or in bulk
5. Blocks them directly via the official Bluesky API

Everything runs **entirely in your browser**. No server, no data collection, no tracking.

---

## How to use it

### Online (recommended)

Just open the tool: **[https://icze4r.github.io/blockback/](https://icze4r.github.io/blockback/)**

### Local

Download `index.html` and open it in any browser. Note: when running locally, your browser may block the automatic ClearSky fetch (CORS). If that happens, the tool will detect it and show a manual fallback — just save the JSON pages from ClearSky and upload them.

---

## Setup

**Step 1 — Get an App Password**

Go to [bsky.app/settings/app-passwords](https://bsky.app/settings/app-passwords) and create one. Use this instead of your main password. You can revoke it any time.

**Step 2 — Enter your handle and app password**

The tool authenticates directly with Bluesky's API. Your credentials never leave your browser.

**Step 3 — Let it fetch (or upload manually)**

If running online, it automatically pages through all your ClearSky blocklist pages (100 per page) until it hits the end. If CORS blocks it locally, a fallback appears with direct links to each page — save them as JSON files and upload them all at once.

**Step 4 — Filter and select**

Two toggles let you skip accounts you follow or accounts you've already blocked. You can also select/deselect individually or use the bulk selectors.

**Step 5 — Block**

Hit **Block Selected**. The tool processes them one at a time with a small delay to be rate-limit friendly, and shows a live log of results.

---

## Notes on rate limits

- Bluesky enforces rate limits on write operations. The tool adds a 300ms delay between each block call.
- If you're blocking a very large number of accounts in one session, pace yourself — wait a few minutes between large batches if you hit errors.
- ClearSky is a free community service. The tool pages through it politely with a small delay between requests.

---

## Privacy & security

- **Your credentials** go directly to `bsky.social` — nowhere else.
- **ClearSky data** is fully public (blocks on AT Protocol are public by design — all servers need to know about them to respect them).
- **Nothing is stored** — no localStorage, no cookies, no external analytics.
- The entire tool is a single self-contained HTML file. You can read every line of it.

---

## Running on GitHub Pages

1. Fork or clone this repo
2. Go to **Settings → Pages**
3. Set source to **Deploy from a branch** → `main` → `/ (root)`
4. Save — your instance will be live at `https://yourusername.github.io/blockback/` within a minute

---

## Credits

Built with:
- [Bluesky AT Protocol API](https://docs.bsky.app) — authentication, follows, blocks, block creation
- [ClearSky](https://clearsky.app) / [clearsky.services](https://github.com/ClearskyApp06/clearskyservices) — public blocklist index

---

## License

MIT — do whatever you want with it.
