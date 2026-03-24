# Facilitator Guide

## Objective

Teach ATS how to explain and demonstrate `agents`, `spec quality`, `model selection`, `MCP grounding`, and `skills` through a single app-building experience.

## Timing

- `0-10 min`: framing, setup check, agent overview
- `10-25 min`: Block 1, spec draft
- `25-40 min`: Block 2, review and model comparison
- `40-65 min`: Block 3, build with Learn MCP
- `65-80 min`: Block 4, design polish with skill and GitHub grounding
- `80-90 min`: demos and ATS talk track

## Trainer Talk Track

### Opening

- The point is not to memorize commands.
- The point is to show how Copilot gets better when work is structured.
- Each block adds one capability to the flow rather than starting from scratch.

### Block 1: 1 Spec Agent

Trainer intro:
- introduce role-based agents
- explain that the first output is a draft, not a finished plan
- keep participants on small app ideas

Participant action:
- open [.github/agents/1-spec-agent.agent.md](../.github/agents/1-spec-agent.agent.md)
- create `app-spec.md` using their chosen app idea

Debrief:
- show how strong specs include target users, workflows, constraints, and non-goals
- point out that the spec agent does not use MCP yet

### Block 2: 2 Spec Review Agent

Trainer intro:
- different models are good at different jobs
- review work is one of the easiest places to compare models side by side

Participant action:
- run [.github/agents/2-spec-review-agent.agent.md](../.github/agents/2-spec-review-agent.agent.md) twice with two models
- save outputs as `spec-review-a.md` and `spec-review-b.md`
- apply the top fixes from the stronger review to `app-spec.md` in place

Debrief:
- ask which model produced better critique and why
- reinforce that the best model depends on the task

### Block 3: 3 Build Agent with Learn MCP

Trainer intro:
- MCP is authoring-time grounding, not runtime app integration
- the build agent should consult trusted platform guidance before implementation

Participant action:
- run [.github/agents/3-build-agent.agent.md](../.github/agents/3-build-agent.agent.md)
- require the build agent to consult Microsoft Learn MCP before making implementation choices
- keep design minimal in this stage

Debrief:
- ask how the build output changes when the agent grounds itself in docs instead of guessing

### Block 4: Zava Design Skill with GitHub Grounding

Trainer intro:
- a skill fires automatically — the participant does not select an agent or mention Zava
- the moment Copilot sees a UI request, the `zava-designer` skill activates
- MCP gives Copilot trusted design and brand context from a live GitHub repository
- the design phase should improve the interface without rewriting the product
- Zava styling is grounded from a separate GitHub repository, not this workshop repo

Participant action:
- stay in default Agent mode — no custom agent to select
- send a plain prompt: "Apply the Zava design language to the app."
- watch the `zava-designer` skill activate automatically in the chat response
- have Copilot retrieve files and issues from `Jfhelin/zava-design-guidelines` through GitHub MCP

Debrief:
- ask what came from the skill versus what came from GitHub MCP content
- emphasize the separation:
  - skill shapes behavior and carries the rules
  - MCP supplies live source material
  - the model executes — no custom agent needed

## Recommended App Categories

- visit prep tool
- onboarding checklist
- issue triage dashboard
- meeting action tracker
- lightweight request intake app

## Trainer Prep Checklist

- publish the issue seeds from [github-issues](github-issues) into GitHub
- create and publish the separate design repo from [designguidelines-repo-template](designguidelines-repo-template)
- confirm the design skill is installed in the participant environment
- confirm GitHub MCP can reach `Jfhelin/zava-design-guidelines`
- dry-run the lab once in a clean environment

## ATS Wrap-Up Narrative

- start with a spec, not just a prompt
- use a review step before building
- choose the model for the task
- ground implementation with trusted context through MCP
- use skills to make outcomes more repeatable and brand-safe
