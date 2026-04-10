# GitHub Copilot Workshop Trainer Cue Card

## Opening

- This workshop is about structure, not prompt memorization.
- We are using one flow across four blocks: spec, review, build, design.
- The audience does not need to code by hand.
- Their job is to describe, review, and refine.

## Setup Check

- VS Code is open.
- GitHub Copilot is enabled.
- Copilot Chat opens.
- BuildAppWorkshop is open in VS Code.
- If not, ask Copilot to clone the repo and open it.

## Ground Rules

- Keep the app small.
- Browser-based and local.
- No auth.
- No backend.
- Demoable in about 90 minutes.

## Block 1

- Open [WORKSHOP-BLOCK-1.md](../WORKSHOP-BLOCK-1.md).
- Use the 1 Spec Agent.
- Get to a buildable `app-spec.md`.
- Push people to iterate, not accept the first draft.
- Debrief: user, workflow, scope cuts.

## Block 2

- Open [WORKSHOP-BLOCK-2.md](../WORKSHOP-BLOCK-2.md).
- Run the 2 Spec Review Agent twice with two models.
- Compare specificity, blockers, and hallucinations.
- Apply the best fixes back to `app-spec.md`.
- Debrief: which model was better for review, and why.

## Block 3

- Open [WORKSHOP-BLOCK-3.md](../WORKSHOP-BLOCK-3.md).
- Use the 3 Build Agent.
- Build from `app-spec.md`.
- Watch grounding: Microsoft Learn MCP plus GitHub MCP when relevant.
- Emphasize authoring-time grounding, not runtime dependency.
- Debrief: what changed because of MCP.

## Block 4

- Open [WORKSHOP-BLOCK-4.md](../WORKSHOP-BLOCK-4.md).
- Stay in default Agent mode.
- Do not select a custom agent.
- Ask Copilot to apply the Zava design language.
- Skill carries behavior, GitHub MCP carries source material.
- Debrief: what came from the skill versus the MCP content.

## Close

- Start with a spec.
- Review before building.
- Choose the model for the task.
- Ground implementation with trusted context.
- Use skills for more repeatable outcomes.
- Ask for feedback after the session.