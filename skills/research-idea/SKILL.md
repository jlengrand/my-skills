---
name: research-idea
description: Research the next unfilled business idea in the Obsidian vault and complete its note with description, competitors, tags, pricing model, ranking, and sources. Use when the user says "research my next idea", "fill in the next idea", or invokes /research-idea.
user_invocable: true
---

# Research Idea

Research the first unfilled business idea note and populate all its fields with real, sourced information.

## Step 1 — Find the first unfilled note

Run this to find the first note (alphabetically) where `ranking` is still empty (an empty ranking is the reliable signal that a note hasn't been researched — a note can have a seed `description` but no ranking yet):

```bash
grep -rlE '^ranking:[[:space:]]*$' "/Users/julienlengrand-lambert/Library/Mobile Documents/iCloud~md~obsidian/Documents/Icloud-new-git/Business Ideas/ideas/" | sort | head -1
```

**If the command returns no output**, all ideas have been researched. Print exactly:

```
ALL_IDEAS_RESEARCHED
```

Then stop — do not proceed further.

Read the file. The idea title is the filename (without `.md`).

If the user passed an argument (e.g. `/research-idea MCP server for Goodreads`), use that title to find the matching file instead of finding the first unfilled one.

## Step 2 — Research the idea

Use **WebSearch** and **WebFetch** to research the idea from at least 3 reputable sources. Cover all of these angles:

1. **What it is / problem it solves** — search `"[idea title]"` and read 1-2 results
2. **Existing competitors** — search `"[idea title] alternatives"` or `"[idea title] tools"` or `"[idea concept] software"`, read the pages (not just snippets), and list real product names with their URLs
3. **Pricing models** — look at what competitors charge; note the model (freemium, SaaS per seat, one-time, usage-based, etc.)
4. **Market size / demand** — look for signals: HN discussions, Reddit threads, Product Hunt launches, analyst estimates

For each source you actually fetch (not just search snippets), keep the URL — it goes in the Sources section of the note body.

## Step 3 — Fill in the frontmatter

Update the note file using the Edit tool. Replace these fields with real values:

```yaml
tags: [tag1, tag2]           # 2-5 short lowercase tags, e.g. AI, productivity, mobile, SaaS, developer-tools, privacy
description: "…"             # 2-3 sentences: what the idea is, what problem it solves, why it's interesting
competitors:                 # real existing products/companies — use wikilinks if a note exists, otherwise plain names
  - "Product Name (url)"
updated: YYYY-MM-DD          # today's date
pricing: "…"                 # e.g. "Freemium + SaaS $9-29/mo", "One-time $49", "Usage-based"
ranking: N                   # integer 1-10, see rubric below
```

### Ranking rubric

Score 1–10 based on:
- **Market demand**: is there clear, expressed demand? (HN, Reddit, Product Hunt, existing paid competitors)
- **Competition**: few strong incumbents = higher score; saturated market = lower
- **Feasibility**: can one developer build an MVP in weeks?
- **Differentiation**: does the idea have a real angle vs. what exists?
- **Personal fit**: is this in Julien's wheelhouse (developer tools, AI, productivity, open source)?

Be honest and critical. Most ideas score 4-6. Reserve 8-10 for genuinely under-served markets with clear demand.

## Step 4 — Write the note body

Below the closing `---` of the frontmatter, write a structured research summary:

```markdown
## Research Notes

Brief narrative (3-5 sentences) synthesizing what you found: the market, the opportunity, the main risk.

## Competitors

| Name | URL | Pricing | Notes |
|---|---|---|---|
| … | … | … | … |

## Sources

- [Page title](url) — one line on what you found there
- …
```

## Step 5 — Report back

Tell the user:
- Which idea was researched
- The ranking and a one-sentence reason
- Any surprising finding from the research
