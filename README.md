# odoo-skills

A skills source repo for the [open agent skills ecosystem](https://agentskills.io),
installable with the [`skills` CLI](https://github.com/vercel-labs/skills)
into Claude Code, Cursor, Codex, OpenCode, and 60+ other agents.

## Skills

| Skill | Description |
|-------|--------------|
| [odoo-module-builder](skills/odoo-module-builder/SKILL.md) | Scaffold new Odoo modules the standard way — manifest, models, security, list/search views with filters, cron jobs, server actions, menus — using patterns copied verbatim from the official `odoo/odoo` GitHub repo. |

## Install

```bash
# from GitHub, once pushed (replace <you> with your GitHub username/org)
npx skills add <you>/odoo-skills

# from a local clone/checkout, no GitHub push required
npx skills add /Users/mina/odoo-skills

# install to a specific agent only
npx skills add /Users/mina/odoo-skills -a claude-code

# install globally (available in every project)
npx skills add /Users/mina/odoo-skills -g
```

List skills in this repo without installing:

```bash
npx skills add /Users/mina/odoo-skills --list
```

## Structure

```
odoo-skills/
└── skills/
    └── odoo-module-builder/
        ├── SKILL.md
        ├── README.md
        └── references/
```

Each skill under `skills/<name>/` is a self-contained directory with a
`SKILL.md` (YAML frontmatter: `name`, `description`) at its root — the
format the `skills` CLI and every supported agent understand. Add more
skills by creating additional `skills/<new-skill-name>/SKILL.md` directories.
