# Block 3: Build Agent

> **Reading this in VS Code?** Press `Cmd+Shift+V` (Mac) or `Ctrl+Shift+V` (Windows / Linux) to open Markdown preview. Drag the preview tab to the centre of the screen to view it full-width.

**Goal:** Build a working first version of your app — grounded in real technical documentation and realistic sample data — that runs entirely in the browser with no setup required.

Estimated time: **25–30 minutes**

---

## What the Build Agent Does

The Build Agent reads `app-spec.md` and implements the app directly in this repository. Before making technical choices, it grounds its decisions in **Microsoft Learn documentation** retrieved through MCP — so framework choices, API patterns, and implementation approaches are based on real, current guidance rather than the model's training data alone.

If your app is based on one of the sample data scenarios, it also retrieves **realistic sample data** from [Jfhelin/zava-sample-data](https://github.com/Jfhelin/zava-sample-data) through GitHub MCP, so your app has real-looking content from the start instead of obvious placeholder filler. If your app uses a different data source (a public API, a game state, or data you define yourself), this step is skipped.

---

## What MCP Grounding Means

MCP (Model Context Protocol) lets the agent query live external sources at authoring time. In this workshop there are two MCP sources connected:

| MCP source | What the agent uses it for |
|------------|---------------------------|
| **Microsoft Learn MCP** | Confirms correct API usage, framework patterns, and implementation guidance before writing code |
| **GitHub MCP** | Retrieves sample datasets, schemas, and scenario briefs from `Jfhelin/zava-sample-data` |

This is **authoring-time grounding only** — the built app itself does not call out to any external service. The agent uses MCP to *write better code*; the app runs fully off that code without any network dependency.

---

## Step 1: Start the Build Agent

1. Open **Copilot Chat** and switch to **Agent mode**
2. **Switch to a strong coding model.** In Block 2 you may have switched to a model optimised for analysis. For the build step you want a model that excels at writing code — **Claude Opus 4.6** or **GPT-5.4** are good choices. Use the model picker at the bottom of the chat panel to switch before continuing.
3. Select the **3 Build Agent**
4. Send this message:

   > "Implement the app from app-spec.md."

The agent will:
- Read `app-spec.md`
- Consult Microsoft Learn MCP for implementation guidance
- Retrieve the relevant scenario, dataset, and schema files from `Jfhelin/zava-sample-data`
- Create the app files directly in this repository

---

## Step 2: Watch What the Agent Does

While the agent works, pay attention to:

- **Which MCP sources it queries** — what documentation does it reach for, and why?
- **Which sample-data files it retrieves** — does it match the data to your spec?
- **What technical decisions it makes** — framework, data handling, file structure
- **What it says it did not do** — the agent should explicitly note what visual design work it left for Block 4

This is not just a build step — observing the agent's reasoning is part of what you are here to learn.

---

## Step 3: Open the App

Once the agent finishes, open the app in your browser.

Depending on what the agent built, either:

- Open `index.html` directly in the browser (drag it in, or right-click > Open With), or
- Run the single start command the agent provides (typically `npm run dev` or `npx serve`)

No other setup should be required. If it asks you to configure a database, create accounts, or add API keys — that is a sign something went off-spec. Ask the agent to fix it.

---

## Step 4: Verify the App Meets the Spec

Check the running app against `app-spec.md`:

- [ ] The main screen matches the core workflow described in the spec
- [ ] Sample data is visible — real-looking names, values, and content (not "Lorem Ipsum" or `item_1`)
- [ ] The app works without any network connection
- [ ] No login screen or auth prompt appears
- [ ] Key interactions from the spec work (filters, search, detail views, etc.)

If something is missing or broken, follow up in chat:

> "The filter by status isn't working. Please fix it."

> "The detail view is missing. When I click a row, nothing happens. Please add it."

> "The data looks like placeholders. Please pull the actual sample data from the zava-sample-data repo."

---

## Step 5: Review the Build Summary

The agent will provide a summary at the end listing:
- What Microsoft Learn MCP guidance it used
- Which sample-data files it retrieved
- What it built
- What visual design work remains for Block 4

Read this summary. It tells you what grounding actually influenced the output, which is useful for understanding what MCP adds vs. what the model would have done on its own.

---

## What You Learned in This Block

- How MCP lets agents ground technical decisions in live documentation rather than training data alone
- How sample data repositories give agents a shared, controlled source of realistic content
- That the build output should be verified against the spec — agents drift without feedback
- That modern coding models can produce a working, multi-feature app from a written spec in minutes — the bottleneck is the quality of the spec, not the speed of the code generation
- That a clear, specific spec translates almost directly into working code, while a vague spec produces working code that does the *wrong thing* — the model follows what you wrote, not what you meant

---

[Back: Block 2 — Spec Review](WORKSHOP-BLOCK-2.md) | [Next: Block 4 — Design](WORKSHOP-BLOCK-4.md)
