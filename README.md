# Bulk OCR Extractor v2.0

## Files
- `index.html` — the browser app.
- `icon.svg` — app icon.
- `Supabase_setup.md` — optional setup for permanent duplicate history.

## Run
Open `index.html` in a modern browser, or deploy the folder to GitHub Pages. Internet access is required for the OCR/export libraries loaded from public CDNs.

## Main features
- OCR extraction of Indian mobile numbers from multiple images.
- Photos processed, numbers found, duplicates, and unique-number statistics.
- Editable contact list.
- Split VCF, CSV, and Excel exports by the maximum contacts per file.
- ZIP contains the split exports (VCF, CSV and Excel); no combined VCF.
- Master file naming/serial settings and per-file edits.
- Optional Supabase duplicate-history sync.

## Important
The cloud history feature is optional. Follow `Supabase_setup.md` and use only your Supabase anon/public key. Never put a `service_role` key in this browser app. The OCR runs locally; if you enable cloud sync, normalized phone numbers are sent to your own Supabase project.
