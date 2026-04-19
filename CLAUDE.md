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

## Footer nav strip

Every Kit 1 / Kit 2 diagnostic page has a `<nav class="kit-nav">` between `</main>` and `<footer>` listing all sibling diagnostics in its kit. When a new diagnostic ships, update every sibling page's nav strip so the new diagnostic renders as a link (or the current page as a `.current` span).

Kit 1 uses a single-row strip. Kit 2 uses a two-row strip with `<br>` splitting after D4.
