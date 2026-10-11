---
name: design-principles
description: Enforce a precise, minimal design system inspired by Linear, Notion, and Stripe. Use this skill when building dashboards, admin interfaces, or any UI that needs Jony Ive-level precision - clean, modern, minimalist with taste. Every pixel matters.
---

# Design Principles

This skill enforces precise, crafted design for enterprise software, SaaS dashboards, admin interfaces, and web applications. The philosophy is Jony Ive-level precision with intentional personality — every interface is polished, and each is designed for its specific context.

## Design Direction (REQUIRED)

**Before writing any code, commit to a design direction.** Don't default. Think about what this specific product needs to feel like.

### Think About Context

- **What does this product do?** A finance tool needs different energy than a creative tool.
- **Who uses it?** Power users want density. Occasional users want guidance.
- **What's the emotional job?** Trust? Efficiency? Delight? Focus?
- **What would make this memorable?** Every product has a chance to feel distinctive.

### Pick a Vibe (REQUIRED)

Choose ONE primary aesthetic direction. This is the foundation — everything else builds on it.

| Direction | When to Use | Feel | Typography | Color | Spacing | Personality |
|-----------|--------------|------|------------|-------|---------|-------------|
| **Linear** | Data, analytics, B2B, internal tools | Clean, precise, Swiss | Inter, system fonts | Monochrome + 1 accent | Tight, consistent | Confident, no-nonsense |
| **Notion** | Docs, knowledge, collaboration | Friendly, approachable, soft | Rounded sans-serif | Neutral grays + pastels | Generous | Warm, human |
| **Stripe** | Payments, fintech, professional | Premium, trustworthy, refined | Sharp sans-serif | Deep blues/blacks + white | Balanced | Sophisticated, reliable |
| **Figma** | Creative tools, design systems | Playful, expressive, bold | Geometric sans-serif | Vibrant gradients | Flexible | Fun, creative |
| **Vercel** | Developer tools, platforms | Technical, modern, sleek | Mono/spaced fonts | Dark mode + neon | Compact | Geeky, cutting-edge |

**Default to Linear** if unsure. It's the safest for most professional software.

## Design System Rules

### Typography

**Font Stack (use exactly this):**
```css
font-family: Inter, -apple-system, BlinkMacSystemFont, "Segoe UI", Robot, "Helvetica Neue", Arial, sans-serif;
```

**Weights:**
- Body: 400 (normal)
- Medium emphasis: 500
- Strong emphasis: 600
- Headings: 600 or 700

**Sizes (rem based, never px for text):**
- Body: 1rem (16px)
- Small: 0.875rem (14px)
- Large body: 1.125rem (18px)
- H1: 2rem (32px)
- H2: 1.5rem (24px)
- H3: 1.25rem (20px)
- H4: 1.125rem (18px)

### Spacing

**Use rem, never px.** Base unit = 0.25rem (4px).

```
0   = 0rem     (0px)   - none
1   = 0.25rem  (4px)   - tight
2   = 0.5rem   (8px)   - small
3   = 0.75rem (12px)  - medium-small
4   = 1rem     (16px)  - standard
6   = 1.5rem   (24px)  - large
8   = 2rem     (32px)  - x-large
12  = 3rem     (48px)  - xx-large
16  = 4rem     (64px)  - section spacing
```

**Vertical rhythm:** Multiples of 4px. Never use odd numbers (5, 7, 9, 11, etc.).

### Color

**Use a constrained palette.** Pick ONE primary color and build around it.

**Linear (Default):**
```
Primary:   #3B82F6 (blue-500)
Secondary: #64748B (slate-600)
Success:   #22C55E (green-500)
Warning:   #F59E0B (amber-500)
Error:     #EF4444 (red-500)
Background: #FFFFFF
Surface:   #F8FAFC (slate-50)
Border:    #E2E8F0 (slate-200)
Text:      #1E293B (slate-800)
Muted:     #64748B (slate-600)
```

**Notion:**
```
Primary:   #8B5CF6 (violet-500)
Background: #FFFFFF or #FDFDFD
Surface:   #F9F9F9
Border:    #E5E7EB
Text:      #374151
```

**Stripe:**
```
Primary:   #635BFF (indigo-500)
Background: #FFFFFF
Surface:   #F6F9FC
Border:    #E6EBF2
Text:      #0A2540
```

**Rules:**
- Primary color usage: max 10% of the interface
- Never use pure black (#000000) or pure white (#FFFFFF) for text
- Use semantic color names in code: `primary`, `success`, `error`, not hex codes
- Background must pass WCAG AA contrast with text

### Layout

**Grid:** 12-column, 16px gap (1rem). Mobile: 4-column.

**Max widths:**
- Full page: 1440px
- Content: 1200px
- Text: 65ch (≈720px)

**Card padding:**
- Small: 1rem (16px)
- Standard: 1.5rem (24px)
- Large: 2rem (32px)

**Card shadows (use exactly):**
```css
box-shadow: 0 1px 3px 0 rgb(0 0 0 / 0.1), 0 1px 2px -1px rgb(0 0 0 / 0.1);
```

Or for elevated cards:
```css
box-shadow: 0 4px 6px -1px rgb(0 0 0 / 0.1), 0 2px 4px -2px rgb(0 0 0 / 0.1);
```

### Borders

**Width:** Always 1px. Never 2px, 3px, etc.

**Color:** Use slate-200 (#E2E8F0) for light mode, slate-700 (#334155) for dark mode.

**Radius:**
- Small: 0.25rem (4px) - inputs, buttons
- Medium: 0.375rem (6px) - cards
- Large: 0.5rem (8px) - containers
- Full: 9999px - pills, badges

### Buttons

**Primary:**
```
Background: Primary color
Text: White
Padding: 0.75rem 1.5rem (12px 24px)
Radius: 0.25rem (4px)
Font: 500, 0.875rem (14px)
Shadow: 0 1px 2px 0 rgb(0 0 0 / 0.05)
Hover: Darken primary by 10%
Active: Darken primary by 20%
```

**Secondary:**
```
Background: White
Border: 1px solid slate-300
Text: slate-700
Padding: 0.75rem 1.5rem
Radius: 0.25rem
Font: 500, 0.875rem
Hover: Border slate-400, background slate-50
Active: Border slate-500, background slate-100
```

**Ghost:**
```
Background: Transparent
Text: slate-600
Padding: 0.75rem 1.5rem
Radius: 0.25rem
Font: 500, 0.875rem
Hover: Background slate-100
Active: Background slate-200
```

### Forms

**Inputs:**
```
Border: 1px solid slate-300
Radius: 0.25rem
Padding: 0.625rem 0.875rem (10px 14px)
Font: 400, 0.875rem
Focus: Border primary, shadow 0 0 0 3px rgba(primary, 0.1)
Placeholder: slate-400
```

**Labels:**
```
Font: 500, 0.75rem (12px)
Color: slate-700
Margin-bottom: 0.5rem (8px)
```

### Tables

**Header:**
```
Background: slate-50
Text: slate-700
Font: 600, 0.75rem
Padding: 0.75rem 1rem
Border-bottom: 1px solid slate-200
```

**Cell:**
```
Padding: 0.75rem 1rem
Border-bottom: 1px solid slate-100
Text: slate-600
Font: 400, 0.875rem
```

**Row hover:** Background slate-50

## Component Patterns

### Empty States

Always include:
1. Icon (48x48px)
2. Headline (H3, 1.25rem)
3. Description (1-2 sentences, slate-500)
4. Primary action button

**Example:**
```
┌─────────────────────────────────┐
│                                     │
│     📄                           │
│     No projects yet               │
│     Get started by creating your │
│     first project.               │
│                                     │
│     [Create Project]             │
│                                     │
└─────────────────────────────────┘
```

### Loading States

Use skeleton screens, not spinners. Skeleton should match the content shape.

**Card skeleton:**
```
┌─────────────────────────────────┐
│ ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░ │
│ ░░░░░░░░░░░░                    ░░ │
│ ░░░░░░░░░░░░                    ░░ │
│ ░░░░░░░░░░░░                    ░░ │
└─────────────────────────────────┘
```

Animation: Shimmer (gradient moving left to right, 1.5s infinite).

### Error States

**Inline validation:**
```
┌─────────────────────────────────┐
│ Label                           │
│ ┌─────────────────────────────┐ │
│ │ Email                       │X│
│ └─────────────────────────────┘ │
│ Please enter a valid email      │
└─────────────────────────────────┘
```

Text: red-500, 0.75rem
Icon: red-500, 1rem

### Tooltips

```
┌─────────────────────┐
│ This is a tooltip   │
└─────────────────────┘
```

Padding: 0.5rem 0.75rem
Background: slate-900
Text: white
Font: 400, 0.75rem
Radius: 0.25rem
Shadow: 0 4px 6px -1px rgb(0 0 0 / 0.1), 0 2px 4px -2px rgb(0 0 0 / 0.1)
Arrow: 8px, same color as background

## Accessibility

**Required:**
- Every interactive element must have :hover, :focus, :active states
- Focus ring: 2px solid primary, offset 2px
- Color contrast: Minimum 4.5:1 for text
- Keyboard navigation: Tab order must be logical
- ARIA labels on icon-only buttons

**Testing:**
- Use a keyboard to navigate the entire interface
- Use a screen reader (VoiceOver/NVDA) to verify labels
- Check color contrast with [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/)

## Code Quality

**CSS:**
- Use Tailwind CSS (preferred) or inline styles
- Never use !important
- Alphabetize class names
- Group related classes: `text-sm font-medium text-slate-600`

**Naming:**
- Components: PascalCase (Button, Card, Input)
- Utilities: kebab-case (text-primary, bg-secondary)
- Variables: SCREAMING_SNAKE_CASE (PRIMARY_COLOR, MAX_WIDTH)

**Organization:**
- One component per file
- Components in `components/` directory
- Styles in `styles/` directory
- Global styles in `styles/globals.css`

## Review Checklist

Before shipping, verify:

- [ ] Design direction chosen and documented
- [ ] Typography uses correct font stack and sizes
- [ ] Spacing uses rem, multiples of 4px
- [ ] Colors from approved palette
- [ ] Layout respects max widths
- [ ] Buttons follow size and style rules
- [ ] Forms have proper labels and validation
- [ ] Empty states are designed
- [ ] Loading states use skeletons
- [ ] Error states are clear and actionable
- [ ] Tooltips are positioned correctly
- [ ] Accessibility requirements met
- [ ] Code is clean and organized
- [ ] Responsive on mobile, tablet, desktop
- [ ] Tested in both light and dark mode (if applicable)

## Inspiration

Study these products for reference:
- **Linear:** https://linear.app
- **Notion:** https://notion.so
- **Stripe:** https://stripe.com
- **Vercel:** https://vercel.com
- **Figma:** https://figma.com

Notice how each has a distinct personality while maintaining precision.
