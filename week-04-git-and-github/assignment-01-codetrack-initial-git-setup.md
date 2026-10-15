# Assignment 1 — CodeTrack: Initial Git Setup (Local Only)

Part of the DevOps Micro Internship (DMI) with Agentic AI

---

## Purpose

In this assignment, you will set up Git correctly on your local machine before starting the CodeTrack project. You will create a local repository and configure your Git identity at both the repository level (local) and the machine level (global). This assignment is local only — you will not push anything to GitHub yet.

---

# Task 1 — Create the CodeTrack Project and Initialize Git

## Goal

Create a `CodeTrack` project folder and initialize it as a Git repository.

### Evidence

#### Screenshot 1 — Output of `git init` inside `CodeTrack` showing "Initialized empty Git repository"

<img width="2433" height="1151" alt="AdobeExpressPhotos_eba3aa38b62c4fa998ee9116a10621c2_CopyEdited" src="https://github.com/user-attachments/assets/566c2d9a-593d-428d-a2ca-c3342a39744f" />


---

#### Screenshot 2 — Output of `ls -a` showing the `.git` folder

<img width="2449" height="249" alt="AdobeExpressPhotos_d90683742ae24178a97939f6dcb34851_CopyEdited" src="https://github.com/user-attachments/assets/6ac2aae7-026a-4c0e-a009-faf145f10bb4" />


---

### Notes

**1. What is the `.git` folder, and why does it matter?**

The .git folder is a hidden directory created when we run the git init command. It stores important information about the Git repository, including commit history, configuration, branches, and other data required for version control. It matters because Git uses this folder to track changes and manage different versions of our project.

---

# Task 2 — Configure Git Identity Locally (Repository-Only)

## Goal

Set your Git username and email for the `CodeTrack` repository only, using `git config --local`.

### Evidence

#### Screenshot 3 — Output of `git config --local --list` showing your `user.name` and `user.email`

<img width="2487" height="528" alt="AdobeExpressPhotos_1cdc0ab1611845729c839953a75ca5c0_CopyEdited" src="https://github.com/user-attachments/assets/ffd3ff27-be89-4f89-b07e-d50a586d8ab9" />


---

# Task 3 — Configure Git Identity Globally

## Goal

Set a global Git username and email for this machine using `git config --global`. Note that CodeTrack's local settings still take priority over these.

### Evidence

#### Screenshot 4 — Output of `git config --global --list` showing your `user.name` and `user.email`

<img width="2445" height="379" alt="AdobeExpressPhotos_99f6cc2b47df44e48b74748cf3ac5cd0_CopyEdited" src="https://github.com/user-attachments/assets/774c07be-28a7-4417-a167-e28a6904b93a" />


---

# Submission Instructions

- Add all required screenshots in your submission
- Full Name must be visible in required screenshots
- Do not expose passwords, access tokens, or private keys

---

# Completion Checklist

- [✅] `CodeTrack` folder created and initialized as a Git repository (Screenshots 1–2)
- [✅] Explanation of the `.git` folder written in your own words
- [✅] Local `user.name` and `user.email` configured and verified (Screenshot 3)
- [✅] Global `user.name` and `user.email` configured and verified (Screenshot 4)
- [✅] No sensitive data exposed

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
