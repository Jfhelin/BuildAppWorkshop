# Block 1: Spec Agent

> **Reading this in VS Code?** Press `Ctrl+Shift+V` (Windows / Linux) or `Cmd+Shift+V` (Mac) to open Markdown preview.

**Goal:** Turn your app idea into a clear, reviewed draft spec that is ready for a build agent.

This block is about thinking before building. A good spec saves you from halfway-built apps and late pivot decisions. The Spec Agent will help you structure your idea — but *you* need to iterate on it until it actually describes what you want.

Estimated time: **15–20 minutes**

---

## Step 1: Pick a Good Idea

Your app needs to be small, local, and concrete. Avoid anything that naturally requires a login, a database, or an external service. If explaining it requires the phrase "and then it connects to...", simplify the idea first.

### What makes a good workshop idea

A good idea:
- Has a **clear user** (who uses it and why)
- Has a **clear primary action** (what the user does in the app)
- Works with **list + detail** patterns, forms, filters, dashboards, cards, or interactive visuals
- Can be demoed by opening a single page in a browser
- Does not require a backend, a database, or user accounts to work

Good categories:
- **Internal tools and dashboards** — order trackers, support consoles, KPI views, task boards
- **Games and simulations** — browser-based games (flight simulator, strategy, puzzle) work well because all state is local and there is no auth or persistence needed
- **Apps powered by a public no-auth API** — if a free API requires no account or API key, it is fair game. Example: [open-meteo.com](https://open-meteo.com/) provides weather forecasts with no key required. A weather dashboard or route planner built on top of it is a perfectly valid workshop app.

A bad idea for this workshop:
- Anything with login or user accounts
- Anything that requires a paid API, API keys, or account sign-up
- Anything that needs a database or server to work
- Apps that are primarily about creating or editing content (rich text editors, drawing tools, video editors) — these are harder to scope and demo in 90 minutes

### Ready-made ideas based on available sample data

The workshop repository is pre-loaded with realistic sample data in [Jfhelin/zava-sample-data](https://github.com/Jfhelin/zava-sample-data). Using one of these ideas means the Build Agent can hit the ground running with real data instead of making things up.

| App idea | What it does | Sample data it uses |
|----------|-------------|---------------------|
| **Customer account overview** | Browse and search customer accounts, view account details and recent notes | Customers, customer notes |
| **Order management dashboard** | View and filter orders, see order items, check product details | Orders, order items, products |
| **Support ticket console** | Triage open support cases, view case history and updates | Support cases, case updates |
| **Appointment manager** | View and filter upcoming appointments by advisor or status | Appointments, advisors |
| **Operations task board** | See tasks across work queues, filter by status or team | Tasks, work queues |
| **KPI / executive dashboard** | Display key business metrics, trend charts, and volume summaries | KPI summary, sales trend, case volume trend |

### Other valid ideas

You are not limited to the sample data scenarios. These also work well:

| App idea | Notes |
|----------|-------|
| **Flight simulator** | Browser-based, canvas or WebGL, all state is local — a great fit for a game-style build |
| **Weather dashboard** | Uses the free [Open-Meteo API](https://open-meteo.com/) — no account or API key required |
| **Route weather planner** | Combines a route input form with Open-Meteo forecasts along the route |
| **Browser game** | Puzzle, strategy, arcade — anything that runs entirely in the browser with local state |

If you have a completely different idea, use it — just make sure it fits the ground rules: no auth, no API keys, no backend required to demo.

---

## Step 2: Open the 1 Spec Agent in Copilot Chat

1. Open **Copilot Chat** in VS Code (press `Ctrl+Alt+I` / `Cmd+Shift+I`, or click the Copilot icon in the sidebar)
2. In the chat input, switch to **Agent mode** using the mode selector at the bottom of the chat panel
3. Select the **1 Spec Agent** from the agent picker

> **Tip:** If you do not see the **1 Spec Agent**, type `@` in chat and look for it in the list. If it does not appear, ask your facilitator.

---

## Step 3: Describe Your Idea

In the chat, describe your app in plain language. You do not need a formal description — just say what the app is for and who uses it.

**Example prompts to get started:**

> "I want to build an order management dashboard where a sales manager can browse recent orders, filter by status, and drill into order details."

> "I want a support ticket console where a support agent can see their open cases, sort by priority, and mark cases as resolved."

> "I want a customer account overview where an account manager can search for customers and see their recent notes and activity."

The agent will produce a draft spec and save it as `app-spec.md`.

---

## Step 4: Review the Spec

Read through `app-spec.md`. A good spec at this stage should have:

- [ ] **Target user** — who uses the app and what their role is
- [ ] **User problem** — what problem the app solves for them
- [ ] **Core workflow** — what the user actually does, step by step
- [ ] **Success criteria** — how you know the app is working
- [ ] **Constraints** — what the app does *not* do (no auth, no backend, local only)
- [ ] **Minimum data** — what data the app needs and where it comes from
- [ ] **Non-goals** — features explicitly out of scope
- [ ] **Implementation note** — a short hint for the build agent

If any of these sections feel vague, wrong, or missing — **do not move on**. Go to Step 5.

---

## Step 5: Iterate Until You Are Happy

This is the most important step. Keep asking the Spec Agent for changes until the spec accurately describes what you want to build.

**Examples of follow-up messages:**

> "The core workflow is too vague. Can you be more specific about what the user sees on the main screen and what actions they can take?"

> "I don't want a form-based workflow, I want a dashboard with a table and filters. Please update the spec."

> "The target user should be a field technician, not a manager. Update the spec accordingly."

> "Can you add search as a core feature? The user needs to search by customer name."

> "The non-goals section doesn't mention that there's no backend. Please add that explicitly."

There is no fixed number of rounds. Iterate until the spec feels like a clear, honest description of the app you want. Do not move to Block 2 until you are satisfied.

---

## Step 6: Save and Move On

Once you are happy with the spec, confirm the file is saved as `app-spec.md` in the root of the repository.

**Before moving to Block 2, you should be able to answer:**

- Who is the user and what problem does the app solve for them?
- What does the user do on the main screen?
- What data does the app use, and where does it come from?
- What is explicitly out of scope?

If you cannot answer those confidently, spend more time in Step 5.

---

## What You Learned in This Block

- How to describe an app idea precisely enough for a build agent to act on it
- Why constraints (no auth, no backend, local only) belong in the spec — not just in your head
- How to use a spec agent iteratively rather than accepting the first output
- Why a clear spec is faster than fixing a misbuilt app

---

[Next: Block 2 — Spec Review](WORKSHOP-BLOCK-2.md)
