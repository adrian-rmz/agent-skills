# Workflow Reference

## Phase Gates

1. Discovery complete: business, audience, services, geography, assets, conversion and constraints are known.
2. SEO spec approved: routes, keywords, page sections, metadata and acceptance criteria are written.
3. UI direction approved: design system, mockups, media policy and key screens are accepted.
4. Implementation complete: routes, components, content, SEO helpers, images and static output are built.
5. Deployment verified: public URL, key routes, robots and sitemap respond.

## Default Artifact Sequence

- `docs/.../<project>-seo-website-design.md` or equivalent spec.
- `.stitch/DESIGN.md` or equivalent design system doc.
- `.stitch/designs/manifest.md` or equivalent design artifact index.
- Next.js app with structured data and reusable components.
- Vercel deployment URL and verification notes.

## Avoid

- Starting implementation from a vague idea.
- Letting UI tools invent photos, clients, metrics, awards, or project facts.
- Creating unapproved routes because they seem useful.
- Deploying before build and SEO route checks pass.
