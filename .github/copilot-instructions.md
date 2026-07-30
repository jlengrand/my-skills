# Copilot instructions for my-skills

## What this repo is

A personal collection of Claude Code **skill** definitions, distributed both as a Claude Code
plugin marketplace and via the universal `npx skills` installer. There is no application code,
build step, or test suite — the repo is pure markdown/JSON configuration. Do not add
build/lint/test tooling; it is not part of this project.

## Repo layout and how the pieces relate

Each skill is defined in **three places that must stay in sync** whenever a skill is added,
removed, or renamed:

1. `skills/<skill-name>/SKILL.md` — the actual system-prompt-style persona/workflow (source of truth for behavior).
2. `skills/<skill-name>/.claude-plugin/plugin.json` — per-skill plugin manifest (name, version, description, keywords, `skills: ["./SKILL.md"]`).
3. `.claude-plugin/marketplace.json` — the marketplace-wide list of plugins; each entry mirrors the name/description/keywords/version from the skill's own `plugin.json`.
4. `skills.json` — a richer per-skill catalog (icon, color, `triggers`, install commands for Claude/other agents, auth requirements) used by the `npx skills` universal installer.
5. `README.md` — human-facing skills table and install instructions (Claude plugin marketplace + `npx skills`).

When adding a new skill, update all of these together — `skills.json` and `marketplace.json`
descriptions/keywords should match what's in the skill's own `plugin.json`, and the `README.md`
table/install snippets need a new row/line per skill.

## SKILL.md conventions

- Every `SKILL.md` in this repo currently uses YAML frontmatter with `name` and `description` fields, followed by a Markdown body:
  ```markdown
  ---
  name: skill-name
  description: "One-sentence description shown in skill picker"
  ---

  # Skill Title
  ...
  ```
- Internal structure follows a consistent pattern across skills — read an existing skill (e.g. `skills/nvc-coach/SKILL.md`) as a template:
  - **Role declaration** — who/what the AI is.
  - **Core framework** — the methodology/principles the skill applies (e.g. NVC's 4 components, McKinsey's 7 slide principles, SLC).
  - **Modes of operation** — numbered/named modes triggered by different user intents.
  - **Output format** — explicit response structure with section headers.
  - **Tone guidelines** — how to communicate, what to avoid.
- `skills/video-to-skills/` additionally has its own `README.md` alongside `SKILL.md`.

## Adding a new skill

1. Create `skills/<skill-name>/SKILL.md` with frontmatter (`name`, `description`) and the standard internal structure above.
2. Create `skills/<skill-name>/.claude-plugin/plugin.json` (copy an existing one, e.g. `skills/nvc-coach/.claude-plugin/plugin.json`, and update name/description/keywords).
3. Add a matching plugin entry to `.claude-plugin/marketplace.json`.
4. Add a matching entry to `skills.json` (icon, color, triggers, install commands, auth block).
5. Add a row to the skills table in `README.md`, plus install-command lines under both the "Claude Code Plugin Marketplace" and "Universal install (npx)" sections.
