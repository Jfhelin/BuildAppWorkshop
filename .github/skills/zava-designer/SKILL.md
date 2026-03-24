---
name: zava-designer
description: 'Zava is the default and only design language for all apps built in this company. Apply automatically whenever building, styling, or improving any app UI — even when the user does not mention Zava. Use for any UI work: building a new app, improving layout, polishing an interface, adding branding, fixing colors, adjusting spacing, or making any visual change. Retrieves design guidance from the Jfhelin/zava-design-guidelines GitHub repository via MCP.'
---

# Zava Designer

Zava is the company-wide default design system. Apply it to **every** app, regardless of whether the user explicitly requests it. Whenever any UI is built or modified, ground all visual decisions in the Zava design language from the public GitHub repository `Jfhelin/zava-design-guidelines`.

## How This Skill Works

This skill bundles the rules, retrieval map, and source authority for Zava design into one place.

**This skill fires automatically.** You do not need to select a custom agent or invoke anything manually. Whenever Copilot detects UI work in Agent mode — building, styling, or improving any interface — this skill activates and shapes the response. That is the point: design decisions are grounded without you having to remember to ask.

When this skill is active, Copilot knows:

1. **What to apply** — the Zava visual rules and constraints below
2. **Where to look** — the `Jfhelin/zava-design-guidelines` repository via GitHub MCP
3. **What is available** — both files (brand guidance, tokens, assets) and published GitHub issues (design directives)

The separation is intentional: the skill carries the *process*, GitHub MCP supplies the *content*. This means design decisions are grounded in a live, auditable source — not in the model's training data.

## Goals

- Apply a calm, modern, enterprise-ready Zava style
- Improve hierarchy, readability, spacing, and responsiveness
- Reuse approved assets and guidance from `Jfhelin/zava-design-guidelines`
- Preserve accessibility and functional clarity

## Grounding Workflow

- Use GitHub MCP to retrieve all design guidance from `Jfhelin/zava-design-guidelines`
- Prefer GitHub MCP file and issue retrieval over public web access
- Do not fetch brand files, logos, or style guidance from arbitrary public URLs
- Prefer guidance in files before inventing stylistic details
- Use `brand/tokens.json` and `brand/page-structure.md` as the default starting points for color and layout

## What Is Available in Jfhelin/zava-design-guidelines

### Files

| File | What it contains |
|------|-----------------|
| `brand/zava-style.md` | Overall visual direction, tone, and design principles |
| `brand/page-structure.md` | Header, body, and footer layout structure |
| `brand/zava-ui-patterns.md` | Component patterns: cards, tables, forms, controls |
| `brand/tokens.json` | Colors, radii, typography, spacing, borders, shadows |
| `brand/logo-usage.md` | Logo placement rules and constraints |
| `assets/logo-primary.png` | Canonical Zava logo — reference by URL in the app, do not fetch the binary via MCP |
| `assets/logo-preview.jpg` | Visual reference only — do not fetch via MCP |

### Published GitHub Issues

| Issue | Title | Labels | What it covers |
|-------|-------|--------|----------------|
| #1 | Zava Design Guidance | design-guidance, zava | Core design direction: calm, modern, card-based, monochrome brand |
| #2 | Zava Logo Usage | zava, logo | Logo placement, no recoloring, single placement per page |
| #3 | Zava Copy Tone | zava, copy | Direct, concise, service-oriented — no hype or playful tone |
| #4 | Zava Design Do Not Do | zava, design-guardrails | Anti-patterns: dark dashboards, competing accents, gradients, custom logos |
| #5 | Zava Layout Blocks | zava, layout | Dark teal header, light body, white cards, structured footer |

## Retrieval Map

Use these sources depending on the task:

- **Overall visual direction** — `brand/zava-style.md`, issue #1
- **Layout structure** — `brand/page-structure.md`, `brand/zava-ui-patterns.md`, issue #5
- **Colors, radii, typography, borders, shadows** — `brand/tokens.json`
- **Logo placement and constraints** — `brand/logo-usage.md`, issue #2 (do not fetch the PNG binary via MCP)
- **Copy tone** — issue #3
- **Guardrails and anti-patterns** — issue #4

## Retrieval Triggers

Zava is always active. Load the relevant sources based on the type of work:

- Building or scaffolding any new UI:
  - `brand/zava-style.md`, `brand/tokens.json`, `brand/page-structure.md`, `brand/zava-ui-patterns.md`, issues #1, #5
- `add a logo`, `brand this`, `add branding`:
  - `brand/logo-usage.md`, issue #2
  - Use the logo by referencing its raw GitHub URL directly in the app's HTML/CSS: `https://raw.githubusercontent.com/Jfhelin/zava-design-guidelines/main/assets/logo-primary.png`
  - Do not fetch the PNG file via GitHub MCP — passing binary image data to the model will fail
- `improve the header`, `fix the top of the page`:
  - `brand/page-structure.md`, `brand/tokens.json`, `brand/logo-usage.md`, issue #5
- `improve the footer`:
  - `brand/page-structure.md`, `brand/tokens.json`, issue #5
- `fix the colors`, `adjust spacing`, `make the controls match`:
  - `brand/tokens.json`, `brand/zava-ui-patterns.md`
- `fix the copy`, `make the tone match`:
  - issue #3

## Rules

- Do not change the app's product scope or core workflow
- Do not invent a new brand style — always retrieve from `Jfhelin/zava-design-guidelines` first
- Prefer dark teal header/footer regions, light gray-blue body background, and white content surfaces
- Use the monochrome Zava logo as the primary brand signal
- Use cards, panels, tables, forms, and clear headers over decorative patterns
- Use the system UI font stack
- Keep cards lightly bordered with modest radius — no heavy shadows
- Keep motion minimal and purposeful
- Preserve or improve accessibility and contrast
- Do not apply anti-patterns from issue #4

## Logo Behavior

- Retrieve `brand/logo-usage.md` from `Jfhelin/zava-design-guidelines` and read issue #2 before placing a logo
- **Do not fetch `assets/logo-primary.png` via GitHub MCP** — binary image files cannot be passed to the model and will cause a 400 error
- Reference the logo in the app using its raw GitHub URL: `https://raw.githubusercontent.com/Jfhelin/zava-design-guidelines/main/assets/logo-primary.png`
- Place an `<img>` tag with that URL in the page header by default unless guidance says otherwise
- Do not recolor, distort, or create custom variants of the logo
- If the URL is unreachable at runtime, fall back to a text wordmark only

## Decision Rule

- Treat files in `issues/seed/` as templates for published GitHub issues, not as the live issue source
- Retrieve only the sources needed for the requested change, not the entire repo
- Start with the most specific source for the request, then add `brand/tokens.json` if styling details are needed
- If two sources conflict, prefer:
  1. asset file
  2. brand markdown file
  3. issue guidance

## Expected Output

- **Skill constraints applied** — which rules from the `zava-designer` skill shaped the output
- **Files retrieved via GitHub MCP** — which files from `Jfhelin/zava-design-guidelines` were used and what they contributed
- **Issues retrieved via GitHub MCP** — which issues influenced decisions and what guidance they provided
- **Visual changes made** — what specifically changed in the app and why
