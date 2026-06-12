# Valley Almanac — Bloomburrow Standard Deck Guide

A mobile-first, dark-themed reference for 14 Standard-legal decks built entirely
from Bloomburrow (BLB): 5 monocolor, 6 dual color, 3 tricolor. Tap any card to
see the full card image (live from Scryfall), with mana costs shown on every row.

Everything runs client-side in a single `index.html` — no build step, no
dependencies, no API keys.

## Publish on GitHub Pages

1. **Create the repo.** On GitHub, click **New repository**. Name it anything
   (e.g. `valley-almanac`). Set it to **Public** (required for free Pages).
   Don’t add any template files. Click **Create repository**.
1. **Upload the files.** On the new repo page, click **uploading an existing
   file** (or **Add file → Upload files**). Drag in `index.html` and
   `README.md`. Commit directly to the `main` branch.

> `index.html` must sit at the **root** of the repo (not inside a folder) —
> GitHub Pages serves it automatically as the homepage.
1. **Enable Pages.** Go to **Settings → Pages** (left sidebar). Under
   **Build and deployment**:
- Source: **Deploy from a branch**
- Branch: **main**, folder: **/ (root)**
- Click **Save**
1. **Open your site.** After ~1–2 minutes the page header shows your URL:
   
   ```
   https://<your-username>.github.io/valley-almanac/
   ```
   
   If it 404s at first, give it another minute and hard-refresh.

## iPhone tip

Open the URL in Safari, tap **Share → Add to Home Screen**. It launches
full-screen with the dark status bar like a native app.

## How it works

- Deck lists are embedded in the page; on first view of each deck the app
  batch-fetches mana costs from Scryfall’s `/cards/collection` endpoint
  (with fuzzy lookup fallback) and caches them for the session.
- Tapping a card loads the full card scan from Scryfall. If the image can’t
  load (e.g. offline), the app renders the card from oracle data instead —
  name, cost, type, rules text, flavor, and P/T in a color-matched frame.
- Heartfire Hero is excluded (banned in Standard, June 2025). All other
  Bloomburrow cards remain Standard-legal.

## Customizing decks

Edit the `DECKS` array near the top of the `<script>` block in `index.html`.
Each card row is `[quantity, "Exact Card Name"]` — add `'basic'` as a third
element for basic lands (skips the mana-cost pip lookup). Commit the change
and Pages redeploys automatically within a minute or two.