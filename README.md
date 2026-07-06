# odoo-skills

A skills source repo for the [open agent skills ecosystem](https://agentskills.io),
installable with the [`skills` CLI](https://github.com/vercel-labs/skills)
into Claude Code, Cursor, Codex, OpenCode, and 60+ other agents.

## Prerequisites

`npx` ships with Node.js, so there's nothing to pre-install — `npx skills`
downloads and runs the [`skills` CLI](https://github.com/vercel-labs/skills)
on demand.

1. Install Node.js (which includes `npm`/`npx`) if you don't have it:
   ```bash
   # macOS
   brew install node

   # or via nvm (any OS)
   curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.1/install.sh | bash
   nvm install --lts
   ```
2. Verify it's available:
   ```bash
   npx --version
   ```
3. That's it — run any `npx skills ...` command below and it will fetch the
   CLI automatically on first use.

Prefer not to re-fetch it every time? Install it once, globally:
```bash
npm install -g skills
skills add minaonlyone/odoo-skills   # same commands, without the npx prefix
```

## Skills

| Skill | Description |
|-------|--------------|
| [odoo-module-builder](skills/odoo-module-builder/SKILL.md) | Scaffold new Odoo modules the standard way — manifest, models, security, list/search views with filters, cron jobs, server actions, menus — using patterns copied verbatim from the official `odoo/odoo` GitHub repo. |

## Install

```bash
npx skills add minaonlyone/odoo-skills

# install a specific skill only
npx skills add minaonlyone/odoo-skills --skill odoo-module-builder

# install to a specific agent only
npx skills add minaonlyone/odoo-skills -a claude-code
npx skills add minaonlyone/odoo-skills -a antigravity

# install globally (available in every project)
npx skills add minaonlyone/odoo-skills -g
```

List skills in this repo without installing:

```bash
npx skills add minaonlyone/odoo-skills --list
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
