# Block 4: Zava Design Skill

> **Reading this in VS Code?** Press `Cmd+Shift+V` (Mac) or `Ctrl+Shift+V` (Windows / Linux) to open Markdown preview. Drag the preview tab to the centre of the screen to view it full-width.

**Goal:** Apply the Zava design language to your app — grounded in real brand guidance retrieved from a GitHub repository — without changing anything about how the app works.

Estimated time: **15–20 minutes**

---

## What Happens in This Block

This block has no custom agent. You stay in default Agent mode and send a plain prompt. What makes this block different is what fires automatically underneath: the `zava-designer` **skill**.

A skill is a set of rules and retrieval instructions that Copilot activates automatically when it detects relevant work. The `zava-designer` skill is configured to fire on any UI work — building, styling, or improving any interface — without you having to select it or mention Zava. Copilot reads the skill, knows what design system to apply and where to retrieve the brand guidance, and acts on it.

This block is about observing that moment. You will send a simple prompt and watch the skill activate, retrieve real brand files from a GitHub repository through MCP, and apply a consistent design.

This block demonstrates two things:
1. How a **skill** changes Copilot's behavior automatically — without a custom agent or extra instructions from you
2. How **GitHub-grounded design** produces consistent, brand-aligned results rather than Copilot improvising a visual style

---

## What Is the Zava Design Language?

Zava is a calm, modern, enterprise-ready visual system built around:

- Dark teal header and footer regions
- Light gray-blue body backgrounds
- White content surfaces (cards, panels, tables, forms)
- Clean typography using the system UI font stack
- Lightly bordered cards with modest radius — no heavy shadows
- Minimal, purposeful motion
- The monochrome Zava logo as the primary brand signal

The agent retrieves the exact tokens, layout rules, logo usage guidelines, and UI patterns from the `Jfhelin/zava-design-guidelines` repository — so the output is grounded in the actual brand spec, not the model's interpretation of "enterprise design."

---

## Step 1: Apply the Design

1. Open **Copilot Chat** and confirm you are in **Agent mode**
2. **Do not select a custom agent** — stay on the default agent. The skill fires on its own.
3. Send this message:

   > "Apply the Zava design language to the app."

Copilot will:
- Automatically activate the `zava-designer` skill — watch for it appearing in the chat response
- Retrieve color tokens, layout structure, UI patterns, and logo guidance from `Jfhelin/zava-design-guidelines` via GitHub MCP
- Apply the design to the app files built in Block 3
- **Not change** any functionality, data, or core workflows

---

## Step 2: Watch What the Agent Retrieves

The agent will reach out to GitHub MCP to pull specific files and issues from `Jfhelin/zava-design-guidelines`. Pay attention to:

- **Which files it retrieves** — `tokens.json`, `page-structure.md`, `zava-ui-patterns.md`, `logo-usage.md`, `assets/logo-primary.png`
- **Which issues it reads** — #1 design guidance, #2 logo usage, #3 copy tone, #4 do-not-do, #5 layout blocks
- **What decisions it attributes to the guidelines** — does it say "I used teal from tokens.json" or does it just make changes silently?

The grounding chain — **skill → MCP → guidelines repo → code changes** — is the core thing to observe in this block.

---

## Step 3: Review the Styled App

Once Copilot finishes, ask it to start the app if it is not already running:

> "Start the app so I can review the design."

Copilot will run the correct start command in the terminal. Then reload the app in your browser and compare it to Block 3.

Look for:

| Element | What Zava should look like |
|---------|---------------------------|
| Header | Dark teal band with navigation |
| Body background | Light gray-blue |
| Content areas | White cards or panels with light borders |
| Typography | Clean, readable, system font |
| Logo | Monochrome Zava logo in the header |
| Controls | Consistent buttons, inputs, and badges |
| Spacing | Even, structured — not cramped or overly spread |

If something looks off — wrong colors, missing logo, broken layout — give feedback:

> "The header is not using the dark teal color. Please check the tokens and reapply."

> "The cards still have heavy box shadows. Zava uses light borders instead."

> "The logo is missing from the header. Please add it using the approved asset from the brand repo."

---

## Step 4: Verify No Functionality Was Changed

The design pass should be invisible to the app's behavior. Verify:

- [ ] All filters, search, and interactions still work
- [ ] Sample data is still visible and correct
- [ ] No new screens or features were added
- [ ] The app still opens without any setup

If the agent broke something functional, tell it:

> "The status filter stopped working after the design changes. Please restore it."

---

## What to Look for Before Finishing

- [ ] The app looks like a Zava app — teal header, light body, white surfaces
- [ ] The Zava logo appears in the header
- [ ] Typography and spacing feel clean and consistent
- [ ] No functionality was lost or changed
- [ ] You can point to at least one design decision the agent made because of the brand repo

---

## End of Workshop Check

You have now built a complete, styled, browser-based app using:

- A spec produced by an agent and refined through iteration
- A review that surfaced and fixed spec problems before they became code problems
- A build grounded in real technical documentation and realistic sample data
- A design pass driven by a skill and a live brand guidelines repository

Before you finish, make sure you can answer these:

1. **Why did the spec step matter?** What would have gone wrong if you skipped it?
2. **Why does model choice matter?** What was different between the two review outputs?
3. **What did MCP add to the build?** What would the agent have done differently without it?
4. **What did the skill do in the design step?** What changed because of it versus what the agent would have done on its own?
5. **What is the difference between a skill and a custom agent?** What did the skill do that a custom agent would have done differently — or couldn't do at all?

---

## What You Learned in This Block

- What a **skill** is — a set of rules and retrieval instructions that Copilot activates automatically, without you selecting an agent or writing extra instructions
- That skills fire based on the *type of request*, not because you asked for them — that is the design intent
- How GitHub-grounded design produces consistent, brand-aligned output versus Copilot improvising from its training data
- The difference between a skill (carries process and rules) and MCP (supplies live content) — and why separating them makes each independently auditable
- How to verify a design pass without breaking the app underneath it

---

[Back: Block 3 — Build](WORKSHOP-BLOCK-3.md) | [Workshop Overview](WORKSHOP.md)
