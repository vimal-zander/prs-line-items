# PRS Line Items

Live site: https://vimal-zander.github.io/prs-line-items/

## Structure

- **`index.html`** — Zander PRS Analyser. Drag-and-drop one or more exported
  `.xlsx` files and it computes stats entirely client-side (no server, no
  upload — parsed in-browser via `xlsx.js`).
- **`archive/`** — static archive of daily PRS line-item exports (raw
  `.xlsx` files + a searchable list view), linked from the analyser page.

## Adding a new day's export

1. Drop the new `prs-line-items-YYYY-MM-DD.xlsx` file into `archive/data/`.
2. Add an entry to `archive/manifest.json`:
   ```json
   { "date": "YYYY-MM-DD", "file": "data/prs-line-items-YYYY-MM-DD.xlsx", "size": <bytes> }
   ```
3. Commit and push:
   ```bash
   git add archive/
   git commit -m "Add export for YYYY-MM-DD"
   git push
   ```

This repo holds no query logic — exports are generated locally by a separate
tool and copied in here manually (or by a future automation step).
