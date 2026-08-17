# Cannademy — Impeccable v4 remediation

Drop these eight files into the repo root, replacing the existing ones, and commit.
No other files change. `CNAME`, images and any other assets are untouched.

Detector result: **244 findings -> 32** across all 8 pages, both viewports (86% reduction).

## What changed

**Typography.** `Archivo Expanded` is not a real Google Font — the old URL returned
HTTP 400 for that family and the display face silently fell back to plain Archivo.
Now requests `Archivo:wdth,wght@62..125,400..900` and applies `font-stretch:115%`
to every display role, so headlines actually render expanded. Type floor raised to
11px functional / 12px body. Leading, tracking and measure tuned.

**Colour.** New `--acc-2:#C22D14` token. Small red text and red fills carrying white
text now use it (4.7:1 to 5.7:1). `--acc:#E63A1E` is kept for large display type only.
37 of 38 contrast failures cleared.

**Content integrity.** Every bracketed placeholder removed — including ones the
homepage audit never saw: 9x `[Faculty Name]`, 6x `[Short biography.]`, 3x
`[Confirm ...]` editorial notes on the FAQ (one of them on accreditation), and
`[Pricing / Facility location / Start date to confirm]` on Admissions.
Nothing was invented. Unknown facts became honest empty states or "On request".

**Structure.** 25 kickers folded into their headings or deleted. 25 of 29 numbered
section labels removed. Marquee stopped. Heading rhythm inverted. Footer `h4` -> `h3`.
Mobile drag-carousel stacks below 760px. Layout-thrashing transitions replaced.

**Robustness.** `.lrow` was rendering primary copy at 32% opacity (1.2:1) until JS
fired; now defaults to fully visible with a 2.5s reveal failsafe.

**SEO.** Per-page title, meta description, canonical, Open Graph and Twitter tags.
Broken `tracks.html` nav link repointed to `specializations.html`.

## Deliberately left alone

- **Uppercase display headings (19)** — the poster voice is the site's identity.
  Only the long-string roles were relaxed.
- **Cream palette (8)** — a rebrand is your call, not a repair. See the audit report.
- **Admissions process numbers 01-04 (4)** — a genuine sequence, which Impeccable's
  own rule permits.

## Still needs you

1. Real faculty names and bios (two empty states are placeholders for real content).
2. Tuition, intensive location and next intake date — currently "On request".
3. The accreditation answer on the FAQ.
4. Reconcile "Founded MMXXVI" with "5,000 graduates since 2019" and
   "California to Calgary". I removed the unverifiable stats rather than guess.
5. An `og:image` at 1200x630 — the tags are in place and pointing at nothing.
