# Agent Skills

Reusable, agent-agnostic skills for shipping real projects with repeatable workflows.

This repository is a monorepo for skills that can be read by any capable AI coding agent. Each skill keeps its core process in a universal format, with optional adapters for specific agent runtimes such as Codex.

## Why This Repo Exists

Most useful agent workflows are not just prompts. They are repeatable operating procedures:

- how to discover requirements,
- how to write specs,
- how to use external tools,
- how to implement safely,
- how to validate output,
- and how to deploy or deliver the final work.

`agent-skills` captures those procedures so they can be reused across projects and agents.

## Available Skills

### `business-landing-builder`

Build SEO-first landing pages and small business websites end to end.

Use it for local businesses, service companies, contractors, clinics, agencies, professional firms, and other commercial sites where search visibility and conversion matter.

Workflow covered:

1. Discovery and business validation.
2. SEO keyword and route planning.
3. Written spec and approval gate.
4. UI design with Stitch or equivalent tools.
5. Placeholder-first visual design for images/logos.
6. Next.js implementation.
7. SEO metadata, schema, sitemap, and robots.
8. Iteration and Vercel deployment.

## Install With Codex

Install a specific skill from this GitHub repo:

```bash
npx skills add adrian-rmz/agent-skills --skill business-landing-builder
```

Then invoke it explicitly:

```text
$business-landing-builder build a landing page for a local dental clinic
```

## Universal Skill Structure

Every skill should follow this pattern:

```text
skills/
  skill-name/
    AGENT_SKILL.md
    SKILL.md
    references/
      workflow-or-checklist.md
```

### `AGENT_SKILL.md`

The universal source of truth. It should be usable by any agent, not just Codex.

Put the real workflow here:

- phases,
- gates,
- required outputs,
- validation,
- fallbacks,
- and delivery criteria.

### `SKILL.md`

The Codex adapter. It exists so the skill can be installed and discovered with `npx skills`.

Keep it short. It should point to `AGENT_SKILL.md` and list any Codex-specific notes or optional companion skills.

### `references/`

Phase-specific details that should only be loaded when needed. Keep these files practical and focused.

Examples:

- SEO spec templates,
- deployment checklists,
- UI prompt guides,
- implementation checklists,
- tool-specific workflows.

## Design Principles

- Skills are universal by default.
- Agent-specific behavior belongs in adapters, not the core workflow.
- Do not include client-specific assets, credentials, or private project data.
- Prefer concise, procedural instructions over long explanations.
- Keep every skill self-contained.
- Add references only when they reduce repeated explanation or improve reliability.
- Use approval gates before irreversible actions such as deploys, migrations, or destructive changes.

## Creating A New Skill

Start from the template:

```text
templates/skill/
```

Recommended steps:

1. Copy `templates/skill` to `skills/<new-skill-name>`.
2. Rename the skill in `SKILL.md`.
3. Write the universal process in `AGENT_SKILL.md`.
4. Add only the reference files the skill actually needs.
5. Validate that `SKILL.md` has valid frontmatter:
   - `name`
   - `description`
6. Commit the new skill.

Skill names should use lowercase hyphen-case:

```text
business-landing-builder
seo-audit-workflow
proposal-generator
```

## Compatibility Notes

This repo supports two usage styles:

- Agent-agnostic: point any AI agent at `AGENT_SKILL.md`.
- Codex/npx skills: install via `npx skills add ... --skill <name>`.

Some skills may mention optional tools such as MCP servers, Vercel CLI, or other skills. Those are optional unless the task requires them. If a tool is unavailable, the agent should follow the documented fallback.

## Repository Layout

```text
.
├── README.md
├── LICENSE
├── skills/
│   └── business-landing-builder/
│       ├── AGENT_SKILL.md
│       ├── SKILL.md
│       ├── agents/
│       │   └── openai.yaml
│       └── references/
└── templates/
    └── skill/
```

## License

See [LICENSE](./LICENSE).
