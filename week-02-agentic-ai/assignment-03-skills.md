# Assignment 3 — Building Your Command Center

Part of the DevOps Micro Internship (DMI) Cohort 3 with Agentic AI

---

## Purpose

In this assignment, you will build a local Claude Skills system by creating the `.claude/skills/` folder structure, adding predefined skill files, and executing a real agentic command (`/scaffold-terraform`) to generate infrastructure code. You will also observe how skills enforce tool restrictions and enable controlled automation.

---

# Task 1 — Create the Skill Folder Structure

## Goal

Create the required `.claude/skills/` directory structure for all skills.

### Evidence

#### Screenshot 1 — VS Code sidebar showing `.claude/skills/` folder with all 4 subfolders visible

<img width="1600" height="2177" alt="image" src="https://github.com/user-attachments/assets/6fc44d64-326a-4b0e-925a-3c202de92aa1" />




---

# Task 2 — Add the Skill Files

## Goal

Place all required skill files into their correct directories and verify their configuration.

### Evidence

#### Screenshot 2 — `.claude/skills/scaffold-terraform/` open in VS Code showing both `SKILL.md` and `template-spec.md`

<img width="898" height="1100" alt="AdobeExpressPhotos_539650525ba446fd931bcb37b2e1bd44_CopyEdited" src="https://github.com/user-attachments/assets/f3de2025-51e2-4ec3-99c7-8bd1d544f1e4" />


---

#### Screenshot 3 — Screenshot 3 — `tf-plan/SKILL.md` frontmatter showing `allowed-tools: Bash, Read, Grep` (no Write) and `disable-model-invocation: true`

<img width="2545" height="1843" alt="image" src="https://github.com/user-attachments/assets/511da28f-a0cb-401d-9cb4-b86514a0ffaa" />

---

# Task 3 — Run /scaffold-terraform

## Goal

Execute the `/scaffold-terraform` skill to generate a full Terraform infrastructure setup.

### Evidence

#### Screenshot 4 — Claude's response showing the scaffold complete with the file list

<img width="2143" height="927" alt="AdobeExpressPhotos_e73b4795f8ef43debbc7d8559de5afa2_CopyEdited" src="https://github.com/user-attachments/assets/3dd9ea47-6e32-4471-9783-f9054b79c036" />


---

#### Screenshot 5 — VS Code sidebar showing the `terraform/` folder with all generated files inside

<img width="2509" height="1409" alt="AdobeExpressPhotos_b6934394869146e09088da1b950f14c3_CopyEdited" src="https://github.com/user-attachments/assets/0c30b056-593f-4320-83cd-e8cb1d2d0f23" />


---

# Task 4 — Run terraform init and /tf-plan

## Goal

Initialize Terraform and execute the `/tf-plan` skill to observe plan execution and output analysis.

### Evidence

#### Screenshot 6 — Claude's `/tf-plan` response showing it ran the command and analyzed the result (pass or auth error both count)

<img width="1339" height="2051" alt="AdobeExpressPhotos_75b910e389c3423187454ed6d5776390_CopyEdited" src="https://github.com/user-attachments/assets/dd6465c4-a936-42e7-bb9d-ec9a65934d0c" />


---

# Submission Instructions

- Ensure `.claude/skills/` folder and all skill files are committed to your GitHub repository
- Run all commands successfully and capture required screenshots
- Push final changes to your forked repository

---

## GitHub Repository URL

Paste your forked repository URL here:

`Add your URL here`

## LinkedIn post URL

Paste your forked repository URL here:

`Add your URL here`
---

# Completion Checklist

- [ ] `.claude/skills/` folder created with all 4 skill folders
- [ ] All skill files placed correctly
- [ ] `tf-plan/SKILL.md` shows correct `allowed-tools` restrictions
- [ ] `/scaffold-terraform` executed successfully
- [ ] Terraform files generated inside `terraform/` folder
- [ ] `terraform init` executed successfully
- [ ] `/tf-plan` executed and output analyzed by Claude
- [ ] All required screenshots added
- [ ] GitHub repository URL included
- [ ] LinkedIn post URL included

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

*This submission is part of DevOps Micro Internship (DMI) Cohort 3 — Agentic AI Track.*
