# designguidelines

This folder is a scaffold for the separate public GitHub repository `github.com/jhelin/designguidelines`.

Purpose:

- provide Zava design guidance through GitHub MCP during Block 4
- keep workshop brand/design artifacts outside the workshop repo
- make branding retrieval visible and deliberate

This repository is intended to be the source of truth for the workshop-defined Zava style. It is not presented as an official Microsoft or Zava brand repository.

## Repository Structure

- `README.md`
- `brand/zava-style.md`
- `brand/zava-ui-patterns.md`
- `brand/logo-usage.md`
- `brand/tokens.json`
- `assets/logo-primary.svg`
- `assets/logo-mark.svg`
- `assets/hero-01.svg`
- `assets/logo-preview.md`
- `issues/seed/01-zava-design-guidance.md`
- `issues/seed/02-zava-logo-usage.md`
- `issues/seed/03-zava-copy-tone.md`
- `issues/seed/04-zava-do-not-do.md`

## How This Repo Is Used In The Workshop

- participants use the `zava-designer` skill
- the design agent retrieves design files and issues via GitHub MCP
- prompts like `add a logo` should cause the agent to fetch the approved logo and usage rules from this repo before editing the app

## Visual Direction

This repository defines Zava in a way that matches the provided workshop references:

- bright azure-blue branding
- rounded, approachable logo treatment
- light application surfaces
- clean cards, forms, and account-style layouts
- friendly but professional tone
- accessible contrast with restrained accent usage

## Publish Steps

1. Create `github.com/jhelin/designguidelines`
2. Copy the contents of this scaffold into that repository
3. Add the real approved Zava assets
4. Publish the seed issue files as GitHub issues
5. Confirm GitHub MCP can read both files and issues from the repo
