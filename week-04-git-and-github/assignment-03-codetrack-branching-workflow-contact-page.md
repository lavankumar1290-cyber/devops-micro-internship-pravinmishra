# Assignment 3 — CodeTrack: Branching Workflow (Add & Verify a Contact Page)

Part of the DevOps Micro Internship (DMI) with Agentic AI

---

## Purpose

In this assignment, you will add a new Contact page to CodeTrack using a clean feature-branch workflow. You will keep each change in a separate commit, prove that your default branch remains unchanged before the merge, and validate the result after merging.

---

# Task 1 — Confirm Repository State and Default Branch

## Goal

Start from a clean default branch (`main` or `master`) and confirm the repository status.

### Evidence

#### Screenshot 1 — Output of `git status` and `git branch` showing a clean status and the default branch checked out

<img width="3204" height="353" alt="AdobeExpressPhotos_81fac46732e9468a8d4eb24c5982b689_CopyEdited" src="https://github.com/user-attachments/assets/9056a0c0-bf7d-4faa-9dd9-b5f977fcf914" />


---

# Task 2 — Create and Switch to a Feature Branch

## Goal

Create a branch named exactly `feature/contact-page` and switch to it.

### Evidence

#### Screenshot 2 — Output of `git checkout -b feature/contact-page` and `git branch` showing `* feature/contact-page`

<img width="2054" height="413" alt="AdobeExpressPhotos_485c25f57b5746d784bb518c0875ebad_CopyEdited" src="https://github.com/user-attachments/assets/99a0b0b5-a231-4c00-8157-de15444a956b" />


---

# Task 3 — Add contact.html on the Feature Branch

## Goal

Create `contact.html` with the provided content and commit it alone using the message `feat(contact): add Contact page`.

### Evidence

#### Screenshot 3 — Output of `ls` showing `contact.html`

<img width="2072" height="321" alt="AdobeExpressPhotos_b005dbdfa5684f7a8105c93927097156_CopyEdited" src="https://github.com/user-attachments/assets/3a77c212-aeb3-4628-892f-9c21b6b65b12" />


---

#### Screenshot 4 — Output of `git commit`

<img width="2043" height="715" alt="AdobeExpressPhotos_cede2400f58b446f913f546cd88e631b_CopyEdited" src="https://github.com/user-attachments/assets/cb8eb95d-5643-4bf7-a26d-0a6eb156e204" />


---

#### Screenshot 5 — Output of `git log --oneline -3` showing the new commit

<img width="2059" height="387" alt="AdobeExpressPhotos_242dbe736e50433b8d9b954c0554336a_CopyEdited" src="https://github.com/user-attachments/assets/3bb88ba0-e0f3-4f87-a4b9-6c84b57f2507" />


---

# Task 4 — Add the Contact Link to index.html

## Goal

Add the provided Contact Page link to `index.html` and commit it separately using the message `feat(nav): add Contact Page link`.

### Evidence

#### Screenshot 6 — Output of `git status` showing `index.html` as modified before staging

<img width="2084" height="508" alt="AdobeExpressPhotos_995e725bf74a4d639b9bc786362878a0_CopyEdited" src="https://github.com/user-attachments/assets/dd1a903b-5ee6-41ca-9ba7-1e0b4d34b6db" />


---

#### Screenshot 7 — Output of `git commit`

<img width="2062" height="363" alt="AdobeExpressPhotos_e3fd1d3c97234ffb9328b3bb0f7d907b_CopyEdited" src="https://github.com/user-attachments/assets/b9138873-1b55-4e53-8b8e-258d3c228509" />


---

#### Screenshot 8 — Browser showing the Contact Page link on the homepage while on `feature/contact-page`

<img width="3645" height="2254" alt="AdobeExpressPhotos_3031e590dba049299ba2e3836160c35f_CopyEdited" src="https://github.com/user-attachments/assets/4fb990d9-6076-4642-8cbc-29b4bc0442a2" />


---

# Task 5 — Verify Isolation (Prove the Default Branch Is Unchanged)

## Goal

Switch back to the default branch and confirm that `contact.html` and the Contact Page link do not exist there yet.

### Evidence

#### Screenshot 9 — Terminal showing the checkout and `ls` output, proving `contact.html` is absent

<img width="2064" height="851" alt="AdobeExpressPhotos_853f86c75f74488fa83e88d27488dbe8_CopyEdited" src="https://github.com/user-attachments/assets/7a53613f-0bcf-416d-a54f-e1c2f5e03502" />


---

#### Screenshot 10 — Browser showing the homepage on the default branch with no Contact Page link

<img width="3640" height="2252" alt="AdobeExpressPhotos_ce01be32a1db4df7b79547adefa44499_CopyEdited" src="https://github.com/user-attachments/assets/7ad30911-af44-4696-9024-c565c4f987fa" />


---

# Task 6 — Merge the Feature Branch into the Default Branch

## Goal

Merge `feature/contact-page` into your default branch and confirm the Contact page works.

### Evidence

#### Screenshot 11 — Output of `git merge feature/contact-page`

<img width="2057" height="659" alt="AdobeExpressPhotos_a5d8557da45042c9898aef8dde9b72ce_CopyEdited" src="https://github.com/user-attachments/assets/1ca9f8b5-1369-4ab2-a327-9fd209413648" />

---

#### Screenshot 12 — Output of `ls` showing `contact.html` after the merge

<img width="2079" height="418" alt="AdobeExpressPhotos_d7f62d9df3d34493a5d0b5abfd697853_CopyEdited" src="https://github.com/user-attachments/assets/0391873d-7fd4-4af7-9dc3-e2653c000cc3" />


---

#### Screenshot 13 — Browser showing the Contact page opened from the homepage link on the default branch

<img width="2168" height="1506" alt="AdobeExpressPhotos_986513cb72cb49ddac6918b5bede59d8_CopyEdited" src="https://github.com/user-attachments/assets/5e66ab79-bc11-4c71-8a0a-fa8bf3640e5e" />


---

# Task 7 — Inspect History (Graph View)

## Goal

Display the repository history as a graph and locate both feature commits.

### Evidence

#### Screenshot 14 — Full output of `git log --oneline --graph --decorate --all`

<img width="2070" height="500" alt="AdobeExpressPhotos_ed56e6b81b6346dbb27a078f79893977_CopyEdited" src="https://github.com/user-attachments/assets/8a504d90-3a85-4f28-a577-12f1dd1f6217" />


---

# Task 8 — Optional Cleanup (Delete the Feature Branch)

## Goal

Delete the merged `feature/contact-page` branch to keep your branch list clean.

### Evidence

#### Screenshot 15 (Optional) — Output showing `feature/contact-page` deleted and no longer listed

<img width="2067" height="535" alt="AdobeExpressPhotos_34101235415740a8a6e089feaa0c12a6_CopyEdited" src="https://github.com/user-attachments/assets/e15d89d5-e717-42b5-90e0-e2e9f2e904b7" />


---

# Submission Instructions

- Tasks 1–7 are required; Task 8 is optional
- Add all required screenshots in your submission
- Evidence must show `contact.html` and the homepage link were absent before merging, and working after merging
- Do not expose passwords, access tokens, or private keys

---

# Completion Checklist

- [✅] Repository confirmed clean on the default branch (Screenshot 1)
- [✅] `feature/contact-page` created and checked out (Screenshot 2)
- [✅] `contact.html` added in its own commit (Screenshots 3–5)
- [✅] Homepage Contact link added in a separate commit (Screenshots 6–8)
- [✅] Default branch proven unchanged before merge (Screenshots 9–10)
- [✅] Feature branch merged and Contact page verified (Screenshots 11–13)
- [✅] Graph history reviewed (Screenshot 14)
- [✅] Optional cleanup completed (Screenshot 15)
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
