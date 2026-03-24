# App Spec: [App Name]

> This is the canonical spec for the workshop app. It is created and updated by the 1 Spec Agent and refined by the 2 Spec Review Agent. The 3 Build Agent reads this file to implement the app.

---

## Target User

*Who uses this app and what is their role?*

Example: A support agent who needs to triage incoming support cases across multiple queues.

---

## User Problem

*What problem does the app solve for the target user? Why does it matter?*

Example: The agent currently has no single view of all open cases. They switch between systems to check priority and status, which is slow and error-prone.

---

## Core Workflow

*What does the user actually do in the app, step by step?*

Example:
1. Open the app — see a table of all open support cases sorted by priority
2. Filter by status (Open, In Progress, Resolved) or assignee
3. Click a case row to open a detail panel showing case history and updates
4. Mark a case as resolved directly from the detail panel

---

## Success Criteria

*How do you know the app is working correctly?*

Example:
- The case list loads with realistic sample data on first open
- Filtering by status updates the table immediately without a page reload
- The detail panel shows accurate case history for the selected case
- Marking a case resolved updates its status in the list

---

## Constraints

*What the app explicitly does NOT do.*

- No authentication or login
- No backend server or database — all data is local (bundled sample files or in-memory)
- No external API calls at runtime — the app works fully offline
- No data persistence between sessions

*If a public no-auth API is used (e.g. Open-Meteo), state it here explicitly:*

Example: Uses the Open-Meteo API for live weather data — no account or API key required.

---

## Platform Assumptions

- Runs entirely in the browser
- Opens by loading `index.html` directly, or with a single `npm run dev` / `npx serve` command
- No installation, deployment, or infrastructure required
- Target browsers: current Chrome, Firefox, or Safari

---

## Minimum Data

*What data does the app need, and where does it come from?*

Options:
- **Sample data scenario** — name the scenario file from `Jfhelin/zava-sample-data` (e.g. `scenarios/support-triage.md`)
- **Public no-auth API** — name the API and the endpoints used
- **Generated** — the Build Agent will create synthetic data matching the described schema

Example: Uses `scenarios/support-triage.md` from `Jfhelin/zava-sample-data`. Key fields: case ID, title, status, priority, assignee, created date, case updates array.

---

## Non-Goals

*Features explicitly out of scope for this prototype.*

Example:
- Editing or creating new cases
- Email or notification integration
- User roles or permissions
- Charts or analytics views
- Mobile-optimised layout

---

## Implementation Note

*A short hint for the Build Agent about the recommended technical approach.*

Example: Build as a single-page vanilla JS app or a lightweight Vite + framework app. Load the sample data from a bundled JSON file. Use a simple two-panel layout: case list on the left, detail panel on the right. Keep it functional and minimal — design polish comes in Block 4.
