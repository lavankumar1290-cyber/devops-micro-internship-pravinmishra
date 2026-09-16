# Week 00 - Internet and Networking

Part of the DevOps Micro Internship (DMI) with Agentic AI

---

# 🧑‍💻 Task 1: Using ChatGPT as Your Learning Assistant

## Scenario

You're new to DevOps and will frequently encounter technical questions. ChatGPT can be your learning companion.

## Your Task

Write a clear ChatGPT prompt to help you understand:

> "What is a protocol in networking? Explain with a simple real-life example."

Take a screenshot of your interaction showing:

* Your detailed prompt (with clear expectations)
* ChatGPT's simplified response with an example

## Screenshot

Save your screenshot in the `screenshots` folder and update the file name below.

![Task 1 Screenshot]!(<img width="1590" height="1020" alt="AdobeExpressPhotos_01e162138993443b81e9c0285fa9d5f5_CopyEdited" src="https://github.com/user-attachments/assets/0fa3bc81-49f0-4750-907e-8c73f31f3a31" />



Replace `task-1-chatgpt.png` with your actual screenshot file name.

---

## What I Learned (2–3 lines)

I learned that a networking protocol is a set of rules that allows devices to communicate with each other correctly. I also understood the concept using a real-life communication example and learned why protocols such as HTTP are important in networking.

---

# 🌐 Task 2: Internet and Networking

## Scenario

Your friend is launching an online bookstore named **EpicReads**.

He asked you to explain how users globally can access his website hosted in Finland.

## Your Task

Write a short explanation (**100–150 words**) that includes:

* Packet Switching
* IP Address
* TCP/IP
* HTTP/HTTPS

💡 **Tip:** You may use ChatGPT (as demonstrated in Task 1) to refine your explanation.

## Answer
### Task 2 — Explanation (100–150 words)

When a user wants to access the **EpicReads** website hosted in Finland, the request travels through the Internet using **packet switching**. The data is divided into small packets, which can travel through different network paths and are reassembled at the destination.

Every device and server has an **IP address** that helps identify where the data should go. **TCP/IP** provides the rules for delivering packets reliably across different networks. TCP ensures the data arrives correctly, while IP handles addressing and routing.

When the user's browser requests the EpicReads website, **HTTP or HTTPS** is used to communicate with the web server. HTTPS provides encrypted communication, helping protect information such as login details and payment data. Thus, packet switching, IP addresses, TCP/IP, and HTTP/HTTPS work together to allow users worldwide to access EpicReads.



---

# 🏗️ Task 3: Application Architecture & Stack

## Scenario

EpicReads bookstore has two application versions:

### Two-Tier Application

* Frontend
* Database

### Three-Tier Application

* Frontend
* Backend
* Database

## Your Task

* Draw simple diagrams (hand-drawn or tool-based such as draw.io)
* Label each layer clearly
* List at least two common technologies or tools used for each layer
* Submit a screenshot or photo clearly showing your own drawing

## Diagram Screenshot / Photo

Save your diagram image in the `screenshots` folder and update the file name below.

![Application Architecture Diagram]!(<img width="2239" height="1677" alt="AdobeExpressPhotos_00597eee01304fcf83ecb06b69200f6e_CopyEdited" src="https://github.com/user-attachments/assets/3b280f02-7010-4399-93ff-4e74d91de758" />
)


Replace `task-3-diagram.png` with your actual diagram file name.

---

## Technologies Used

### Frontend

- HTML
- React.js

### Backend

- Node.js
- Java


### Database

- MySQL
- MongoDB

---

# 🌍 Task 4: Domain Name & DNS (Basic Concepts)

## Scenario

Your friend's bookstore **EpicReads** is currently accessible through:

```text
52.172.142.222:3000
```

He purchased the domain:

```text
epicreads.com
```

## Your Task

In **50–100 words**, explain in your own words:

1. What is DNS (Domain Name System)?
2. Which DNS record type should be used to connect the domain to the given IP, and why?

## Answer

### Answer

DNS (Domain Name System) translates human-readable domain names into IP addresses that computers can understand. It allows users to access websites using names like **epicreads.com** instead of remembering an IP address.

To connect **epicreads.com** to **52.172.142.222**, an **A record** should be used because an A record maps a domain name to an IPv4 address. After configuring it, users can access the website using **epicreads.com** instead of the IP address.


---

# 💻 Task 5: Visual Studio Code Setup (Hands-on)

## Your Task

Install Visual Studio Code (if not already installed).

Take a screenshot of your VS Code environment showing:

* Terminal open inside VS Code
* Running a basic command:

### Windows

```powershell
dir
```

### Linux / macOS

```bash
pwd
ls
```

* Your selected VS Code theme clearly visible

⚠️ **Important:** The screenshot must show your username or another identifiable detail to confirm it is your environment.

## Screenshot

Save your screenshot in the `screenshots` folder and update the file name below.

![VS Code Setup Screenshot]!(<img width="3818" height="2371" alt="AdobeExpressPhotos_b33b415b0c9440eba656e813345e0090_CopyEdited" src="https://github.com/user-attachments/assets/731dadc6-e70e-498d-9c4f-02cc154ffbb7" />
)


Replace `task-5-vscode.png` with your actual screenshot file name.

---

# 🔗 Task 6: Publish Your Assignment as a LinkedIn Post

## Objective

Publishing on LinkedIn helps you:

* Build your professional online presence
* Reinforce your learning
* Document your DevOps journey publicly

## Your Task

Summarize your answers from Tasks 1–5 into a LinkedIn post.

Clearly structure your post into the following sections:

* ChatGPT
* Internet & Networking
* App Architecture
* DNS
* VS Code Setup

Use the credit note that matches your track:

Add the following credit note at the end of your post **(If you are DMI Cohort 3 student)**:

> **P.S. This post is part of the DevOps Micro Internship (DMI) with Agentic AI — Cohort 3 — by Pravin Mishra. My graded progress is public: https://dmi.pravinmishra.com/s/YOUR-GITHUB-USERNAME.html · Start your DevOps journey: https://dmi.pravinmishra.com/?utm_source=student&utm_medium=ps-linkedin&utm_campaign=cohort3**

**Tag [Pravin Mishra](https://www.linkedin.com/in/pravin-mishra-aws-trainer/) in your LinkedIn post, then tag Lead Co-Mentor — [Anjana Muthunayake](https://www.linkedin.com/in/anjana-muthunayake/).**

Add the following credit note at the end of your post **(If you are DMI Self-paced track student)**:

> **P.S. This post is part of the DevOps Micro Internship (DMI) — Self-Paced Engineer Track — by Pravin Mishra. My graded progress is public: https://dmi.pravinmishra.com/s/YOUR-GITHUB-USERNAME.html · Start your DevOps journey: https://dmi.pravinmishra.com/?utm_source=student&utm_medium=ps-linkedin&utm_campaign=self-paced**

Add the following credit note at the end of your post **(If you are DMI Campus student)**:

> **P.S. This post is part of the DevOps Micro Internship (DMI) — Campus — by Pravin Mishra. My graded progress is public: https://dmi.pravinmishra.com/s/YOUR-GITHUB-USERNAME.html · Start your DevOps journey: https://dmi.pravinmishra.com/?utm_source=student&utm_medium=ps-linkedin&utm_campaign=campus**

**Tag [Pravin Mishra](https://www.linkedin.com/in/pravin-mishra-aws-trainer/) in your LinkedIn post, then tag Lead Co-Mentor — [Anjana Muthunayake](https://www.linkedin.com/in/anjana-muthunayake/).**

Hashtags:

#DMIByPravinMishra #AgenticAI #DevOps

Replace `YOUR-GITHUB-USERNAME` with your GitHub username — that link is your public DMI progress page (your graded badge page).
---

## LinkedIn Post URL

Paste your LinkedIn post URL here:https://www.linkedin.com/posts/lavan-kumar-aa2724307_dmibypravinmishra-agenticai-devops-activity-7505877798276825088-SSLD?utm_source=share&utm_medium=member_desktop&rcm=ACoAAE49RxoBGxFraCVYmiQyDbk76Ur65n4P1Kk

Add your U🚀 Week 00 of my DevOps Micro Internship journey!

I completed my Week 00 — Internet and Networking tasks and learned the fundamentals of how applications communicate over the Internet.

🤖 **ChatGPT**
Learned how networking protocols work using simple real-life examples.

🌐 **Internet & Networking**
Learned about packet switching, IP addresses, TCP/IP, and HTTP/HTTPS.

🏗️ **App Architecture**
Understood the difference between two-tier and three-tier architectures and explored frontend, backend, and database technologies.

🔗 **DNS**
Learned how DNS converts domain names into IP addresses and how an A record connects a domain to an IPv4 address.

💻 **VS Code Setup**
Set up my VS Code environment and practiced using the terminal with basic commands.

This week helped me build a stronger foundation in networking and DevOps concepts. Looking forward to learning more! 🚀

P.S. This post is part of the DevOps Micro Internship (DMI) with Agentic AI — Cohort 3 — by Pravin Mishra. My graded progress is public:

https://dmi.pravinmishra.com/s/YOUR-GITHUB-USERNAME.html

Start your DevOps journey:
https://dmi.pravinmishra.com/?utm_source=student&utm_medium=ps-linkedin&utm_campaign=cohort3

Tag Pravin Mishra in your LinkedIn post, then tag Lead Co-Mentor — Anjana Muthunayake.

#DMIByPravinMishra #AgenticAI #DevOps
RL here...
```

---

## LinkedIn Post Backup Copy

Paste the full text of your LinkedIn post here:

Add your post content here...

---

# Reflection – Week 0

### What did you find easy?

Add your answer here...

---

### What was difficult?

Add your answer here...

---

### What will you improve next week?

Add your answer here...

---

## 📌 About DMI & CloudAdvisory

DevOps Micro Internship (DMI) is a project-based DevOps program run by Pravin Mishra (The CloudAdvisory) focused on real-world execution, systems thinking, and career readiness.

It helps learners build strong DevOps foundations with hands-on experience.


## 📌 Resources

- 🌐 **DMI Official Website:** https://dmi.pravinmishra.com?utm_source=github&utm_medium=readme  
- 🎓 **University:** https://university.pravinmishra.com?utm_source=github&utm_medium=readme  
- 💬 **Discord Community:** https://discord.pravinmishra.com?utm_source=github&utm_medium=readme  
- 📝 **Blog:** https://dmi.pravinmishra.com/blog?utm_source=github&utm_medium=readme  
- ▶️ **YouTube Playlist (DMI Cohort 3):** https://www.youtube.com/playlist?list=PLFeSNDtI4Cho  
- 🔗 **Pravin Mishra (LinkedIn):** https://www.linkedin.com/in/pravin-mishra-aws-trainer/  
- 🏢 **CloudAdvisory (LinkedIn):** https://www.linkedin.com/company/thecloudadvisory/

---

*This submission is part of DevOps Micro Internship (DMI) — Agentic AI Track*
