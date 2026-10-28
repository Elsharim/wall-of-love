# Mo's Wall of Love ❤️

Every Trustpilot, AppSumo and Poppy Wall of Love review that names Mo (Mo / Mohamed / Mohammed / Elsharif),
on one page to send people before their call. Same build as Killian's (killianward8-lab/wall-of-love).

- `index.html` — the page. Reads `reviews.json`.
- `reviews.json` — the reviews. Built by `tools/refresh.py`; don't edit by hand.
- `hidden.json` — review ids to leave off the page, e.g. `["as:385369", "tp:6abad8a4f3d990ed5ccc6c42"]`.
- `tools/trustpilot_seed.json` — the Trustpilot reviews that name Mo, collected 2026-10-28 (all 11 since Aug 2025).

## How it stays up to date

`.github/workflows/refresh.yml` runs every 3 hours and reads AppSumo (deal 255707, public) and
the Poppy Wall of Love feed (`getpoppy.ai/api/proof`, which imports new Trustpilot reviews).
Any review that says Mo gets added, then the page republishes. Reviews are never removed by a
refresh; only `hidden.json` takes one off. A Trustpilot review the Wall never imports goes in
`tools/trustpilot_seed.json` by hand.

## Run it locally

```bash
python3 tools/refresh.py
```
