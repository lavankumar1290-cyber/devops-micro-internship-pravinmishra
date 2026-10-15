# Assignment 2 — CodeTrack: Tracking, Staging, Committing + Deploy to EC2

Part of the DevOps Micro Internship (DMI) with Agentic AI

---

## Purpose

In this assignment, you will track and stage project files, create two meaningful Git commits in `CodeTrack`, verify your commit history, and deploy the CodeTrack static website to an EC2 instance using Nginx. This connects local version-control practice with a basic manual deployment workflow used in real DevOps environments.

---

# Task 1 — Verify Git Setup and Enter the Repository

## Goal

Confirm that Git works and that you are inside the correct `CodeTrack` repository.

### Evidence

#### Screenshot 1 — Output of `pwd` showing you're inside `CodeTrack`

<img width="2577" height="142" alt="AdobeExpressPhotos_4323bc7d0d4241ae8c5a0861f2a6241d_CopyEdited" src="https://github.com/user-attachments/assets/efd4b62b-3e91-4953-9d1c-7da8700341f0" />

---

#### Screenshot 2 — Output of `git status` showing no "not a git repository" error

<img width="2415" height="405" alt="AdobeExpressPhotos_25a959cab3be408da77c62551f0fb3de_CopyEdited" src="https://github.com/user-attachments/assets/8540f941-2601-496c-903e-2460a5341609" />

---

# Task 2 — Create index.html and style.css

## Goal

Create the two starter UI files inside `CodeTrack`.

### Evidence

#### Screenshot 3 — Output of `ls` showing `index.html` and `style.css`

<img width="2579" height="409" alt="AdobeExpressPhotos_5d62767e98e44e44bfc8fdf4eaf67c1b_CopyEdited" src="https://github.com/user-attachments/assets/2bc0a561-a131-4209-afc4-963d3bd74082" />


---

# Task 3 — Add Starter Content

## Goal

Copy the provided starter HTML and CSS content into your local `index.html` and `style.css` files.

### Evidence

#### Screenshot 4 — Your editor showing the contents of `index.html` and `style.css`

<img width="3818" height="1619" alt="AdobeExpressPhotos_4941f22aaa7a478daaa129d4b33b5c31_CopyEdited" src="https://github.com/user-attachments/assets/30e5907b-6c1b-4ded-9c2c-c4d6dbca7488" />


---

# Task 4 — Track and Stage Files Correctly

## Goal

Confirm both files show as untracked, then stage them individually with `git add`.

### Evidence

#### Screenshot 5 — Output of `git status` showing both files as untracked

<img width="2164" height="604" alt="AdobeExpressPhotos_193a0b7fb8664231abe7dc43db17f998_CopyEdited" src="https://github.com/user-attachments/assets/27a7ef9b-b52d-4467-b1c2-221e27f16596" />

---

#### Screenshot 6 — Output of `git status` showing both files staged under "Changes to be committed"

<img width="2178" height="761" alt="AdobeExpressPhotos_0bbb8fbe8b7540b3b3c17669abe489d5_CopyEdited" src="https://github.com/user-attachments/assets/6a77aae3-db64-460b-b897-273576787fec" />


---

# Task 5 — Create the First Commit (Clean Initial Commit)

## Goal

Commit the staged starter files using the message `Initial UI scaffold: add index.html and style.css`, then check the log.

### Evidence

#### Screenshot 7 — Output of `git commit`

<img width="2609" height="681" alt="AdobeExpressPhotos_c15005eb1ac44f2eb3976c605ee50477_CopyEdited" src="https://github.com/user-attachments/assets/99680887-78a0-48ac-b742-15f9b8a4677f" />


---

#### Screenshot 8 — Output of `git log --oneline` showing the first commit

<img width="2610" height="262" alt="AdobeExpressPhotos_fc1e3ef17a3c496e9c8751110f9eaa5f_CopyEdited" src="https://github.com/user-attachments/assets/2d28f8b2-8a9b-4e98-9e6f-28750784d0da" />


---

# Task 6 — Modify index.html and Create a Second Commit

## Goal

Follow the instruction comment inside `index.html` to update the Student Name and Group Name, then commit that change separately using the message `Update homepage content: heading, tagline, CTA button`.

### Evidence

#### Screenshot 9 — Browser showing the updated page with your Student Name and Group Name visible

<img width="3818" height="2363" alt="AdobeExpressPhotos_c1836d72ebbc449b8dda9a7bdf2c5ea7_CopyEdited" src="https://github.com/user-attachments/assets/a18844d4-ed3b-4261-9007-fddbb231cef7" />


---

#### Screenshot 10 — Output of `git status` showing `index.html` as modified

<img width="2408" height="276" alt="AdobeExpressPhotos_bc1fa7b99d854ea7b9118c42c7fc91ed_CopyEdited" src="https://github.com/user-attachments/assets/0158fe76-61e5-4bd6-baea-ea2398523933" />


---

#### Screenshot 11 — Output of `git commit`

<img width="2469" height="276" alt="AdobeExpressPhotos_93d96bf13cac4151aa6b591c10694b1a_CopyEdited" src="https://github.com/user-attachments/assets/71e70bc6-8371-4523-987c-814609c180a1" />


---

#### Screenshot 12 — Output of `git log --oneline` showing two commits

<img width="2444" height="287" alt="AdobeExpressPhotos_c808c0eec2ad4cc5a2c4132138a0f7e8_CopyEdited" src="https://github.com/user-attachments/assets/11b30cfb-9ec0-46d9-a255-a35d229ed608" />


---

# Task 7 — Deploy to EC2 with Nginx (Static Website)

## Goal

Install and start Nginx on your EC2 instance, then copy `index.html` and `style.css` into the Nginx web root.

### Evidence

#### Screenshot 13 — Output of `systemctl status nginx --no-pager` showing Nginx `active (running)`

<img width="2399" height="1280" alt="AdobeExpressPhotos_0068ee1b8fe14b29b8148cdf41b57eae_CopyEdited" src="https://github.com/user-attachments/assets/a474900f-bf61-42ac-8695-e563f48211b9" />


---

#### Screenshot 14 — Output of `curl -I http://localhost` showing `HTTP/1.1 200 OK`

<img width="2392" height="506" alt="AdobeExpressPhotos_f34159a78ec04256abd61475916b2415_CopyEdited" src="https://github.com/user-attachments/assets/aae91cd9-787a-4a73-9587-4e67828df142" />


---

#### Screenshot 15 — Browser showing the CodeTrack site loaded at `http://<EC2_PUBLIC_IP>`, with your Full Name and Group Name visible

<img width="1660" height="947" alt="image" src="https://github.com/user-attachments/assets/d3b1be6b-e4d6-41ae-a200-46e05da13615" />

---

# LinkedIn Post (Required)

## Evidence

#### LinkedIn Post URL

Paste your LinkedIn post URL here:

https://www.linkedin.com/posts/lavan-kumar-aa2724307_devops-dmi-agenticai-share-7516456417415929856-_8ag/?utm_source=share&utm_medium=member_desktop&rcm=ACoAAE49RxoBGxFraCVYmiQyDbk76Ur65n4P1Kk

---

#### Screenshot — LinkedIn post showing the deployed CodeTrack application

<img width="1718" height="2149" alt="AdobeExpressPhotos_ac031380fab349a1b4107c276e2b5c98_CopyEdited" src="https://github.com/user-attachments/assets/83f305ef-bc3c-4abb-9bee-6ac97564d996" />

---

# Submission Instructions

- Add all required screenshots in your submission
- Full Name and Group Name must be visible in the deployed application evidence
- `git log --oneline` output must show at least two meaningful commits
- Do not expose AWS access keys, passwords, private key contents, or other sensitive information

---

# Completion Checklist

- [✅] `CodeTrack` repository verified with `git status` (Screenshots 1–2)
- [✅] `index.html` and `style.css` created and populated (Screenshots 3–4)
- [✅] Starter files staged and committed in the first commit (Screenshots 5–8)
- [✅] Student Name and Group Name updated in `index.html` (Screenshot 9)
- [✅] Second controlled commit created (Screenshots 10–12)
- [✅] Nginx active on the EC2 instance and CodeTrack reachable via its public IP (Screenshots 13–15)
- [✅] LinkedIn post published and URL submitted
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
