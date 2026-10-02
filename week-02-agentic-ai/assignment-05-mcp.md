# Assignment 5 — Connecting Claude to the Outside World

Part of the DevOps Micro Internship (DMI) with Agentic AI

---

## Purpose

In this assignment, you will connect Claude Code to external systems using MCP (Model Context Protocol). You will configure the GitHub MCP server, securely store credentials, verify the connection, and run a live query that proves Claude is accessing real-time GitHub data.

---

# Task 1 — Create a GitHub Personal Access Token

## Goal

Generate a GitHub Personal Access Token (PAT) that will be used for MCP authentication.

### Evidence

#### Screenshot 1 — GitHub token creation page showing the selected scopes (`repo`, `read:user`) — token value must NOT be visible

<img width="3783" height="2260" alt="Screenshot 2026-10-01 154031" src="https://github.com/user-attachments/assets/405c30c5-be22-4ecf-8a07-c1acb75cb6c9" />

<img width="2834" height="2245" alt="Screenshot 2026-10-01 154103" src="https://github.com/user-attachments/assets/10644d88-e654-4edd-bbf7-5c63b3e7322e" />

---

# Task 2 — Create .mcp.json at the Project Root

## Goal

Create and configure the `.mcp.json` file to define the GitHub MCP server.

### Evidence

#### Screenshot 2 — `.mcp.json` open in VS Code showing the full configuration

<img width="2935" height="1787" alt="Screenshot 2026-10-01 154550" src="https://github.com/user-attachments/assets/4660724d-60fd-46db-9edf-9a6cd557230c" />


---

# Task 3 — Add Your Token to settings.local.json

## Goal

Store your GitHub token securely in `.claude/settings.local.json` and ensure it is not committed to version control.

### Evidence

#### Screenshot 3 — `settings.local.json` open in VS Code showing the `env` section — **blur or cover the actual GitHub token value**

<img width="2919" height="1756" alt="Screenshot 2026-10-01 155115" src="https://github.com/user-attachments/assets/306172c1-0951-4ed7-af8e-76a25eb3080e" />


---

# Task 4 — Verify the Connection with /mcp

## Goal

Confirm that the GitHub MCP server is successfully connected inside Claude Code.

### Evidence

#### Screenshot 4 — `/mcp` output showing `github: connected`

<img width="2313" height="404" alt="Screenshot 2026-10-01 161433" src="https://github.com/user-attachments/assets/26f86257-0847-4672-9c1c-a346ccf837fc" />


---

# Task 5 — Run a Live GitHub Query

## Goal

Verify MCP functionality by retrieving real-time data from your GitHub account using Claude Code.

### Evidence

#### Screenshot 5 — Claude's response showing the GitHub MCP tool call and the retrieved README.md content.

<img width="2935" height="1787" alt="Screenshot 2026-10-01 154550" src="https://github.com/user-attachments/assets/ec446abd-a922-4590-8f63-f2fa6e094f09" />

---


# Submission Instructions

- Ensure `.mcp.json` is committed to your GitHub repository
- Ensure `.claude/settings.local.json` is NOT committed (must be gitignored)
- Confirm token value is hidden in all screenshots
- Add all required screenshots to your submission
- Push final changes to your forked repository

---

## GitHub Repository URL

Paste your forked repository URL here:

https://github.com/lavankumar1290-cyber/devops-micro-internship-pravinmishra

https://github.com/lavankumar1290-cyber/Ultimate-Agentic-DevOps-with-Claude-Code

---

## Security Confirmation

Confirm below:

- [✅] `settings.local.json` is added to `.gitignore`
- [✅] GitHub token is NOT exposed in repository or screenshots

---

# Completion Checklist

- [✅] GitHub PAT created with correct scopes (`repo`, `read:user`)
- [✅] `.mcp.json` created at project root
- [✅] `.claude/settings.local.json` contains token (hidden in screenshot)
- [✅] `.claude/settings.local.json` is NOT committed
- [✅] `/mcp` shows GitHub connection as active
- [✅] Live GitHub query returns real repository data
- [✅] All required screenshots added
- [✅] GitHub repository URL included
- [✅] MCP achievement shared on Facebook or WhatsApp Status
- [✅] Screenshot 6 added showing the published post/status

---

## 📌 About DMI & CloudAdvisory

DevOps Micro Internship (DMI) is a project-based DevOps program run by Pravin Mishra (The CloudAdvisory) focused on real-world execution, systems thinking, and career readiness.

It helps learners build strong DevOps foundations with hands-on experience.

---

## 📌 Resources

- 🌐 DMI Official Website: https://dmi.pravinmishra.com?utm_source=github&utm_medium=readme  
- 🎓 University: https://university.pravinmishra.com?utm_source=github&utm_medium=readme  
- 💬 Discord Community: https://discord.pravinmishra.com?utm_source=github&utm_medium=readme  
- 📝 Blog: https://dmi.pravinmishra.com/blog?utm_source=github&utm_medium=readme  
- ▶️ YouTube Playlist: https://www.youtube.com/playlist?list=PLFeSNDtI4Cho  
- 🔗 Pravin Mishra (LinkedIn): https://www.linkedin.com/in/pravin-mishra-aws-trainer/  
- 🏢 CloudAdvisory (LinkedIn): https://www.linkedin.com/company/thecloudadvisory/

---

*This submission is part of DevOps Micro Internship (DMI) — Agentic AI Track.*
