# Workshop Guide

This guide is the participant walkthrough. Work through the four blocks in order and build directly in this repository.

## Before You Start

- Confirm you can use GitHub Copilot in VS Code
- Confirm Copilot CLI is available
- Confirm `Microsoft Learn MCP` and `GitHub MCP` are already configured
- Confirm the `zava-designer` skill is available in your environment
- Confirm GitHub MCP can reach `jhelin/designguidelines`
- Pick a small app idea:
  - internal tool
  - dashboard
  - form-based workflow
  - lightweight tracker

Keep your app small enough for a 90-minute prototype. Avoid auth, payments, and complex backend work.

## Files You Will Produce

- `spec-v1.md`
- `spec-review-a.md`
- `spec-review-b.md`
- `spec-v2.md`

Use [.github/workshop/spec-templates/app-spec-template.md](.github/workshop/spec-templates/app-spec-template.md) as your spec shape.

## Block 1: Spec Agent

Goal: turn your idea into a clear draft spec.

1. Open [.github/workshop/agents/spec-agent.md](.github/workshop/agents/spec-agent.md)
2. Replace the placeholder idea with your own
3. Run the prompt with the `Spec Agent`
4. Save the output as `spec-v1.md`

What to look for:

- clear target user
- clear workflow
- realistic scope
- explicit non-goals

## Block 2: Spec Review Agent

Goal: compare two models doing the same review task.

1. Open [.github/workshop/agents/spec-review-agent.md](.github/workshop/agents/spec-review-agent.md)
2. Run the exact same prompt twice with two different models
3. Save the outputs as `spec-review-a.md` and `spec-review-b.md`
4. Compare the reviews
5. Create `spec-v2.md` using the stronger review

What to look for:

- which model finds more useful gaps
- which model is clearer and more actionable
- which model overcomplicates the app

## Block 3: Build Agent

Goal: build a working first version with Microsoft Learn MCP grounding.

1. Open [.github/workshop/agents/build-agent.md](.github/workshop/agents/build-agent.md)
2. Point the agent at `spec-v2.md`
3. Tell the agent to create the app directly in this repository
4. Require it to consult `Microsoft Learn MCP` before making implementation choices
5. Keep the result functional and intentionally simple

What to look for:

- how the agent uses docs to guide technical choices
- whether the app stays aligned to the reviewed spec
- whether the app is demoable without extra setup

## Block 4: Design Agent

Goal: improve clarity and polish without changing the product scope.

1. Open [.github/workshop/agents/design-agent.md](.github/workshop/agents/design-agent.md)
2. Tell the agent to use the `zava-designer` skill
3. Ask it to retrieve Zava design guidance from `jhelin/designguidelines` through GitHub MCP
4. Ask it to use:
   - design rules from the external brand repo
   - approved logo or asset files from the external brand repo
   - any supporting design guidance issues in the external brand repo
4. Apply the changes in the app files created during Block 3

What to look for:

- what changed because of the skill
- what changed because of GitHub-grounded design context from `jhelin/designguidelines`
- whether the UI improved without changing app scope

## End Of Workshop Check

By the end, you should be able to explain:

- why the spec step matters
- why model choice matters
- how MCP improves authoring-time grounding
- how a skill changes agent behavior
- why different agents are useful for different jobs
