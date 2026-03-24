# designguidelines

This folder is a scaffold template for the design guidelines repository used in Block 4.

The published version of this repository is at `github.com/Jfhelin/zava-design-guidelines`.

Purpose:

- provide Zava design guidance through GitHub MCP during Block 4
- keep workshop brand/design artifacts outside the workshop repo
- make branding retrieval visible and deliberate

This repository is intended to be the source of truth for the workshop-defined Zava style. It is not presented as an official Microsoft or Zava brand repository.

## Repository Structure

The live repository contains:

- `README.md`
- `brand/zava-style.md`
- `brand/zava-ui-patterns.md`
- `brand/logo-usage.md`
- `brand/page-structure.md`
- `brand/tokens.json`
- `assets/logo-primary.png`
- `assets/logo-preview.jpg`
- `assets/logo-preview.md`

GitHub issues #1–#5 are already published in the live repo:

- #1 Zava Design Guidance
- #2 Zava Logo Usage
- #3 Zava Copy Tone
- #4 Zava Design Do Not Do
- #5 Zava Layout Blocks

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

1. Confirm `Jfhelin/zava-design-guidelines` is accessible via GitHub MCP
2. Confirm issues #1–#5 are published and readable via GitHub MCP
3. Confirm `assets/logo-primary.png` is retrievable
4. Confirm GitHub MCP can read both files and issues from the repo
