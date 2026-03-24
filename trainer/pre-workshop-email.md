# Pre-Workshop Email Template

Send this email 2–3 days before the workshop. Adjust the placeholders in `[brackets]` before sending.

---

**Subject:** Getting ready for the GitHub Copilot Workshop — action needed before [DATE]

---

Hi [NAME / team],

Looking forward to seeing you at the GitHub Copilot Workshop on **[DATE]** at **[TIME]**. This is a hands-on session where you will build a working web app from scratch using Copilot agents — no prior coding experience needed.

To make the most of the session, please complete the setup steps below **before you arrive**. The workshop moves quickly and we will not have time to troubleshoot installations on the day.

---

## What You Will Need

- **Visual Studio Code** — [download here](https://code.visualstudio.com/)
- **A GitHub account** with access to GitHub Copilot
- **The GitHub Copilot extension** installed in VS Code

---

## Setup Steps

### 1. Install VS Code and the Copilot extension

If you do not already have VS Code, download and install it from [code.visualstudio.com](https://code.visualstudio.com/).

Then install the **GitHub Copilot** extension:
1. Open VS Code
2. Go to the Extensions panel (press `Ctrl+Shift+X` / `Cmd+Shift+X`)
3. Search for **GitHub Copilot** and install it
4. Sign in with your GitHub account when prompted

### 2. Confirm Copilot Chat is working

1. Open the Copilot Chat panel in VS Code (press `Ctrl+Alt+I` / `Cmd+Shift+I`)
2. Type a simple question like "What is a variable?" and confirm you get a response
3. Click the **model picker** at the bottom of the chat panel and confirm you can see **Claude Sonnet 4.6** in the list — select it as your default model for the workshop

### 3. Configure GitHub MCP

GitHub MCP lets Copilot retrieve content from GitHub repositories at authoring time. We use it to ground the app build with real sample data and design guidelines.

To configure it:
1. Open VS Code Settings (`Ctrl+,` / `Cmd+,`)
2. Search for **MCP** and follow the setup steps for **GitHub MCP**

If you are unsure how to set this up, [follow the official guide](https://code.visualstudio.com/docs/copilot/chat/mcp-servers) or ask your IT contact. Your GitHub account credentials are all that is needed.

### 4. Configure Microsoft Learn MCP

This MCP connection lets Copilot consult official Microsoft documentation when making technical decisions.

Set it up the same way as GitHub MCP, selecting **Microsoft Learn** as the source. If your environment does not support it, let us know before the session — it is used in Block 3 but is not strictly required to participate.

### 5. Clone the workshop repository

The workshop takes place entirely inside a GitHub repository. You will receive the repository link separately — clone it to your local machine before the session:

```
git clone [WORKSHOP REPO URL]
```

Open the cloned folder in VS Code.

---

## On the Day

- Bring your laptop with VS Code open and the workshop repository loaded
- Have your GitHub account signed in to Copilot before you arrive
- We start promptly at **[TIME]** — aim to arrive 10 minutes early if you can

No other prep is needed. We will walk through everything together in the session.

---

If you run into any issues with the setup, reply to this email before **[DATE - 1 day]** and we will help you sort it out.

See you on [DATE],

[YOUR NAME]
[YOUR CONTACT / TEAM]
