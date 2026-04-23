# julien-skills

<p align="center">
  <strong>Julien's personal Claude Code skill collection — coaching, slides, design, product validation, and indie founder tools.</strong>
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
| [validate-app-idea](./skills/validate-app-idea) | App idea validator — evaluates whether an idea is worth building using the painkiller/vitamin/candy framework and 3 market validation questions. |
| [slc-scope](./skills/slc-scope) | MVP scoper — cuts feature scope using the SLC (Simple, Lovable, Complete) framework to ship the smallest version that delivers real value. |
| [landing-page-builder](./skills/landing-page-builder) | Landing page coach — builds or reviews high-conversion pages using the three pillars: copywriting, design, and social proof. |
| [app-launch-marketing](./skills/app-launch-marketing) | Launch marketing advisor — creates realistic marketing plans covering organic Reddit, Product Hunt, social content, and paid ads for solo founders. |
| [video-to-skills](./skills/video-to-skills) | Skill extractor — analyzes a video transcript and creates reusable Claude Code skill files from the teachable frameworks it contains. |

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
/plugin install validate-app-idea@julien-skills
/plugin install slc-scope@julien-skills
/plugin install landing-page-builder@julien-skills
/plugin install app-launch-marketing@julien-skills
/plugin install video-to-skills@julien-skills
```

### Universal install (npx)

```bash
# Install all skills
npx skills add jlengrand/my-skills

# Install a specific skill
npx skills add jlengrand/my-skills --skill nvc-coach
npx skills add jlengrand/my-skills --skill impactful-slides
npx skills add jlengrand/my-skills --skill logo-designer
npx skills add jlengrand/my-skills --skill validate-app-idea
npx skills add jlengrand/my-skills --skill slc-scope
npx skills add jlengrand/my-skills --skill landing-page-builder
npx skills add jlengrand/my-skills --skill app-launch-marketing
npx skills add jlengrand/my-skills --skill video-to-skills
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
  validate-app-idea/
    .claude-plugin/plugin.json
    skill.md
  slc-scope/
    .claude-plugin/plugin.json
    skill.md
  landing-page-builder/
    .claude-plugin/plugin.json
    skill.md
  app-launch-marketing/
    .claude-plugin/plugin.json
    skill.md
  video-to-skills/
    skill.md
.claude-plugin/
  marketplace.json
skills.json
```

Each skill is a single markdown file with YAML frontmatter (`name`, `description`) followed by system-prompt-style instructions.

---

## Author

Julien Lengrand-Lambert — [github.com/jlengrand](https://github.com/jlengrand)
