# Agent Skills

Reusable, agent-agnostic skills for building real projects with repeatable workflows.

Each skill is designed with two layers:

- `AGENT_SKILL.md`: universal workflow that any capable agent can follow.
- `SKILL.md`: Codex-compatible adapter for `npx skills add` and Codex skill discovery.

## Skills

- `business-landing-builder`: Build SEO-first business landing pages through discovery, SEO specs, Stitch UI design, Next.js implementation, iteration, and Vercel deploy.

## Install With Codex

After publishing this repository to GitHub:

```bash
npx skills add <github-user-or-org>/agent-skills --skill business-landing-builder
```

## Authoring Convention

Keep project-specific assets and private data out of this repository. Skills should describe reusable workflows and include only portable templates, references, and scripts.
