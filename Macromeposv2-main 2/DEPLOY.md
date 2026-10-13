# Macrome Electronics POS — deploying

Folders: `css/`, `js/` (app code), `icons/`, `screenshots/` (install prompt), `tools/`, `vendor/` (made by tools/vendor.py).

## Every time you change anything
1. Edit the files (usually `js/app.js`, `css/app.css` or `index.html`).
2. Run `python3 tools/stamp.py`  (needs only Python 3). It prints a new version when something changed.
3. Upload the whole folder. Tills update themselves and show the "update available" banner.

Never edit `VERSION` in `sw.js` or the `?v=` links in `index.html` by hand; the stamp tool owns them.

## One-time: make libraries and fonts work offline from the first launch
On a computer with internet: `python3 tools/vendor.py`, then `python3 tools/stamp.py`, then upload including `vendor/`.
Until you do this, Macrome falls back to the CDN copies (cached after first use).

## Multi-shop (Shops A–D)
One install holds all four shops. Products and prices are shared; stock, sales and expenses are kept per shop.
Rename the shops in Settings → Shops. Owners/all-shop managers switch shops from the top bar; cashiers and shop managers
are locked to the shop set on their staff account. Old single-shop backups restore into Shop A.
