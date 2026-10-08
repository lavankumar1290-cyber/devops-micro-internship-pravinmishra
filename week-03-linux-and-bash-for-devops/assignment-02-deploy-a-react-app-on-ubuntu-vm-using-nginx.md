# Assignment 2 — Deploy a React App on Ubuntu VM Using Nginx

Part of the DevOps Micro Internship (DMI) with Agentic AI

---

## Purpose

In this assignment, you will deploy a React application on an Ubuntu EC2 instance and serve it using Nginx. You will provision a Linux server, install the required tools, personalize the application with your details, and verify that it is publicly accessible via a browser.

---

# Task 1 — Setup Environment (Node.js & npm)

## Goal

Install Node.js and npm on the Ubuntu VM and verify the installation.

### Evidence

#### Screenshot 1 — Output of `node -v && npm -v` showing installed versions

<img width="2630" height="282" alt="image" src="https://github.com/user-attachments/assets/36288ad8-510c-4059-a69d-76f71157aa45" />


---

# Task 2 — Setup Environment (Nginx)

## Goal

Install Nginx, start the service, and confirm it is running.

### Evidence

#### Screenshot 2 — Output of `systemctl status nginx --no-pager` showing Active (running)

<img width="2665" height="1710" alt="image" src="https://github.com/user-attachments/assets/6f8e42d8-c470-4e59-8179-9139498b7346" />


---

# Task 3 — Clone React Application

## Goal

Clone the project repository and verify the project files are present.

### Evidence

#### Screenshot 3 — Output of `ls` inside the `my-react-app` directory showing project files

<img width="2225" height="797" alt="image" src="https://github.com/user-attachments/assets/1a585d06-4c2e-47b6-8982-dd201de06440" />

---

# Task 4 — Modify Application (Personalization)

## Goal

Update `App.js` with your full name and the current date.

### Evidence

#### Screenshot 4 — `nano App.js` open showing your full name and date filled in

<img width="2050" height="1830" alt="image" src="https://github.com/user-attachments/assets/3c9f80e0-8439-448d-a7a4-dfbba04ed31e" />




---

# Task 5 — Build React Application

## Goal

Install dependencies and generate the production build.

### Evidence

#### Screenshot 5 — Output of `ls` inside `my-react-app` showing the `build/` folder generated

<img width="3012" height="1765" alt="image" src="https://github.com/user-attachments/assets/4f4cc5e5-4efa-4b26-b908-2acff483aa4c" />



---

# Task 6 — Deploy React Build to Nginx Web Root

## Goal

Copy the production build files to the Nginx web root directory.

### Evidence

#### Screenshot 6 — Output of `ls /var/www/html/` showing the deployed build contents

<img width="2170" height="445" alt="image" src="https://github.com/user-attachments/assets/c252364a-010f-4a6a-9c18-917a9c9be549" />


---

# Task 7 — Configure Nginx for React Application

## Goal

Apply Nginx configuration for React routing and confirm the service is active.

### Evidence

#### Screenshot 7 — Output of `systemctl is-active nginx` showing `active`

<img width="2325" height="360" alt="image" src="https://github.com/user-attachments/assets/2f93c92d-c060-4f55-a6eb-80144b28640e" />


---

#### Screenshot 8 — Output of `cat /etc/nginx/sites-available/default` showing the Nginx config

<img width="2342" height="902" alt="image" src="https://github.com/user-attachments/assets/e40051aa-34fd-48a8-9c35-897d9c20a2e1" />


---

# Task 8 — Test Deployment

## Goal

Verify the React application is publicly accessible via the server's public IP.

### Evidence

#### Screenshot 9 — Output of `curl ifconfig.me` showing the server's public IP address

<img width="2335" height="187" alt="image" src="https://github.com/user-attachments/assets/efefbf8b-85fe-4f43-a3a7-a9da807e1768" />


---

#### Screenshot 10 — Browser showing the deployed React app at `http://<public-ip>` with your name and date visible

<img width="3792" height="2172" alt="image" src="https://github.com/user-attachments/assets/a249c0ce-e7d8-40a7-9d4c-579f33aa3f4b" />


---

# LinkedIn Post (Required)

## Evidence

#### LinkedIn Post URL

Paste your LinkedIn post URL here:

https://www.linkedin.com/posts/lavan-kumar-aa2724307_aws-nginx-react-share-7513936008904642560-TcSK/?utm_source=share&utm_medium=member_desktop&rcm=ACoAAE49RxoBGxFraCVYmiQyDbk76Ur65n4P1Kk

---

#### Screenshot — LinkedIn post showing the deployed application

<img width="1670" height="1870" alt="image" src="https://github.com/user-attachments/assets/c3dbdea2-f536-436e-97c8-e9a0a24a316c" />


---

# Submission Instructions

- Add all required screenshots in your submission
- Full name must be visible in required screenshots
- Do not expose sensitive information (keys, passwords, account IDs)

---

# Completion Checklist

- [✅] Node.js and npm installed and verified (Screenshot 1)
- [✅] Nginx installed and running (Screenshot 2)
- [✅] Repository cloned and files verified (Screenshot 3)
- [✅] App.js updated with full name and date (Screenshot 4)
- [✅] Production build generated (Screenshot 5)
- [✅] Build files deployed to Nginx web root (Screenshot 6)
- [✅] Nginx configured and active (Screenshots 7 & 8)
- [✅] Public IP retrieved (Screenshot 9)
- [✅] React app accessible in browser with personal details visible (Screenshot 10)
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
