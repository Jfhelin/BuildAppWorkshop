# Block 2: Spec Review Agent

> **Reading this in VS Code?** Press `Cmd+Shift+V` (Mac) or `Ctrl+Shift+V` (Windows / Linux) to open Markdown preview. Drag the preview tab to the centre of the screen to view it full-width.

**Goal:** Stress-test your spec before building. Find the gaps, ambiguities, and risks that would slow down or break the build — and apply the fixes directly to `app-spec.md` before handing it to the Build Agent.

This block also introduces one of the most useful Copilot insights: **different models produce meaningfully different outputs for the same task**. You will run the same review twice with two different models and compare the results.

Estimated time: **20–25 minutes**

---

## Why Review the Spec?

A spec that seems clear to you may be deeply ambiguous to a build agent. Common problems:

- The core workflow is described at a high level, but the screens and interactions are missing
- The data model is implied but never stated
- Constraints live in your head but not on the page
- Scope is too broad to build in 90 minutes

The Spec Review Agent finds these problems *before* the Build Agent runs into them. It is cheaper to fix a spec than to fix half-built code.

---

## Step 1: Run the Review With Your First Model

### What is a reusable prompt?

In Block 1, you used a **custom agent** — a fully configured assistant with its own name, tools, and role. Agents are powerful, but sometimes you just need to **replay a well-crafted prompt** without spinning up a whole persona. That is what **reusable prompts** are for.

A reusable prompt is a `.prompt.md` file stored in `.github/prompts/`. It contains a pre-written prompt — complete with instructions, rubrics, or output formats — that you can invoke in Copilot Chat with a single click instead of typing it from scratch every time. Think of it as a saved command you can reuse across conversations, models, and team members.

> Want to see how it works? Open [`.github/prompts/spec-review.prompt.md`](.github/prompts/spec-review.prompt.md) to read its contents. You can also read more about reusable prompts in the [VS Code documentation](https://code.visualstudio.com/docs/copilot/customization/prompt-files).

### Run the review

1. Open **Copilot Chat** in VS Code and switch to **Agent mode**
2. In the chat input, type `/` and select **spec-review** from the prompt picker
3. Press **Enter** to send the prompt — it will run the full review rubric automatically
4. When it finishes, **review the output `spec-review-<model-used>.md`**


---

## Step 2: Switch Models and Run the Review Again

1. In the Copilot Chat model picker, switch to a **different model** than the one you just used — try a model from a different provider for the most contrast. Good options:
   - **Google Gemini** (e.g. Gemini 2.5 Pro) — strong at structured analysis and spotting scope creep
   - **OpenAI GPT-5.4** — well-rounded; tends to be thorough on acceptance criteria gaps
   - Any other model available in the picker you have not used yet
2. In the chat input, type `/` and select **spec-review** again, then press **Enter** to send the prompt


---

## Step 3: Compare the different Reviews

Read both reviews side by side and look for:

| What to compare | Why it matters |
|----------------|----------------|
| **Findings count** | Does one model find more issues? Or just more noise? |
| **Specificity** | Does it tell you *where* the problem is, or just that a problem exists? |
| **Blockers identified** | Did both models flag auth, backend, or external API risks? |
| **Scope assessment** | Does one model push back harder on scope that is too large? |
| **Tone and clarity** | Which review would you rather hand to a colleague? |
| **Hallucinated features** | Did either model invent requirements that were never in the spec? |

There is no universally "better" model. What you are learning is that **model choice is a real decision** — not a default setting.

---

## Step 4: Apply the Fixes to app-spec.md

Use the stronger of the two reviews (or the best parts of both) to update the spec in place.

1. Still in the **2 Spec Review Agent**, send a follow-up message:

   > "Using the findings from the review, apply the top fixes to app-spec.md and update it in place."

   Or, if you want to guide which findings get applied:

   > "Apply findings 1, 2, and 4 from spec-review-<model-name>.md and update app-spec.md."

2. Review `app-spec.md` before moving on. It should now be:
   - More specific about the main screen and user interactions
   - Explicit about what data the app uses
   - Clear that there is no auth, no backend, no external services (or that any external API requires no key)
   - Scoped to things that can actually be built in 90 minutes
---

## What You Learned in This Block

- The core Copilot workflow repeated: **Copilot does the work → you review the output → you ask Copilot to fix it**. You did not edit `app-spec.md` directly — you described what needed to change and let the agent apply it. That pattern is the same whether you are writing a spec, reviewing code, or styling an app.
- That **model choice is a real decision**. The same prompt sent to two different models produces different findings, different prioritisation, and different blind spots. Choosing a model is not a preference — it changes the output in ways that matter.

---

[Back: Block 1 — Spec](WORKSHOP-BLOCK-1.md) | [Next: Block 3 — Build](WORKSHOP-BLOCK-3.md)
