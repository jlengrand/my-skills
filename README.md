# julien-skills

Julien's personal [Claude Code](https://claude.ai/code) skill plugin — a collection of specialized AI personas for coaching, design, and presentation work.

## Skills

### `nvc-coach`
Non-Violent Communication coach based on Marshall Rosenberg's framework. Describe a situation, paste a message to reformulate, or reflect on a past interaction.

Modes: situation coaching · message reformulation · retrospective reflection · NVC concepts

### `impactful-slides`
McKinsey-style slide coach. Share a deck or slide titles to get a structured review against 7 principles: titles-only test, mental model assessment, bridge analysis, and priority rewrites.

### `logo-designer`
SVG logo designer. Generates multiple logo concepts and layout variations (horizontal, vertical, icon-only) from a description, with color palette recommendations and usage guidelines.

## Installation

```
/install-skills https://github.com/jlengrand/my-skills
```

## Structure

```
skills/
  nvc-coach/skill.md
  impactful-slides/skill.md
  logo-designer/SKILL.md
.claude-plugin/
  plugin.json        # plugin metadata
  README.md          # skills table (used by installer)
```

Each skill is a single markdown file with YAML frontmatter (`name`, `description`) followed by the system-prompt-style instructions.

## Author

Julien Lengrand-Lambert — [github.com/jlengrand](https://github.com/jlengrand)
