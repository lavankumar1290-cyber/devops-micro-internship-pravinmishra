# Assignment 3 — Production Maintenance Drill (OPS Checklist)

Part of the DevOps Micro Internship (DMI) with Agentic AI

---

## Purpose

In this assignment, you will treat your already deployed React application (on Ubuntu VM with Nginx) as a live production system. You will perform structured operational checks covering network validation, service health, log analysis, resource monitoring, configuration verification, and incident simulation with recovery — mirroring real on-call DevOps responsibilities.

---

# Task 1 — Server Access & Networking Validation

## Goal

Verify that the deployed React application is reachable from the browser and confirm basic network connectivity of the Ubuntu VM.

### Evidence

#### Screenshot 1 — Browser showing the React app with your Full Name visible on the UI

<img width="3792" height="2172" alt="Screenshot 2026-10-08 174322" src="https://github.com/user-attachments/assets/011ee05f-0bf7-40ad-9e98-6cdcc0add704" />


---

#### Screenshot 2 — Output of `ip a`

<img width="2397" height="890" alt="image" src="https://github.com/user-attachments/assets/fdeec8cd-641a-440f-a17d-8a2405ff87a2" />


---

#### Screenshot 3 — Output of `sudo ss -tulpen`

<img width="3677" height="1377" alt="image" src="https://github.com/user-attachments/assets/d7d7dd8d-fae5-4965-948b-3dd8f53cd193" />

---

#### Screenshot 4 — Output of `sudo ufw status`

<img width="2387" height="262" alt="image" src="https://github.com/user-attachments/assets/3fdd2977-9a30-49c8-bb91-ec19d4828fc8" />


---

### Notes

Answer the following in your own words:

**1. What proves Nginx is listening on 0.0.0.0:80?**

The sudo ss -tulpen output shows:

tcp LISTEN ... 0.0.0.0:80 ... users:(("nginx"...))

This proves that Nginx is listening on TCP port 80 on all IPv4 network interfaces.

---

**2. What proves SSH is active on port 22?**

The sudo ss -tulpen output should show a TCP LISTEN entry for port 22, usually with sshd as the process.

However, in the output you shared, there is no port 22 entry. So you should not claim that SSH is active on port 22 based on that screenshot.

You can verify it with:

sudo ss -tulpen | grep ':22'

If it shows sshd listening on :22, then SSH is active.


---

**3. Did you find any unexpected open ports? Explain briefly.**

I did not find any unexpected application ports. Port 80 is open for Nginx, while the other listed ports are mainly related to system services such as DNS and time synchronization.

---

# Task 2 — Service Health & Systemd Validation (Nginx)

## Goal

Verify that Nginx is properly installed, running, enabled at boot, and safely configured.

### Evidence

#### Screenshot 1 — Output of `systemctl status nginx --no-pager`


<img width="2400" height="1425" alt="image" src="https://github.com/user-attachments/assets/aadf42db-b898-4185-b03b-7044c3fad27f" />


---

#### Screenshot 2 — Output of `sudo nginx -t`


<img width="2507" height="375" alt="image" src="https://github.com/user-attachments/assets/ddf2d651-8021-453c-96e6-b4501a5c321e" />


---

#### Screenshot 3 — Output of `sudo ss -lptn '( sport = :80 )'`


<img width="2500" height="705" alt="image" src="https://github.com/user-attachments/assets/754f4586-a0d5-4f5e-8cda-611c59587a16" />

---

### Notes

Answer the following in your own words:

**1. What happens if Nginx fails to restart in production?**

If Nginx fails to restart, the website may become unavailable and users may not be able to access the application. I would first check the Nginx configuration and error logs, fix the problem, and then restart Nginx safely.

---

**2. What's your basic rollback plan?**

My basic rollback plan is to keep a working copy of the previous application build and configuration. If a new deployment causes problems, I would restore the previous working version, test the Nginx configuration with nginx -t, and restart Nginx to bring the application back online.

---

# Task 3 — Logs & Request Trace

## Goal

Verify real traffic flow and analyze logs to understand system behavior and errors.

### Evidence

#### Screenshot 1 — Output of `sudo tail -n 30 /var/log/nginx/access.log`


<img width="3672" height="882" alt="image" src="https://github.com/user-attachments/assets/305a393c-0fc4-4adc-bbd0-44a670e2d67b" />


---

#### Screenshot 2 — Output of `sudo tail -n 30 /var/log/nginx/error.log`


<img width="3657" height="280" alt="Screenshot 2026-10-08 182210" src="https://github.com/user-attachments/assets/a8fbbf99-14be-4609-81b2-5b0dcdc80dfd" />


---

#### Screenshot 3 — Output of `sudo journalctl -u nginx --no-pager -n 50`


<img width="3687" height="770" alt="image" src="https://github.com/user-attachments/assets/775291cf-2b22-467a-8586-44408ac4ab6b" />


---

### Notes

Answer the following in your own words:

**1. Were there any errors in the logs?**

- If yes, mention 1–2 example error lines from the logs and explain what each one means in simple terms.
- If no, explain what it means if the error log is empty or shows no recent errors during your check.

No, I did not find any recent errors in the Nginx error log. The error log was empty during my check. The Nginx journal also showed successful start and stop operations without failure messages.

---

**2. If there were no errors, what does that indicate about the system?**

It indicates that Nginx is running normally and there were no recent Nginx errors detected during the check. The service was able to start and restart successfully.

---

**3. Based on the access logs, were your curl requests visible in the log entries? What does that prove about traffic flow?**

If the access log contains entries for my curl requests, it proves that the requests reached Nginx and were processed by the web server. A successful HTTP status such as 200 indicates that Nginx successfully served the requested content.

---

# Task 4 — System Resource Health Check (Capacity Red Flags)

## Goal

Assess server capacity and detect potential performance or failure risks.

### Evidence

#### Screenshot 1 — Output of `uptime`


<img width="3102" height="310" alt="Screenshot 2026-10-08 182849" src="https://github.com/user-attachments/assets/9e0f1594-095e-40e0-b740-730eefac9e8b" />


---

#### Screenshot 2 — Output of `free -h`


<img width="3087" height="182" alt="Screenshot 2026-10-08 183220" src="https://github.com/user-attachments/assets/ec161513-1d51-40f1-9f00-ed9fb43b5eef" />


---

#### Screenshot 3 — Output of `df -h`


<img width="3035" height="902" alt="Screenshot 2026-10-08 183238" src="https://github.com/user-attachments/assets/9bcf7716-3ec0-4e76-95c4-12546a3ad92b" />


---

#### Screenshot 4 — Output of `sudo du -sh /var/* | sort -h`


<img width="3520" height="352" alt="image" src="https://github.com/user-attachments/assets/f6a9d38f-86c6-4711-aaaf-76d216151997" />


---

### Notes

Answer the following in your own words:

**1. Which resource looks most critical right now? (CPU/load, memory, or disk) Explain why.**

CPU/load looks the most active resource, but it is still very healthy. The load average is very low (0.00, 0.02, 0.00), memory has about 7.0 GiB available, and the root disk is only 1% used. So there are currently no critical resource issues.

---

**2. What happens if disk becomes 100% full in a production server?**

If the disk becomes 100% full, the server may not be able to write files, logs, temporary data, or database information. Applications can start failing, services such as Nginx may stop working correctly, and users may experience errors or downtime. Therefore, disk usage should be monitored and cleaned before it reaches full capacity.

---

# Task 5 — Configuration & Deployment Verification

## Goal

Ensure the correct React build is deployed and Nginx is serving it properly.

### Evidence

#### Screenshot 1 — Output of `ls -lah /var/www/html | head -n 20`


<img width="2257" height="792" alt="image" src="https://github.com/user-attachments/assets/9a599c25-598e-4242-b25e-aa9cabcd6eb9" />


---

#### Screenshot 2 — Output of `grep -R "Deployed by" -n /var/www/html 2>/dev/null | head`

Add your screenshot here.

---

#### Screenshot 3 — Output of `grep -n "try_files" /etc/nginx/sites-available/default`


<img width="3575" height="259" alt="image" src="https://github.com/user-attachments/assets/d82aeb1d-a2f0-404b-964e-0da3b0a7aa51" />


---

### Notes

Answer the following in your own words:

**1. How do you confirm that the correct version of the application is deployed?**

I confirm that the correct version is deployed by checking the files in /var/www/html and verifying that the latest application changes are present. I also check the application in the browser to make sure the expected content, such as “Deployed by: Lavan Kumar” and the correct date, is displayed. Finally, I verify the Nginx configuration to ensure it is serving the React build correctly.

---

# Task 6 — Nginx Configuration Failure Simulation

## Goal

Simulate a real-world Nginx misconfiguration and recover the service safely.

### Evidence

#### Screenshot 1 — Output of `sudo nginx -t` showing the syntax error (broken config)


<img width="2250" height="345" alt="image" src="https://github.com/user-attachments/assets/5f911dc1-a6fa-43b3-b7c6-23e64b93ed57" />



---

#### Screenshot 2 — Output of `sudo nginx -t` showing syntax ok (fixed config)


<img width="2270" height="305" alt="image" src="https://github.com/user-attachments/assets/d64d5b4a-1b49-422b-b1df-fac611b70cab" />


---

#### Screenshot 3 — Output of `curl -I http://<public-ip>` confirming recovery (200 OK)

<img width="2240" height="622" alt="image" src="https://github.com/user-attachments/assets/228fddc3-50f8-4bb9-828f-241951fcb118" />


---

### Notes

Answer the following in your own words:

**1. What caused the configuration failure?**

The failure was caused by removing the semicolon (;) from the try_files directive in the Nginx configuration. This created a syntax error, so nginx -t reported an unexpected }.
---

**2. How did you fix the issue?**

I added the missing semicolon (;) back to the try_files line and ran sudo nginx -t again to verify that the configuration was valid.

---

**3. How can you avoid this kind of issue in real production systems?**

In production, always test Nginx configuration using sudo nginx -t before restarting or reloading Nginx. Configuration changes should also be reviewed carefully, backed up before editing, and tested in a staging environment when possible.
---

# Task 7 — Web Application Failure Simulation

## Goal

Simulate missing deployment content and recover the application safely.

### Evidence

#### Screenshot 1 — Output of `curl -I http://<public-ip>` showing failure (non-200 response)

Add your screenshot here.

---

#### Screenshot 2 — Output of `curl -I http://<public-ip>` confirming recovery (200 OK)

Add your screenshot here.

---

### Notes

Answer the following in your own words:

**1. What caused the application to break in this scenario?**

Write your answer here

---

**2. How did you fix the issue and restore the application?**

Write your answer here.

---

**3. What steps would you take to prevent this kind of issue in real production systems?**

Write your answer here.

---

# Task 8 — Security & Reliability Review

## Goal

Review and reflect on the security and reliability practices applied during this assignment.

### Security & Reliability Notes

Answer the following in your own words:

**1. Why is SSH key-based authentication more secure than sharing passwords?**

Write your answer here.

---

**2. Why should only required ports be open on a production server?**

Write your answer here.

---

**3. Why is it important for Nginx to be enabled on boot?**

Write your answer here.

---

**4. What are the risks of sharing secrets, keys, or credentials publicly?**

Write your answer here.

---

**5. Why should cloud resources be stopped or terminated when they are no longer needed?**

Write your answer here.

---

# LinkedIn Post (Required)

## Evidence

#### LinkedIn Post URL

Paste your LinkedIn post URL here:

`Add your URL here`

---

#### Screenshot — Published LinkedIn post

Add your screenshot here.

---

# Submission Instructions

- Add all required screenshots in your submission
- Full name must be visible in required screenshots
- Do not expose sensitive information (keys, passwords, account IDs)

---

# Completion Checklist

- [ ] Task 1: Screenshots (browser, ip a, ss -tulpen, ufw status) + Notes answered
- [ ] Task 2: Screenshots (nginx status, nginx -t, ss port 80) + Notes answered
- [ ] Task 3: Screenshots (access log, error log, journalctl) + Notes answered
- [ ] Task 4: Screenshots (uptime, free -h, df -h, du -sh) + Notes answered
- [ ] Task 5: Screenshots (ls html, grep deployed by, grep try_files) + Notes answered
- [ ] Task 6: Screenshots (nginx -t fail, nginx -t pass, curl recovery) + Notes answered
- [ ] Task 7: Screenshots (curl failure, curl recovery) + Notes answered
- [ ] Task 8: Security & Reliability Notes answered
- [ ] LinkedIn post published and URL submitted
- [ ] Full Name visible in all required screenshots
- [ ] No sensitive data exposed

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
