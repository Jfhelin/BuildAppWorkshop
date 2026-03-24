# Block 2: Spec Review Agent

> **Reading this in VS Code?** Press `Ctrl+Shift+V` (Windows / Linux) or `Cmd+Shift+V` (Mac) to open Markdown preview.

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

1. Open **Copilot Chat** and switch to **Agent mode**
2. Select the **2 Spec Review Agent**
3. Send this message:

   > "Review app-spec.md and produce a critique."

4. The agent will review `app-spec.md` using a structured rubric and produce a report
5. When it finishes, **rename or save the review output as `spec-review-a.md`**

> **Note:** The agent saves the review automatically. Check which file it created and rename it if needed.

---

## Step 2: Switch Models and Run the Review Again

1. In the Copilot Chat model picker, switch to a **different model** than the one you just used
2. Send the exact same message again:

   > "Review app-spec.md and produce a critique."

3. Save this output as `spec-review-b.md`

---

## Step 3: Compare the Two Reviews

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

   > "Apply findings 1, 2, and 4 from spec-review-a.md and update app-spec.md."

2. Review `app-spec.md` before moving on. It should now be:
   - More specific about the main screen and user interactions
   - Explicit about what data the app uses
   - Clear that there is no auth, no backend, no external services (or that any external API requires no key)
   - Scoped to things that can actually be built in 90 minutes

---

## What to Look for Before Moving On

- [ ] `app-spec.md` is more specific than when you started this block
- [ ] The core workflow describes actual screens and interactions, not just goals
- [ ] Constraints are explicitly stated in the spec
- [ ] The data section names the specific data the app needs
- [ ] No blocking issues remain from either review

---

## What You Learned in This Block

- How to use a review agent to find spec problems before they become code problems
- That different models have different strengths — specificity, risk detection, scope judgment
- How to produce a tighter, more actionable spec by iterating on a review
- Why the spec is worth spending time on before writing a single line of code

---

[Back: Block 1 — Spec](WORKSHOP-BLOCK-1.md) | [Next: Block 3 — Build](WORKSHOP-BLOCK-3.md)
