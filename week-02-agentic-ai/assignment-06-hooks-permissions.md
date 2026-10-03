# Assignment 6 — Safety Rails for Your AI Agent

Part of the DevOps Micro Internship (DMI) with Agentic AI

---

## Purpose

In this assignment, you will configure safety and control mechanisms for Claude Code using permissions and hooks. You will define team-level command restrictions and implement prompt-level and tool-level hooks to prevent destructive actions before they execute.

---

# Task 1 — Create Claude Code Configuration Structure

## Goal

Create the `.claude` directory structure required for team-level Claude Code configuration.

### Evidence

#### Screenshot 1 — `.claude` folder structure visible in VS Code Explorer

<img width="1041" height="1321" alt="AdobeExpressPhotos_282ac3c6cc9644daa96a7b5669bb9043_CopyEdited" src="https://github.com/user-attachments/assets/f3b01028-0ebc-40f5-b0c9-b9a8e3af3662" />


---

# Task 2 — Create the UserPromptSubmit Hook Script

## Goal

Create a hook that checks user prompts before Claude processes them and blocks requests containing destructive intent.

### Evidence

#### Screenshot 2 — `user-prompt-guard.sh` open in VS Code showing the hook script

<img width="1036" height="1631" alt="AdobeExpressPhotos_0ca602d63adb47b390507210cb5d07ab_CopyEdited" src="https://github.com/user-attachments/assets/abe79216-1148-44d9-aac7-6fe5ead218fc" />


---

# Task 3 — Create the PreToolUse Hook Script

## Goal

Create a hook that runs before Claude executes Bash commands and blocks dangerous infrastructure commands.

### Evidence

#### Screenshot 3 — `pre-tool-guard.sh` open in VS Code showing the hook script

<img width="3163" height="1553" alt="AdobeExpressPhotos_ebc7de01045940cfbfd59bd4b5b438ff_CopyEdited" src="https://github.com/user-attachments/assets/04d7c1c4-7a96-45d2-9dc7-f9fe7e0b69e3" />


---

# Task 4 — Create the PostToolUse Hook Script

## Goal

Create a hook that runs after Claude executes a Bash command and logs selected Terraform commands.

### Evidence

#### Screenshot 4 — `post-tool-logger.sh` open in VS Code showing the hook script

<img width="2793" height="1549" alt="AdobeExpressPhotos_c2d00101f73c47be8749af608613043c_CopyEdited" src="https://github.com/user-attachments/assets/60732efa-34d5-4354-aeef-622ed326f8c5" />


---

# Task 5 — Configure settings.json to Connect Hook Scripts

## Goal

Configure Claude Code permissions and connect the hook scripts created in the previous tasks.

### Evidence

#### Screenshot 5 — `settings.json` open in VS Code showing permissions and hooks configuration

<img width="2597" height="1780" alt="AdobeExpressPhotos_5a0c6ace1e2d40a1947af91d7ab414fc_CopyEdited" src="https://github.com/user-attachments/assets/e37c83ed-5ed0-407d-abff-df6a63e77000" />


---

# Task 6 — Test the UserPromptSubmit Hook

## Goal

Prove the prompt-level hook works by typing a destructive prompt and verifying it is blocked before Claude processes the request.

### Evidence

#### Screenshot 6 — UserPromptSubmit hook blocking the destructive prompt
<img width="3492" height="1397" alt="AdobeExpressPhotos_7aecda3ca3014bee9472101bc4f267ff_CopyEdited" src="https://github.com/user-attachments/assets/0a5ced5a-9166-48d5-bc9a-832b1301718c" />

---

# Task 7 — Test the PreToolUse Hook

## Goal

Prove the tool-level hook works by asking Claude to execute a dangerous Bash command.

### Evidence

#### Screenshot 7 — PreToolUse hook blocking terraform destroy
<img width="2890" height="2206" alt="AdobeExpressPhotos_7f37e1ff3614465cb66c34f7f9a89e2b_CopyEdited" src="https://github.com/user-attachments/assets/a1db34f1-6607-46e2-8121-a88c7c8a040b" />

---

# Task 8 — Test the PostToolUse Logging Hook

## Goal

Prove the logging hook runs after a successful command execution and records Terraform operations.

### Evidence

#### Screenshot 8 — Claude running terraform validate successfully

#### Screenshot 9 — `.claude/deploy.log` showing the logged command

---

# Task 9 — Share Your AI Safety Achievement

## Goal

Share how you built safety controls that prevent an AI agent from performing destructive actions.

### Evidence

#### Screenshot 10 — Published post on X or LinkedIn showing your AI safety achievement message and leaderboard progress link visible

Add your screenshot here.

---

# Submission Instructions

Complete all tasks in sequence.

Your submission must include:
- All 10 required screenshots

---

# Completion Checklist

- [ ] `.claude` folder structure created correctly
- [ ] `user-prompt-guard.sh` created with UserPromptSubmit hook logic
- [ ] `pre-tool-guard.sh` created with PreToolUse hook logic
- [ ] `post-tool-logger.sh` created with PostToolUse logging logic
- [ ] `settings.json` created with allow and deny permissions
- [ ] `settings.json` configured to connect all three hooks:
  - [ ] UserPromptSubmit
  - [ ] PreToolUse
  - [ ] PostToolUse
- [ ] Destructive prompt test shows UserPromptSubmit blocked the request
- [ ] Terraform destroy command test shows PreToolUse intercepted the command
- [ ] Terraform validate test shows PostToolUse created the log entry
- [ ] AI safety achievement shared on X or LinkedIn
- [ ] Screenshot of published post with leaderboard progress link visible
- [ ] All required screenshots are captured

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
