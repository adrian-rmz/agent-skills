# Vercel Deploy Checklist

## Preflight

- Build passes locally.
- No secrets are required for the static site.
- Domain/canonical target is known.
- User approves Vercel login/network steps.

## CLI Deploy

Default commands:

```bash
npx vercel
npx vercel --prod
```

Recommended answers for a new project:

- Set up and deploy: yes.
- Scope: user's personal or chosen team account.
- Link to existing project: no, unless the user specifies one.
- Project name: business slug.
- Code directory: current project root.
- Modify settings: no, unless build/output differs from defaults.

## Verify Public Deployment

Check:

- `/`
- key service/landing route,
- `/contact` or `/contacto`,
- `/robots.txt`,
- `/sitemap.xml`.

Confirm HTTP 200, images load, and SEO metadata is present.

## Domain Note

If deploying to a temporary Vercel URL while the final custom domain is known, canonical and sitemap may intentionally point to the final domain. If the Vercel URL is the final URL, update canonical, sitemap and robots to use the Vercel domain.
