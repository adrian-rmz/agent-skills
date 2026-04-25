# Business Landing Builder

## Purpose

Build SEO-first landing pages and small business websites through a structured workflow: discovery, keyword strategy, written spec, UI design, implementation, iteration, and deploy.

Use this for local businesses, service companies, professional firms, contractors, clinics, agencies, and other commercial websites where search visibility and conversion matter.

## Core Principles

- Start with business intent, audience, services, geography, trust signals, and conversion goals.
- Treat SEO as product architecture: routes, keywords, headings, metadata, internal links, schema, sitemap, and copy all matter.
- Design before implementation. Get approval on the spec and visual direction before building.
- Use placeholder-first UI mockups when designing with AI UI tools. This prevents fake imagery and makes asset mapping explicit.
- Implement with local structured content and reusable components.
- Validate both the build and the public deployment.

## End-to-End Workflow

### 1. Discovery and Scope

Gather the minimum information needed to avoid rework:

- Business name, industry, services, location, service area, and audience.
- Primary conversion: quote request, call, WhatsApp, booking, form, purchase, or lead magnet.
- SEO priority keywords and geographic targets.
- Existing website, competitors, brand assets, images, logos, testimonials, clients, certifications, and project proof.
- Required pages and explicitly excluded pages.
- Technical constraints: static site, CMS, stack preference, hosting target, domain status, and timeline.

If a brainstorming or planning tool exists, use it before writing specs or code. If not, conduct the same conversation manually.

### 2. SEO and Content Spec

Create a written spec before design or implementation. Use `references/seo-spec-template.md`.

The spec must define:

- Site architecture and URL routes.
- Primary and secondary keywords per page.
- H1 intent, H2 sections, CTAs, internal links, and FAQ opportunities.
- Metadata requirements: title, description, canonical, Open Graph, Twitter metadata.
- Schema requirements: Organization/LocalBusiness, Service, FAQ, BreadcrumbList when relevant.
- Image asset plan: source path, intended placement, and alt text.
- Acceptance criteria: routes, H1 count, metadata, sitemap, robots, responsive layout, and no unsupported claims.

Gate: get user approval before moving to visual design.

### 3. Visual Design With Stitch or Equivalent

If Stitch MCP and a Stitch prompt skill are available, use them. Otherwise use the same workflow with the available design tool. Follow `references/stitch-ui-workflow.md`.

Design requirements:

- Create a design source of truth such as `.stitch/DESIGN.md` with palette, typography, layout rules, component rules, and media policy.
- Generate page mockups for the most important routes first.
- Use image/logo placeholders in the UI mockup, not stock photos or generated AI images.
- Label placeholders with exact local asset paths when assets exist.
- Download or save generated design artifacts and maintain a manifest.
- Validate that the design does not introduce unsupported claims or extra routes.

Gate: get user approval on the visual direction before implementation.

### 4. Implementation

Use `references/next-implementation-checklist.md` for the default Next.js path.

Default implementation approach:

- Build a static Next.js site when no stack exists.
- Store content in structured data files, not duplicated page literals.
- Create reusable layout, hero, service card, project card, FAQ, CTA, footer, image, and SEO helpers.
- Replace design placeholders with approved local images and alt text.
- Generate all approved routes only.
- Add metadata, canonical URLs, Open Graph, JSON-LD, `robots.txt`, and `sitemap.xml`.
- Keep public copy cautious: do not invent project claims, clients, dates, metrics, or certifications.

### 5. Validation and Iteration

Run checks before deploy:

- Production build passes.
- All approved routes respond.
- Each page has exactly one H1.
- Homepage highlights only the approved priority services.
- Service hub links to all service pages.
- Project listing does not create unapproved individual project pages.
- Images load from approved local assets and have descriptive alt text.
- Metadata, canonical, robots, sitemap, and schema are present.
- Desktop and mobile layouts have no overlapping text or broken sections.

Iterate with the user after reviewing the implementation against the approved design.

### 6. Deploy

Use `references/vercel-deploy-checklist.md` for Vercel.

Default deploy path:

- Build locally.
- Deploy with Vercel CLI on the free plan if approved.
- Verify public URLs for home, priority service page, contact page, robots, and sitemap.
- Confirm whether canonical URLs should point to the final custom domain or the Vercel preview domain.

## Fallbacks

- No brainstorming skill: conduct discovery manually and write the spec yourself.
- No Stitch MCP: create a detailed design spec and implementation-ready wireframe descriptions.
- No local images: use placeholders in design and request assets before final implementation.
- No Vercel auth: provide exact CLI steps and stop before deploying.
