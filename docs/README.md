Plasmic Docs Snapshot

This folder contains a snapshot of Plasmic docs under `/learn/`, fetched via sitemap and saved as raw HTML for each page. Use the scraper to refresh:

- Fetch: `python scripts/scrape_plasmic_docs.py --out docs/plasmic`
- Dry run: `python scripts/scrape_plasmic_docs.py --out docs/plasmic --dry-run`

Outputs:
- `docs/plasmic/MANIFEST.json` – list of discovered URLs and counts
- `docs/plasmic/**/index.html` – saved HTML pages, mirroring path structure
- `docs/plasmic/**/_source.json` – minimal metadata for the nearest folder

Notes:
- Only HTML is fetched (no assets). Suitable for indexing or later conversion to Markdown.
- Respects `robots.txt` and relies on the public sitemap for stable discovery.
