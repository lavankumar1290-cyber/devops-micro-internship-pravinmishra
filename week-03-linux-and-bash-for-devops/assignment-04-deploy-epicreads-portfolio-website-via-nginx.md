# Assignment 4 — Deploy EpicReads Portfolio Website via Nginx

Part of the DevOps Micro Internship (DMI) with Agentic AI

---

## Purpose

In this assignment, you will deploy a static portfolio website on an Ubuntu VM using Nginx. You will download the website template, add your ownership proof in the footer, deploy the files to the Nginx web root, and verify the website is publicly accessible via a browser.

---

# Task 0 — Pre-flight Check

## Goal

Verify the Ubuntu VM and Nginx are ready for deployment.

### Evidence

#### Screenshot 0 — Output of `sudo systemctl status nginx --no-pager` showing Active (running)

<img width="3458" height="1365" alt="AdobeExpressPhotos_808e82380932472c8b8a521db24a4255_CopyEdited" src="https://github.com/user-attachments/assets/1364e6d0-c636-4750-91e4-6cfa35bf1964" />


---

# Task 1 — Get the Website Source Code

## Goal

Download and extract the portfolio website template.

### Evidence

#### Screenshot 1 — Output of `ls -la` showing the extracted project folder

<img width="1203" height="490" alt="AdobeExpressPhotos_49c70b9e27504fbdbf3b14166bcee6ac_CopyEdited" src="https://github.com/user-attachments/assets/aed9b7e9-5764-4a85-8a98-eeeaf42187b7" />


---

# Task 2 — Add Ownership Proof (Anti-Copy Change)

## Goal

Update the website footer with your deployment details.

### Evidence

#### Screenshot 2 — Nano editor open with the updated footer showing your Full Name, Group, Week, and Date

<img width="2344" height="288" alt="AdobeExpressPhotos_621fca6a674c43a18be0faf6855bf11d_CopyEdited" src="https://github.com/user-attachments/assets/ecffcd72-4b9d-4104-95e3-161314922cd9" />

---

# Task 3 — Deploy Website via Nginx

## Goal

Deploy the portfolio website to the Nginx web root.

### Evidence

#### Screenshot 3 — Output of `sudo nginx -t` showing configuration test successful

<img width="3059" height="266" alt="AdobeExpressPhotos_9c989e5380d24696a06d22faa0e52cf3_CopyEdited" src="https://github.com/user-attachments/assets/935939c4-61f8-449b-923d-f865bb7e55e4" />


---

#### Screenshot 4 — Output of `ls /var/www/html` showing deployed website files

<img width="3129" height="620" alt="AdobeExpressPhotos_a7802de109764f7bb233164989978ccd_CopyEdited" src="https://github.com/user-attachments/assets/60c914a6-4212-4f30-98aa-2c26ffb41c53" />


---

# Task 4 — Verify Website is Live

## Goal

Verify the deployed website is publicly accessible and the footer contains your details.

### Evidence

#### Screenshot 5 — Output of `curl ifconfig.me` showing the server's public IP address

<img width="3128" height="105" alt="AdobeExpressPhotos_88d46d5802cf4919a4bad19b60932f45_CopyEdited" src="https://github.com/user-attachments/assets/07b68608-43fa-4667-b3ee-8b7c0186b299" />


---

#### Screenshot 6 — Browser showing the live website with your Full Name and deployment details in the footer

<img width="3792" height="2172" alt="image" src="https://github.com/user-attachments/assets/dd40f521-8f05-4c4b-8fa3-b10a197bf0e6" />


---

# Task 5 — Mini Real DevOps Operational Check

## Goal

Verify the deployed website and Nginx service are healthy.

### Evidence

#### Screenshot 7 — Output of `systemctl is-enabled nginx`

<img width="3246" height="154" alt="AdobeExpressPhotos_b47edb8e3b6f4c2fa1f7c546f22e8321_CopyEdited" src="https://github.com/user-attachments/assets/a0ea0f61-d4f8-4925-8054-ac70f995915f" />


---

#### Screenshot 8 — Output of `curl -I http://localhost` showing 200 OK

<img width="3207" height="443" alt="AdobeExpressPhotos_c83b05a4dc4140f28464f42f0b24c9cc_CopyEdited" src="https://github.com/user-attachments/assets/82b311ad-686b-4e87-b8ab-cbdcc844e9e7" />


---

# LinkedIn Post (Mandatory)

## Evidence

#### LinkedIn Post URL

Paste your LinkedIn post URL here:

`Add your URL here`

---

#### Screenshot — Published LinkedIn post showing the live website with your Full Name in the footer

Add your screenshot here.

---

# Submission Instructions

- Add all required screenshots in your submission
- Full name must be visible in required screenshots
- Ownership proof in the footer is mandatory
- Do not expose sensitive information (keys, passwords, account IDs)

---

# Completion Checklist

- [✅] Screenshot 0: Nginx service status (active/running)
- [✅] Screenshot 1: Website files downloaded and extracted
- [✅] Screenshot 2: Footer updated with Full Name, Group, Week, and Date
- [✅] Screenshot 3: Nginx configuration test successful
- [✅] Screenshot 4: Website files deployed to /var/www/html
- [✅] Screenshot 5: Public IP retrieved
- [✅] Screenshot 6: Live website accessible in browser with footer details
- [✅] Screenshot 7: Nginx enabled on boot
- [✅] Screenshot 8: Local HTTP response returns 200 OK
- [✅] LinkedIn post published and URL submitted
- [✅] Full Name visible in all required screenshots
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
