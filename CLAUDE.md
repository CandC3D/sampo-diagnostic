# Project conventions — Sampo / Virtual Intelligence / Diagnostic projects

These conventions apply to all projects under:
- `candc3d/sampo-diagnostic*` (landing page + Kit 1 / Kit 2 / future kit diagnostic pages)
- `candc3d/sampo-framework`
- `candc3d/vi-framework`

## Required files on every deployed page repo

Every diagnostic / Sampo / VI page repo must include at minimum:

1. **`index.html`** — the page itself
2. **`google5315ac0eabfa5ec3.html`** — Google Search Console verification file
   - Source: `C:\Users\chorr\Documents\sampo-diagnostic\google5315ac0eabfa5ec3.html`
   - Copy verbatim; same file across all repos
3. **`sitemap.xml`** — single-URL sitemap pointing to the repo's GitHub Pages URL
   - Format:
     ```xml
     <?xml version="1.0" encoding="UTF-8"?>
     <urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
       <url>
         <loc>https://candc3d.github.io/<repo-name>/</loc>
         <lastmod>YYYY-MM-DD</lastmod>
       </url>
     </urlset>
     ```

When creating a new page repo, add all three from the start of the initial commit, not as a follow-up.

## Landing page updates

When a new diagnostic ships, update `candc3d/sampo-diagnostic/index.html` to mark the corresponding `li.dim-item` as `published` and wrap its label in an anchor to the new repo's GitHub Pages URL.

## Prompts are never drafted

**Never draft diagnostic prompt text.** Option A / B / C prompts are carefully constructed and validated before the page is built. If the user has not provided a prompt source file (typically `kitNdX_prompt_version_A/B/C...md`), pause and ask — do not synthesize, summarize, or paraphrase from build specs or other sources.

## Web graphics

Each kit page ships with:
- `favicon.svg`, `favicon-32x32.png`, `apple-touch-icon.png` (shared across all pages — sourced from `C:\Users\chorr\Downloads\sampo-web-graphics\sampo-assets\`)
- `og_<dx>.png` + `og_square_<dx>.png` (per-kit, 1200×630 + square) — sourced from `sampo-web-graphics\sampo-assets\kit1_<dx>\` or `kit2_<dx>\`
- `og:image` and `twitter:image` meta tags pointing to the repo's own `og_<dx>.png`

The main `sampo-diagnostic` landing page uses generic graphics from `C:\Users\chorr\Downloads\sampo-generic\` (`og_image.png`, `og_square.png`, `github_social_preview.png`, `substack_header.png`).

## Inline SVG illustrations

Every diagnostic page carries a Three Audit Modes diagram inlined into its `<div class="figure-block">`. Use the Kit 2 D4 (Autonomy Erosion) SVG as the structural template. Generator script pattern: `C:\Users\chorr\build-svgs.mjs`.

Required attributes on the root `<svg>` tag:
- `viewBox="0 0 680 <height>"` — height scales with row count of validation table
- `width="680" height="<height>"`
- `role="img" aria-label="Three Audit Modes diagram — <Dimension Name>"`
- Inline style: `display: block; max-width: 100%; height: auto; margin: 0 auto; border-radius: var(--radius-md); border: 0.5px solid var(--border-light); color-scheme: light;`

Color palette inside SVG (don't rely on CSS vars — SVG is self-contained):
- Background: `rgb(245,240,232)` (cream)
- Ink: `rgb(44,44,42)` (dark)
- Muted: `rgb(140,138,132)` / `rgb(180,178,172)`
- Option A / Steel: `rgb(123,143,161)`
- Option B / Olive: `rgb(101,163,13)`
- Option C / Pumpkin: `rgb(255,122,5)`

## Footer nav strip

Every Kit 1 / Kit 2 diagnostic page has a `<nav class="kit-nav">` between `</main>` and `<footer>` listing all sibling diagnostics in its kit. When a new diagnostic ships, update every sibling page's nav strip so the new diagnostic renders as a link (or the current page as a `.current` span).

Kit 1 uses a single-row strip. Kit 2 uses a two-row strip with `<br>` splitting after D4.
