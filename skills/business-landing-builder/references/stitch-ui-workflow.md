# Stitch UI Workflow

## Design System Doc

Create `.stitch/DESIGN.md` before generating screens. Include:

- Brand intent and audience.
- Palette with color roles and hex values.
- Typography direction.
- Component rules for buttons, cards, forms, media slots, CTAs and footer.
- Layout rules and density.
- Strict media policy.

## Placeholder-First Media Policy

In Stitch prompts, use this rule set unless the user asks otherwise:

- Do not use `<img>`.
- Do not use remote image URLs.
- Do not generate AI images.
- Do not use stock photos.
- Use styled placeholder rectangles for all media.
- Label placeholders with exact local paths when known: `IMAGE SLOT: path/to/image.jpg`.
- Use `LOGO SLOT` or `CLIENT LOGO SLOT` for logos.

## Prompt Shape

Before sending a screen-generation or edit prompt to Stitch, run the rough prompt through `enhance-prompt` when available. This is a lightweight refinement step, not a separate approval gate.

The enhanced prompt must preserve:

- The approved SEO/content spec.
- The placeholder-first media policy.
- Approved routes and business facts only.
- Exact local asset path labels when known.

Do not allow prompt enhancement to introduce unsupported claims, extra routes, real image URLs, stock photos, generated images, invented testimonials, invented metrics, or invented credentials.

Use structured prompts:

```markdown
Create a high-fidelity desktop UI screen for [route] for [business].

STYLE:
[Palette, typography, mood, density, component rules]

STRICT MEDIA RULES:
[Placeholder-first rules]

SEO INTENT:
[Keywords and search intent]

PAGE STRUCTURE:
1. Navbar...
2. Hero...
3. Sections...
4. CTA...
5. Footer...
```

## Validation

After generation:

- Download HTML/screenshots if available.
- Check for generated or remote images when placeholder-first was required.
- Confirm placeholders map to real or planned asset paths.
- Confirm the design follows the approved routes and content spec.
- Update a manifest with project ID, screen IDs, files, and notes.
