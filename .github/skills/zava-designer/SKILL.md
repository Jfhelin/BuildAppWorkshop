---
name: zava-designer
description: 'Zava is the default and only design language for all apps built in this company. Apply automatically whenever building, styling, or improving any app UI — even when the user does not mention Zava. Use for any UI work: building a new app, improving layout, polishing an interface, adding branding, fixing colors, adjusting spacing, or making any visual change. Retrieves design guidance from the jhelin/designguidelines GitHub repository via MCP.'
---

# Zava Designer

Zava is the company-wide default design system. Apply it to **every** app, regardless of whether the user explicitly requests it. Whenever any UI is built or modified, ground all visual decisions in the Zava design language from the public GitHub repository `jhelin/designguidelines`.

## Goals

- Apply a calm, modern, enterprise-ready Zava style
- Improve hierarchy, readability, spacing, and responsiveness
- Reuse approved assets and guidance from the external design repository
- Preserve accessibility and functional clarity

## Grounding Workflow

- Use GitHub MCP to retrieve all design guidance from `jhelin/designguidelines`
- Prefer GitHub MCP file and issue retrieval over public web access
- Do not fetch brand files, logos, or style guidance from arbitrary public URLs when the GitHub MCP source is available
- Prefer guidance in files before inventing stylistic details
- Check issues for design directives, logo usage notes, and do/don't rules
- Check the external repo assets before adding logos, icons, or hero imagery
- Use `brand/tokens.json` and `brand/page-structure.md` as the default starting points for color and layout

## Retrieval Map

Use these sources by default depending on the request:

- Overall visual direction:
  - `brand/zava-style.md`
  - published GitHub issue created from `issues/seed/01-zava-design-guidance.md`
- Layout structure, header blocks, body blocks, footer blocks:
  - `brand/page-structure.md`
  - `brand/zava-ui-patterns.md`
  - published GitHub issue created from `issues/seed/05-zava-layout-blocks.md`
- Colors, radii, typography, borders, shadows:
  - `brand/tokens.json`
- Logo placement and logo constraints:
  - `brand/logo-usage.md`
  - published GitHub issue created from `issues/seed/02-zava-logo-usage.md`
  - `assets/logo-primary.png`
- Copy tone and wording:
  - published GitHub issue created from `issues/seed/03-zava-copy-tone.md`
- Guardrails and anti-patterns:
  - published GitHub issue created from `issues/seed/04-zava-do-not-do.md`

## Retrieval Triggers

Zava is always active. Load the relevant sources based on the type of work being done — no explicit Zava mention required:

- Building or scaffolding any new UI:
  - `brand/zava-style.md`
  - `brand/tokens.json`
  - `brand/page-structure.md`
  - `brand/zava-ui-patterns.md`
- `add a logo`, `brand this`, `add branding`, or any new app scaffold:
  - `brand/logo-usage.md`
  - `assets/logo-primary.png`
  - published GitHub issue created from `issues/seed/02-zava-logo-usage.md`
- `improve the header`, `make the hero look right`, `fix the top of the page`:
  - `brand/page-structure.md`
  - `brand/tokens.json`
  - `brand/logo-usage.md`
- `improve the footer`:
  - `brand/page-structure.md`
  - published GitHub issue created from `issues/seed/05-zava-layout-blocks.md`
  - `brand/tokens.json`
- `fix the colors`, `adjust spacing`, `make the controls match`, or any visual polish:
  - `brand/tokens.json`
  - `brand/zava-ui-patterns.md`
- `fix the copy`, `make the tone match`, or any copy changes:
  - published GitHub issue created from `issues/seed/03-zava-copy-tone.md`

## Rules

- Do not change the app's product scope or core workflow
- Do not invent a new brand style if grounded Zava guidance exists
- Prefer dark teal header/footer regions, light gray-blue body background, and white content surfaces
- Use the monochrome Zava logo as the main brand signal
- Use cards, panels, tables, forms, and clear headers over decorative landing-page patterns
- Use the system UI font stack
- Keep cards lightly bordered with modest radius instead of heavy shadows
- Keep motion minimal and purposeful
- Preserve or improve accessibility and contrast

## Logo Behavior

- If the user asks to add a logo, first retrieve the approved logo asset and logo-usage guidance from `jhelin/designguidelines` through GitHub MCP
- Use the primary logo by default unless guidance says otherwise
- Place the logo in the page header, app shell, or authentication panel unless another location is explicitly requested
- Do not redraw, recolor, stretch, or replace the approved logo
- If no approved logo asset is found, explain that and fall back to a text wordmark only

## Zava-Specific Layout Defaults

- dark teal header band with simple navigation
- concise hero copy inside the header region
- section heading plus filters/search near the top of the body
- white cards on a light background
- structured multi-column footer with accent-colored headings and muted links

## Decision Rule

- Treat files in `issues/seed/` as templates for published GitHub issues, not as the live issue source
- Retrieve only the sources needed for the requested change, not the entire repo
- Start with the most specific source for the request, then add `brand/tokens.json` if styling details are needed
- If two sources conflict, prefer:
  1. asset file
  2. brand markdown file
  3. issue guidance

## Expected Output

- Explain which files or issues from `jhelin/designguidelines` informed the design
- State that GitHub MCP was used for brand grounding when it was available
- Explain whether branding, logo placement, or layout rules were applied
- Keep the resulting UI practical and demo-ready
