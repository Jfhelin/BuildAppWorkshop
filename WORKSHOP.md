# Workshop Guide

> **Reading this in VS Code?** Open this file in Markdown preview for the best experience.
> Press `Cmd+Shift+V` (Mac) or `Ctrl+Shift+V` (Windows / Linux).
> The preview opens as a split panel — drag its tab to the centre of the screen to make it full-width.

Welcome to the **Build App Workshop**. In this session you will plan, build, and polish a working web app entirely inside this repository — using GitHub Copilot agents, MCP connections, and the Zava design skill.

You do not need prior coding experience. Copilot does the heavy lifting. Your job is to describe what you want, review what comes back, and keep refining until it is right.

---

## What You Will Build

A small, fully local web app that runs in your browser. No server, no login, no infrastructure. Just open a file and it works.

The app will be grounded in realistic sample data, built from a clear spec, and styled to the Zava design language — all in about 90 minutes.

---

## What You Will Learn

| Block | Skill |
|-------|-------|
| [Block 1: Spec](WORKSHOP-BLOCK-1.md) | How to describe an app idea clearly and iterate on a spec with an agent |
| [Block 2: Spec Review](WORKSHOP-BLOCK-2.md) | How different models approach the same problem differently — and why that matters |
| [Block 3: Build](WORKSHOP-BLOCK-3.md) | How agents use external documentation (MCP) to make better technical decisions |
| [Block 4: Design](WORKSHOP-BLOCK-4.md) | How a design skill automatically applies a consistent visual language |

---

## Before You Start

Confirm each of these before opening Block 1:

- [ ] GitHub Copilot is enabled in VS Code
- [ ] **MCP servers are started** — open the Extensions view (`Ctrl+Shift+X` / `Cmd+Shift+X`), scroll to **MCP SERVERS - INSTALLED**, and confirm both `github` and `microsoft-learn` show a green running indicator. If they are stopped, click the start button next to each. VS Code will prompt you to trust each server the first time — select **Trust**.
- [ ] The `zava-designer` skill is visible in Copilot chat (type `/` to check)
- [ ] **Model is set to Claude Sonnet 4.6** — open Copilot Chat, click the model picker at the bottom of the chat panel, and select **Claude Sonnet 4.6** before starting Block 1

If any of these are missing, ask your facilitator before continuing.

---

## Ground Rules

These apply across all four blocks:

- **No auth.** The app will not have login screens or user accounts.
- **No backend.** Everything runs in the browser — no server to spin up, no database to configure.
- **Stay in the repo.** Create and edit files directly in this repository.
- **Keep it demoable.** If it cannot be shown in 90 minutes, it is out of scope.

---

## Start Here

Open [WORKSHOP-BLOCK-1.md](WORKSHOP-BLOCK-1.md) and begin.
