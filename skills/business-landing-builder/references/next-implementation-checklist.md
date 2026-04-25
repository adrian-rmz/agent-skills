# Next.js Implementation Checklist

## Default Architecture

Use Next.js App Router for static business websites when no stack exists.

Recommended structure:

- `app/` for routes.
- `components/` for shared UI.
- `data/` for services, projects, clients, assets and page content.
- `lib/seo.*` for metadata and JSON-LD helpers.
- `public/images/...` for local assets.

## Required Behaviors

- Generate only approved routes.
- Keep top navigation simple and aligned to the spec.
- Use structured data to avoid duplicated content.
- Use local images with descriptive alt text.
- Add page-level metadata, canonical, Open Graph and Twitter metadata.
- Add JSON-LD for Organization/LocalBusiness and page-specific Service/FAQ/Breadcrumb data when relevant.
- Add `robots.txt` and `sitemap.xml`.

## Validation Commands

Run the equivalent of:

```bash
npm run build
```

Then inspect exported or rendered HTML for:

- one `<h1>` per page,
- unique titles and descriptions,
- canonical links,
- schema scripts,
- service links,
- sitemap entries,
- image paths and alt text.

## Common Fixes

- If static export fails on `sitemap.xml` or `robots.txt`, mark metadata routes as static where the framework requires it.
- If dynamic route pages export as 404, verify route params handling for the framework version.
- If canonical points to the wrong host, update the site base URL before deploying.
