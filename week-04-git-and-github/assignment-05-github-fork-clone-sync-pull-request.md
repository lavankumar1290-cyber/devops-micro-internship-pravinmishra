# Assignment 5 — Open-Source Collaboration: Fork, Clone, Sync & Pull Request

Part of the DevOps Micro Internship (DMI) with Agentic AI

---

## Purpose

In this assignment, you will contribute one small documentation change to a shared repository using a standard open-source collaboration workflow: fork, clone, configure remotes, branch, commit, sync with upstream, push, and open a Pull Request. This is a different, separate practice repository from the one you submit your DMI work in.

---

# Task 0 — Fork the Upstream Repository

## Goal

Fork `pravinmishraaws/devops-micro-internship-interviews` into your own GitHub account.

### Evidence

#### Screenshot 1 — Your fork page with your username and `devops-micro-internship-interviews` visible in the browser URL

<img width="2799" height="2205" alt="Screenshot 2026-10-23 160750" src="https://github.com/user-attachments/assets/3ad255c7-dadc-466e-a610-1d4f5fd35ac8" />


---

# Task 1 — Authenticate GitHub from the Terminal

## Goal

Configure one authentication method — HTTPS with a Personal Access Token, or SSH — so you can push to your fork. Use only one method.

### Evidence

#### Screenshot 2 — Output of `git config --global --get credential.helper` (HTTPS) or `ssh -T git@github.com` (SSH) showing successful authentication — never show your token or private key

<img width="3764" height="1189" alt="Screenshot 2026-10-23 162347" src="https://github.com/user-attachments/assets/dba56ca0-f73e-4f11-9c59-1aebfa5cf524" />


---

# Task 2 — Clone Your Fork and Configure Remotes

## Goal

Clone your fork locally, then add the original repository as `upstream`.

### Evidence

#### Screenshot 3 — Output of `git remote -v` showing `origin` pointing to your fork and `upstream` pointing to `pravinmishraaws/devops-micro-internship-interviews`

<img width="2607" height="1585" alt="image" src="https://github.com/user-attachments/assets/3a0f2b0e-b2be-436c-8c34-c5a6bb16fcaa" />


---

# Task 3 — Create a Feature Branch and Make Your Change

## Goal

Create the branch `feature-readme-update`, add only your own entry (`Full Name — Group <Group Name/Number>`) to the Student List at the end of `pull_request.md`, and commit it with the message `docs: add my name to student list`.

### Evidence

#### Screenshot 4 — Output of `git status` showing `pull_request.md` modified before staging

<img width="2600" height="935" alt="image" src="https://github.com/user-attachments/assets/26bc3e1c-8020-46c7-8a8e-d1cf36394ae6" />


---

#### Screenshot 5 — Output of `git commit`

<img width="2360" height="313" alt="image" src="https://github.com/user-attachments/assets/bd6f7a04-7666-4d8b-bb5b-4849140b6055" />


---

# Task 4 — Synchronize with Upstream and Push to Your Fork

## Goal

Fetch and merge `upstream/main` into your local default branch, rebase your feature branch onto it, then push `feature-readme-update` to your fork.

### Evidence

#### Screenshot 6 — Output of `git push -u origin feature-readme-update` showing a successful push

<img width="2112" height="433" alt="AdobeExpressPhotos_f2302ab61ec44069b081b95ad2839758_CopyEdited" src="https://github.com/user-attachments/assets/9c9b5a6d-d92d-4d60-91ca-094acbec30b4" />


---

#### Screenshot 7 — Your fork on GitHub showing `feature-readme-update` in the branch selector or a "Compare & pull request" banner

<img width="3817" height="2128" alt="AdobeExpressPhotos_486c3fa7a6c449a0a906a2cea50e03fc_CopyEdited" src="https://github.com/user-attachments/assets/129d077d-52fd-473b-ba38-e94dc3d2006f" />


---

# Task 5 — Create a Pull Request to Upstream

## Goal

Open a Pull Request from `feature-readme-update` on your fork to `main` on the upstream repository, using the title `docs: add my name to student list`.

### Evidence

#### Screenshot 8 — Pull Request creation page showing the correct base repository, base branch, head repository, compare branch, and title

<img width="3752" height="808" alt="AdobeExpressPhotos_e8a73c476f164f698032c671c96ce089_CopyEdited" src="https://github.com/user-attachments/assets/f913068b-ffe0-453d-b0e8-9fc46fdd1a47" />


---

#### Screenshot 9 — Successfully created Pull Request page with the PR number visible

<img width="3816" height="2258" alt="AdobeExpressPhotos_c99201fd1bea43c68bd20c8778e53b0a_CopyEdited" src="https://github.com/user-attachments/assets/836a8b58-d1b8-4679-9ee4-e916590f14db" />


---

#### Pull Request URL

Paste your Pull Request URL here:

devops-micro-internship-interviews/pull/#500

---

# LinkedIn Post (Required)

## Evidence

#### LinkedIn Post URL

Paste your LinkedIn post URL here:

https://www.linkedin.com/posts/lavan-kumar-aa2724307_devops-git-github-share-7520365658463825920-qDz3/?utm_source=share&utm_medium=member_desktop&rcm=ACoAAE49RxoBGxFraCVYmiQyDbk76Ur65n4P1Kk

---

#### Screenshot — LinkedIn post showing your successfully created Pull Request

<img width="1821" height="2113" alt="AdobeExpressPhotos_11eb19b375f549d99780aa497eb35004_CopyEdited" src="https://github.com/user-attachments/assets/0ce86a50-8cd7-4152-9da2-09ac77d674fe" />


---

# Submission Instructions

- Add all required screenshots in your submission
- Do not expose a Personal Access Token, SSH private key, password, or authentication secret
- Only your own entry in `pull_request.md` may be added — do not edit or delete another student's entry
- Include your fork URL and Pull Request URL

---

## Fork URL

Paste your fork URL here:

https://github.com/lavankumar1290-cyber/devops-micro-internship-interviews

---

# Completion Checklist

- [✅] Upstream repository forked to your GitHub account (Screenshot 1)
- [✅] GitHub authentication configured securely (Screenshot 2)
- [✅] Fork cloned locally with `origin` and `upstream` configured (Screenshot 3)
- [✅] Only `pull_request.md` modified, with your own entry added (Screenshots 4–5)
- [✅] Local default branch synchronized with `upstream/main`, feature branch rebased and pushed (Screenshots 6–7)
- [✅] Pull Request opened against the correct upstream repository and branch (Screenshots 8–9)
- [✅] Fork URL and Pull Request URL included
- [✅] LinkedIn post published and URL submitted
- [✅] No PAT, password, private key, or authentication secret exposed

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
