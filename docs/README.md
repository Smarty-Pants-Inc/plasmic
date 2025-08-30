Plasmic Docs Snapshot

This submodule folder contains a snapshot of Plasmic docs under `/learn/`, saved as raw HTML plus minimal metadata.

How to refresh (from parent repo):
- Scrape: `python scripts/scrape_plasmic_docs.py --out docs/plasmic` (stages output under parent `docs/plasmic`)
- Import: `scripts/update_plasmic_reference.sh` (copies into `external/plasmic/docs`, writes MANIFEST, commits)
  - To push the submodule commit to the fork automatically: `PLASMIC_PUSH=1 scripts/update_plasmic_reference.sh`

On-disk layout (within this folder):
- `docs/MANIFEST.json` – list of discovered URLs and counts
- `docs/**/index.html` – saved HTML pages, mirroring path structure
- `docs/**/_source.json` – minimal metadata for the nearest folder

Notes:
- Only HTML is fetched (no assets). Suitable for indexing or conversion to Markdown later.
- Scraper respects `robots.txt` and relies on the public sitemap for stable discovery.
