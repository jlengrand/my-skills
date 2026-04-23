# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Repo Is

A personal collection of Claude Code skill definitions. Each skill lives in its own directory as a single markdown file that defines system-prompt-style instructions for a specialized AI persona or workflow.

## Skill File Conventions

Each skill directory contains one file, named `SKILL.md`. Two frontmatter styles exist:

**With frontmatter** (preferred for skills meant to be installed via Claude Code's skill system):
```markdown
---
name: skill-name
description: "One-sentence description shown in skill picker"
---

# Skill Title
...
```

**Without frontmatter** (`impactful-slides/SKILL.md`) — works as a standalone prompt, not registered via metadata.

## Skill Structure Patterns

Skills in this repo follow a consistent internal structure:

- **Role declaration** — who/what the AI is
- **Core framework** — the methodology or principles (e.g., NVC's 4 components, McKinsey's 7 slide principles)
- **Modes of operation** — numbered/named modes triggered by different user intents
- **Output format** — explicit response structure with section headers
- **Tone guidelines** — how to communicate, what to avoid

## Adding a New Skill

1. Create a new directory: `skill-name/`
2. Create `skill-name/SKILL.md` with frontmatter `name` and `description` fields
3. Follow the structure pattern above — role → framework → modes → output format → tone

No build, lint, or test commands — this repo is pure markdown.
