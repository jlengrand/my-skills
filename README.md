# julien-skills

<p align="center">
  <strong>Julien's personal Claude Code skill collection — coaching, slides, and design.</strong>
</p>

<p align="center">
  <a href="https://github.com/jlengrand/my-skills"><img src="https://img.shields.io/badge/Claude_Code-Marketplace-orange?style=flat-square&logo=anthropic" alt="Claude Code Marketplace"></a>
  <a href="https://github.com/jlengrand/my-skills/stargazers"><img src="https://img.shields.io/github/stars/jlengrand/my-skills?style=flat-square" alt="GitHub Stars"></a>
  <img src="https://img.shields.io/github/last-commit/jlengrand/my-skills?style=flat-square" alt="Last commit">
  <a href="https://github.com/jlengrand/my-skills/blob/main/LICENSE"><img src="https://img.shields.io/badge/License-MIT-green?style=flat-square" alt="MIT License"></a>
</p>

---

## What are Skills?

Skills are folders of instructions that AI agents load dynamically to improve performance on specialized tasks. Each skill is self-contained with a `SKILL.md` (or `skill.md`) file containing a system-prompt-style persona and workflow.

For more on the standard, see [agentskills.io](https://agentskills.io).

---

## Skills

| Skill | Description |
|-------|-------------|
| [nvc-coach](./skills/nvc-coach) | Non-Violent Communication coach — reformulate messages with empathy, coach on situations, or reflect on past interactions. Based on Marshall Rosenberg's NVC framework. |
| [impactful-slides](./skills/impactful-slides) | McKinsey-style slide coach — structured deck review using 7 principles: titles-only test, mental model assessment, bridge analysis, and priority rewrites. |
| [logo-designer](./skills/logo-designer) | SVG logo designer — generates multiple logo concepts and layout variations (horizontal, vertical, icon-only) with color palette recommendations. |

---

## Installation

### Claude Code Plugin Marketplace

```bash
# Add this marketplace
/plugin marketplace add jlengrand/my-skills

# Install a specific skill
/plugin install nvc-coach@julien-skills
/plugin install impactful-slides@julien-skills
/plugin install logo-designer@julien-skills
```

### Universal install (npx)

```bash
# Install all skills
npx skills add jlengrand/my-skills

# Install a specific skill
npx skills add jlengrand/my-skills --skill nvc-coach
npx skills add jlengrand/my-skills --skill impactful-slides
npx skills add jlengrand/my-skills --skill logo-designer
```

---

## Structure

```
skills/
  nvc-coach/
    .claude-plugin/plugin.json
    skill.md
  impactful-slides/
    .claude-plugin/plugin.json
    skill.md
  logo-designer/
    .claude-plugin/plugin.json
    SKILL.md
.claude-plugin/
  marketplace.json
skills.json
```

Each skill is a single markdown file with YAML frontmatter (`name`, `description`) followed by system-prompt-style instructions.

---

## Author

Julien Lengrand-Lambert — [github.com/jlengrand](https://github.com/jlengrand)
