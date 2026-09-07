# PRS Line Items Archive

Static archive of daily PRS line-item export files, served via GitHub Pages.

Live site: https://vimal-zander.github.io/prs-line-items/

## Adding a new day's export

1. Drop the new `prs-line-items-YYYY-MM-DD.xlsx` file into `data/`.
2. Add an entry to `manifest.json`:
   ```json
   { "date": "YYYY-MM-DD", "file": "data/prs-line-items-YYYY-MM-DD.xlsx", "size": <bytes> }
   ```
3. Commit and push:
   ```bash
   git add data/ manifest.json
   git commit -m "Add export for YYYY-MM-DD"
   git push
   ```

This repo holds no query logic — exports are generated locally by a separate tool
and copied in here manually (or by a future automation step).
