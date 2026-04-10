# GitHub Copilot Workshop Trainer Speaking Script

## Opening Welcome and Setup

Welcome to today's session.

Today we are going to use GitHub Copilot to build an application from start to finish.

This workshop is for non-developers, so the focus is not on reading code or writing code by hand. The focus is on how to structure the work, how to review what Copilot gives you, and how different Copilot capabilities change the result.

Thanks for being part of this. We are testing this format before rolling it out more broadly in EMEA, so after the session we will ask for feedback on the format, content, and pacing.

This workshop is split into four blocks. Each block adds one capability to the same flow rather than starting over each time.

We will start by creating a spec for a small app.
Then we will review that spec with different models to see how model choice changes the output.
After that, we will build the app with Microsoft Learn MCP and GitHub MCP grounding.
Finally, we will apply a design skill to polish the UI without changing functionality.

## Short Spoken Setup Checklist

Before we start, please check four things.

You have VS Code installed.
GitHub Copilot is enabled.
You can open Copilot Chat.
You are ready to work inside the BuildAppWorkshop repository in VS Code.

If you have not cloned the repository yet, open Copilot Chat and ask it to clone the BuildAppWorkshop (https://github.com/Jfhelin/BuildAppWorkshop) repository and open it in VS Code.

For this workshop, do not worry about memorizing git commands.

## Ground Rules

Before we start Block 1, keep these boundaries in mind.

The app should stay small.
It should run locally in the browser.
No auth.
No backend.
If it cannot be demoed in a few minutes, it is too big for this session.

## Block 1: Spec

In the first block, your job is to turn a small app idea into a buildable spec.

Open [WORKSHOP-BLOCK-1.md](../WORKSHOP-BLOCK-1.md).
Switch to the 1 Spec Agent.
Describe your app idea in plain language.
Let the agent create `app-spec.md`.
Then review it and keep iterating until it is concrete enough to build.

Two things matter here.

Keep the app idea small and demoable.
Treat the first output as a draft, not a finished answer.

The goal of this block is not to write the perfect prompt.

The goal is to get to a spec that clearly describes the user, the workflow, the data, the constraints, and what is out of scope.

I will show you my example first, and then I will give you about 20 minutes to work on your own.


## Block 1 retro

In the Spec block we used a custom agent. A custom agent is a version of Copilot that has been configured for a specific job. In this case, that job is turning an app idea into a structured spec.

The important point is that the first output is a draft.

The value comes from reviewing it and asking for improvements until the spec app is concrete, scoped, and complete.

Note that this agent is not using MCP yet. At this stage, this is just structured thinking and iteration.

## Block 2: Review and Model Comparison

In this block, your job is to stress-test the spec before you build anything.

Open [WORKSHOP-BLOCK-2.md](../WORKSHOP-BLOCK-2.md).
In Copilot Chat, type `/` and run the `spec-review` reusable prompt twice with two different models.
Compare the two critiques.
Then apply the best fixes back into `app-spec.md`.

The reusable prompt lives in `.github/prompts/spec-review.prompt.md`.
Each run should save its output as `spec-review-<model-name>.md` so participants can compare them side by side.

Do not just count how many issues each model found.

Look at the quality of the review.
Which model was more specific?
Which one found real blockers?
Which one invented things that were never in the spec?

This is where model choice becomes visible. Different models are better at different jobs, and review work is one of the clearest places to see that.

Let's work on this for about 20 minutes and then come back together.


## Block 2 retro

Hopefully you were able to try two different models for the review.

The point of this block is to show that not all models are the same. Some are better at critique and analysis, which is exactly what we need for reviewing a spec.

By comparing the outputs, you can see how model choice changes the improvements you make.

Sometimes the best result comes from combining the strongest parts of two different reviews instead of trusting one model blindly.


## Block 3: Build With Microsoft Learn MCP

In this block, your job is to build a working first version of the app from `app-spec.md`.

Open [WORKSHOP-BLOCK-3.md](../WORKSHOP-BLOCK-3.md).
Switch to the 3 Build Agent.
Ask it to implement the app from `app-spec.md`.
Then watch what it grounds on, run the app, and verify the result against the spec.

This is also where we introduce MCP grounding more explicitly.

In this workshop there are two MCP sources in play.
Microsoft Learn MCP gives implementation guidance.
GitHub MCP provides realistic sample data when the scenario fits.

The important distinction is that this is authoring-time grounding, not runtime integration.

The app itself should still run locally without depending on those MCP sources at runtime.

While the agent is working, pay attention to what sources it consults, what technical decisions it makes, and what design work it leaves for Block 4.

Let's work on this for about 30 minutes and then come back together.

## Block 3 retro

Hopefully you now have a working version of your app.

The key takeaway from this block is that grounding the work in live, relevant information usually leads to better results.

Microsoft Learn MCP helps the agent make implementation choices based on current guidance instead of guesswork, and GitHub MCP can provide more realistic sample data.

## Block 4: Zava Design Skill With GitHub Grounding

In this final block, your job is to improve the interface without changing how the app works.

Open [WORKSHOP-BLOCK-4.md](../WORKSHOP-BLOCK-4.md).
Stay in default Agent mode.
Do not select a custom agent.
Ask Copilot to apply the Zava design language to the app.
Then watch what activates and what it retrieves.

This block is where we make the difference between agents, skills, and MCP very explicit.

Up to now, you have been selecting custom agents for specific jobs.
In this block, you do not switch agents.
Instead, the `zava-designer` skill should activate automatically when Copilot detects UI work.

The skill carries the design rules and behavior.
GitHub MCP supplies the live brand guidance and assets.
The model then uses both to make the changes.

That separation matters, because it shows that the behavior and the source material are not the same thing.

## Block 4 retro and Closing

Hopefully you were able to build and design a polished version of your app.

The key takeaway from this block is that skills are a modular way to shape how Copilot behaves for a certain kind of task, while MCP provides live context that the model can ground on.

When we close, I want you to leave with five ideas.

Start with a spec, not just a prompt.
Review before you build.
Choose the model for the task.
Ground implementation with trusted context.
Use skills to make outcomes more repeatable.

Thank you all for participating in this workshop.

I hope it gave you a useful introduction to working with GitHub Copilot.

Please look out for the feedback email afterward. We would love to hear what worked, what did not, and what we should improve for the next run.