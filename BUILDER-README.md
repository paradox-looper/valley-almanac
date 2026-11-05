# Deck Builder: `builder.html`

The third page of Valley Almanac, next to `index.html` (Decks) and `ev.html` (EV Engine).

## Upload
1. In the repo, go to **Add file → Upload files**.
2. Drag in `builder.html`. Put it in the repo root, next to `index.html`. If an older `builder.html` is there, this one replaces it.
3. Commit. GitHub Pages redeploys in about 1–2 minutes. Then open `https://<you>.github.io/<repo>/builder.html` in Safari.

`builder.html` is self-contained: all of its code is inside the file, so no `data/` or `js/` folders are needed.
If you uploaded `data/` and `js/` folders from the first version, delete them. Nothing uses them anymore.

To get a Builder tab on the other two pages, add this line inside the `<nav class="nav">` block in both `index.html` and `ev.html`:
```html
<a href="builder.html">Builder</a>
```

## Must run from GitHub Pages
The page pulls cards from Scryfall. In-app file previews and downloaded copies block those requests, and the page shows a red "Can't reach the card database" message when that happens.

## Flow
1. **Setup**: format, budget, speed, colors (colors are optional).
2. **Strategy**: up to 10 drivers (themes ★ primary, win mode, tribe, setting, era). Then tap **Build deck**.
3. **Review**: projected win %, score breakdown, mana curve, and the card list. Tap a card for its text, price and buy links. Tap **0/4** to mark how many you own. You can swap a card for the next-best one.
4. **Shop**: missing cards, cheapest printing for each, TCGplayer Mass Entry, copy / CSV / .txt export, collection import.

The **Theme guide** is for reference only. Browsing it doesn't change your build. Only the "+ Add to build" buttons do.
**My builds** shows every build. They autosave in this browser, and you can resume, copy or delete them.

## Win % = inferred
No public source publishes win rates for a custom deck. The number is a modeled strength index, weighted by quality 30% · synergy 25% · curve 15% · interaction 12% · mana 10% · win density 8%. It is mapped to a 1v1 match (baseline 50%) or a 4-player Commander pod (baseline 25%).
