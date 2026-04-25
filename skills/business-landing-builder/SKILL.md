---
name: business-landing-builder
description: Build SEO-first business landing pages for companies and local/service businesses. Use when a user wants to create, redesign, plan, implement, iterate, or deploy a landing page or small business website using discovery, keyword strategy, specs, Stitch UI design, Next.js, and Vercel. Especially relevant when using brainstorming, Stitch MCP/stitch-design, placeholder-first UI design, local image assets, SEO metadata, sitemap/robots, and Vercel CLI deployment.
---

# Business Landing Builder

Use this skill to run a repeatable end-to-end workflow for business landing pages and small SEO websites.

## Start Here

1. Read `AGENT_SKILL.md` first. It is the universal source of truth.
2. Load only the reference file needed for the current phase:
   - SEO/spec planning: `references/seo-spec-template.md`
   - Stitch UI: `references/stitch-ui-workflow.md`
   - Next.js implementation: `references/next-implementation-checklist.md`
   - Vercel deploy: `references/vercel-deploy-checklist.md`
3. If available, use external skills in this order:
   - `brainstorming` for idea validation, scope, tradeoffs, and approved spec.
   - `stitch-design` plus Stitch MCP for `.stitch/DESIGN.md`, prompt enhancement, and high-fidelity UI screens.
4. If an external skill or MCP is unavailable, follow the fallback workflow in `AGENT_SKILL.md` and state the limitation clearly.

## Hard Gates

- Do not implement before the user approves the business/SEO spec.
- Do not treat Stitch mockups as final implementation code.
- In Stitch, use placeholder rectangles for images/logos first unless the user explicitly asks for real image rendering in the mockup.
- In final implementation, replace placeholders with approved local assets and descriptive alt text.
- Before deploy, run a production build and validate key SEO routes.

## Codex Notes

- Prefer repo-local specs under `docs/superpowers/specs/` when using the Superpowers/brainstorming workflow.
- Prefer `.stitch/DESIGN.md` and `.stitch/designs/manifest.md` as the design source of truth after Stitch approval.
- Use `rg` for search, `apply_patch` for manual edits, and Vercel CLI for deploy when the user approves network/auth steps.
