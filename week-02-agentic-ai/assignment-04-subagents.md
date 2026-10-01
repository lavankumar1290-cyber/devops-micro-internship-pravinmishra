# Assignment 4 — Building Your AI Team

Part of the DevOps Micro Internship (DMI) Cohort with Agentic AI

---

## Purpose

In this assignment, you will build and configure a set of specialized AI subagents inside your project. You will learn how different models and tool permissions define agent behavior, and you will trigger two real agent delegations to analyze security and cost aspects of your Terraform infrastructure.

---

# Task 1 — Create the Agents Folder and Add Files

## Goal

Create the `.claude/agents/` directory and add all required agent files.

### Evidence

#### Screenshot 1 — VS Code sidebar showing `.claude/agents/` with all 3 files

<img width="878" height="1452" alt="Screenshot 2026-10-01 140112" src="https://github.com/user-attachments/assets/7e365fe6-87cc-4b79-9c2d-277bd12c085f" />


---

# Task 2 — Compare the Agent Configurations

## Goal

Analyze the configuration differences between the three agents and demonstrate understanding of model and tool selection.

### Written Answers

#### 1. Why does the cost optimizer use Haiku instead of Sonnet?

The cost optimizer uses Haiku because cost analysis is usually a straightforward task. Haiku is faster and cheaper while still being capable of identifying unnecessary or expensive resources in Terraform infrastructure.

---

#### 2. Why does the security auditor NOT have Write in its tools list?

The security auditor does not have Write access to prevent it from accidentally changing the infrastructure. It should only read and analyze the Terraform code and report security issues, keeping the audit safe and controlled.

---

#### 3. Why does the tf-writer use `inherit` instead of a specific model?

The tf-writer uses inherit so it automatically uses the model configured by the parent/main agent. This avoids hard-coding a model and allows the writer to use whatever model is currently selected for the main session.

---

### Evidence

#### Screenshot 2 — `security-auditor.md` frontmatter showing model and tools configuration

<img width="2934" height="1485" alt="Screenshot 2026-10-01 141134" src="https://github.com/user-attachments/assets/4b227830-8a56-40db-857d-00c0877c5206" />


---

#### Screenshot 3 — `cost-optimizer.md` frontmatter showing the model and tools configuration

<img width="2853" height="1761" alt="Screenshot 2026-10-01 141236" src="https://github.com/user-attachments/assets/df469167-0d45-46b6-b886-7061aff600a5" />


---

# Task 3 — Run the Security Auditor

## Goal

Trigger the security auditor agent and analyze the generated security report for your Terraform infrastructure.

### Evidence

#### Screenshot 4 — The delegation message showing Claude launched the security-auditor

<img width="2377" height="902" alt="Screenshot 2026-10-01 141740" src="https://github.com/user-attachments/assets/95e2ab56-6a2d-4234-b394-75c21669a12b" />


---

#### Screenshot 5 — Security audit report output

<img width="2318" height="874" alt="Screenshot 2026-10-01 141940" src="https://github.com/user-attachments/assets/0eabfc65-35a4-4b51-b2bc-e40c304b148a" />


---

# Task 4 — Run the Cost Optimizer

## Goal

Trigger the cost optimizer agent and review the generated cost optimization report.

### Evidence

#### Screenshot 6 — The full cost optimization report

<img width="2355" height="857" alt="Screenshot 2026-10-01 142349" src="https://github.com/user-attachments/assets/6b07ee81-f574-4fb0-86b8-1a6a2cfd52ca" />


---

# Task 5 — Share Your AI Team Achievement on LinkedIn

## Goal

Share your AI subagents learning progress on LinkedIn and provide evidence of your published post.

### LinkedIn Post

Use the LinkedIn post template provided in the assignment guideline.

Make sure your published post includes:

- Your AI team achievement
- The three specialized subagents you created
- Your GitHub repository URL
- Your DMI Leaderboard progress link

### Evidence

#### Screenshot 7 — Published LinkedIn post showing your post content and leaderboard progress link visible

<img width="2806" height="2181" alt="Screenshot 2026-10-01 143039" src="https://github.com/user-attachments/assets/1bc3e784-fb7c-4f82-b5ae-556b4152f9bd" />


---

# Submission Instructions

- Ensure all agent files are committed in `.claude/agents/`
- Complete all written answers in your GitHub Repo
- Push final changes to your forked GitHub repository

---

## GitHub Repository URL

Paste your forked repository URL here:

https://github.com/lavankumar1290-cyber/devops-micro-internship-pravinmishra

https://github.com/lavankumar1290-cyber/Ultimate-Agentic-DevOps-with-Claude-Code

---

# Completion Checklist

- [✅] `.claude/agents/` folder contains all 3 agent files
- [✅] Screenshot 2 shows correct `security-auditor.md` configuration
- [✅] Screenshot 3 shows correct `cost-optimizer.md` configuration
- [✅] All 3 written answers completed 
- [✅] Security auditor executed successfully
- [✅] Cost optimizer executed successfully
- [✅] Security report is visible with findings
- [✅] Cost report is visible with recommendations
- [✅] All required screenshots added
- [✅] GitHub repo updated with agents


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
