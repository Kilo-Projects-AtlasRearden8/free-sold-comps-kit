# STATUS

Free Sold-Comps Kit — Asdale Dynamics, LLC
Working directory: `/workspace/kilo-lab/free-sold-comps-kit`
Git commit: `7f73904` (branch `master`, no remote, not pushed)

## What was built

A free, printable, no-account resale price-research kit with four self-contained browser tools plus Markdown sources:

| Tool | HTML file | Markdown source | What it does |
|------|-----------|-----------------|--------------|
| Sold-Comps Worksheet | `sold-comps.html` | `docs/sold-comps.md` | Record sold comparable listings; auto-computes count, average, median, low, high, and a suggested list price; CSV export |
| Condition-Grading Guide | `condition-grading.html` | `docs/condition-grading.md` | Plain-English condition tiers (Like New to Poor) with pricing expectations, category notes (books/electronics/clothing), and a disclosure checklist |
| Fee Estimator | `fee-estimator.html` | `docs/fee-estimator.md` | Estimates eBay/Amazon fees, shipping, and item cost; shows net profit, profit margin, break-even price, and target-margin prices; eBay/Amazon/AM-media presets plus custom rate |
| Price-Tracking Log | `price-tracking.html` | `docs/price-tracking.md` | Log listed/sold items; auto-computes sell-through rate, average sale price, average days listed; CSV export |

Also included:
- `index.html` — landing page linking all tools and Markdown sources
- `README.md` — overview, how-to-use, about Asdale Dynamics, LLC, license, disclaimer
- `LICENSE` — MIT, copyright line exactly `Copyright (c) 2026 Asdale Dynamics, LLC`
- `STATUS.md` — this file

All tools are single self-contained HTML files (inline CSS/JS), work entirely offline, store nothing, and send nothing. Print styles (`@media print`) hide controls/buttons for a clean paper copy via `Ctrl+P`/`Cmd+P`.

## Credit

Built and published by **Asdale Dynamics, LLC** (Indiana). Credited in `README.md`, `index.html`, every HTML tool header, and the `LICENSE` copyright line. Founder: Dylan Asdale, registered nurse turned AI author (*The Massive AI Manual*, `dylanasdale.github.io`).

## How to run

No install, no account, no build step:
1. Open any `.html` file in a browser (Chrome, Firefox, Safari, Edge).
2. Fill in fields; totals compute automatically.
3. Press `Ctrl+P` / `Cmd+P` to print (controls hidden in print output).
4. Optionally open the matching `docs/*.md` for a human-readable source, or click Export CSV to download your data.

## Verification results

- HTML well-formedness (Python `html.parser`): all 5 HTML files pass, no unclosed/mismatched tags.
- Headless Chrome render (`--dump-dom`): all 5 HTML files load and render without errors.
- Calculation spot-check (Node, replicating in-page logic):
  - Sold-comps: comps [299.99, 249.99, 349.99] → count 3, average $299.99, median $299.99, low $249.99, high $349.99.
  - Fee estimator (eBay preset, sale $29.99, ship charged $5.00, ship cost $4.50, item cost $8.00): fees $4.27, net profit $18.22, margin 52.1%, break-even $8.99.
  - Price-tracking: 3 listed, 2 sold → sell-through 67%, average sale $174.75, average days listed 9.
- No secrets, API keys, or personal data in any file. No `.github/workflows` present. No remote repository created; nothing pushed or published.

## Known gaps

- Fee rates are typical estimates (eBay 13.25% + $0.30/order, Amazon 15% standard, Amazon media 15% + $1.80 closing). They are hardcoded and not verified against live fee schedules; users must check current eBay/Amazon rates before pricing (noted in tool + disclaimer).
- Data lives only in the browser session; no persistent storage, sync, or export beyond manual CSV download.
- Estimator is simplified: excludes FBA fulfillment fees, eBay optional upgrades, returns, and sales tax.
- Not financial or tax advice; educational use only.
- Markdown docs are source mirrors, not rendered to HTML automatically (kept intentionally simple, no build step).
