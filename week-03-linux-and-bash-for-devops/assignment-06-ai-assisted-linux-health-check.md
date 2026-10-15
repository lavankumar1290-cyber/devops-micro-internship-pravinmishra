# Assignment 6 — Build an AI-Assisted Linux Health Check (AI-Assisted Linux Incident Triage)

Part of the DevOps Micro Internship (DMI) with Agentic AI

---

## Purpose

In this assignment, you will build a read-only Bash triage script that checks the health of your Ubuntu server and Nginx application, connect it to Claude Code as a reusable `/linux-triage` skill, simulate a controlled Nginx incident, use the skill to gather and analyze evidence, recover the service manually, and verify recovery. The workflow follows the Agentic Loop: Gather → Analyze → Human Act → Verify.

---

# Task 1 — Confirm the Healthy Baseline and Create the Workspace

## Goal

Confirm that Nginx and the React application are healthy before building the automation.

### Evidence

#### Screenshot 1 — Output of `systemctl is-active nginx`, `ss -ltn | grep ':80'`, and `curl -I http://localhost`

<img width="1426" height="744" alt="AdobeExpressPhotos_d5e7717dca9f41169cf374b6bf1e0675_CopyEdited" src="https://github.com/user-attachments/assets/57517af6-d436-4512-b8cf-2e1fcd5e5e30" />

---

#### Screenshot 2 — Output of `pwd` and `find . -maxdepth 4 -type d | sort` showing the workspace folder structure

<img width="1459" height="320" alt="AdobeExpressPhotos_08eeaf93c9fe40e0b7bad57f6a6bc99f_CopyEdited" src="https://github.com/user-attachments/assets/f8a03bec-0b5f-4f59-baff-7e2753188871" />


---

### Notes

Answer the following in your own words:

**1. What proves that Nginx is running?**

The command systemctl is-active nginx displays active, which proves that the Nginx service is running.

---

**2. What proves that the server is listening for HTTP traffic?**

The command ss -ltn | grep ':80' shows whether a socket is listening on port 80, which is the default HTTP port. The command curl -I http://localhost checks whether the server responds to an HTTP request. A response such as HTTP/1.1 200 OK indicates that the request was successful.

---

**3. Why must you capture a healthy baseline before simulating an incident?**

Capturing a healthy baseline helps us understand the normal working condition of the server before an incident occurs. We can compare the results before and after the incident to identify the problem and verify that the service has recovered successfully.

---

# Task 2 — Create Project Context and Safety Rules in CLAUDE.md

## Goal

Tell Claude exactly what this project does and what it is not allowed to do.

### Evidence

#### Screenshot 3 — CLAUDE.md open in VS Code showing all four sections (Project Overview, Incident Workflow, Safety Rules, Output Rules)

<img width="3813" height="2175" alt="AdobeExpressPhotos_a0bce68c6cfd472e89811f4841a59412_CopyEdited" src="https://github.com/user-attachments/assets/7636e772-0b95-4cfd-a58b-7c928346bfc3" />

---

### Notes

Answer the following in your own words:

**1. Why should Claude receive project-specific operational rules?**

Project-specific rules help Claude understand the purpose of the project, follow the correct workflow, and avoid unsafe operations. They ensure that Claude collects evidence and provides recommendations according to the project's requirements.

---

**2. Why is the human required to execute the recovery command?**

The human must execute the recovery command to maintain control over the server and prevent accidental changes or service interruptions. Claude can analyze the evidence and recommend recovery steps, but the human reviews and performs the action.

---

**3. Which rule prevents Claude from making an unsupported diagnosis?**

The rule stating "If evidence is insufficient, report the uncertainty instead of guessing" prevents Claude from making unsupported diagnoses. It requires Claude to base its findings on collected evidence rather than assumptions.

---

# Task 3 — Use Agentic AI to Plan Before Writing the Script

## Goal

Use Claude Code to inspect the environment and produce a read-only plan before creating any Bash code.

### Evidence

#### Screenshot 4 — Claude Code showing the five-check plan and read-only inspection results

<img width="2206" height="1954" alt="AdobeExpressPhotos_db83fb3ed3d04ee9a73386ca012e9980_CopyEdited" src="https://github.com/user-attachments/assets/fcd4f79d-078c-4221-ac10-3bafe3683c17" />


---

### Notes

Answer the following in your own words:

**1. Which part of this task represents the Gather phase?**

The Gather phase is represented by running read-only Linux commands to collect system information, check Nginx status, inspect listening ports, check the HTTP response, and monitor disk and memory usage. These results provide evidence about the current system health.

---

**2. Did Claude follow the instruction not to create files? How did you verify this?**

Claude was instructed not to create or modify any files during the planning phase. I would verify this by checking the Claude Code conversation and inspecting the workspace before and after planning. In this task, I collected the health-check results using read-only commands. Since Claude Code encountered a credit-balance error, I cannot confirm that Claude itself completed the planning task.

---

**3. Why is planning before coding useful in DevOps automation?**

Planning before coding helps identify the required checks, understand the expected results, and define safety rules before writing a script. It reduces mistakes, prevents unintended system changes, and makes automation easier to test, maintain, and troubleshoot.

---

# Task 4 — Build the Linux Triage Bash Script

## Goal

Create one Bash script that gathers consistent Linux and Nginx health evidence.

### Evidence

#### Screenshot 5 — Top section of `linux-triage.sh` showing variables, thresholds, and the checks array

<img width="2489" height="2165" alt="AdobeExpressPhotos_9345d1cc66e343878d471898781df014_CopyEdited" src="https://github.com/user-attachments/assets/f04c4044-3700-4280-9c52-d9d80c4e0491" />


---

#### Screenshot 6 — Middle section showing check functions and conditionals

<img width="2207" height="1724" alt="AdobeExpressPhotos_a0bf42f6a5544fc7b68d702e35612569_CopyEdited" src="https://github.com/user-attachments/assets/0c38a51d-c8c7-477a-9427-2456ad6cf057" />


---

#### Screenshot 7 — Bottom section showing the loop, summary function, and exit behavior

<img width="2180" height="1745" alt="AdobeExpressPhotos_83785cf1d8754d15ac53e8288c1403c9_CopyEdited" src="https://github.com/user-attachments/assets/33baa003-544a-4e15-9da9-bc32afb5dfa9" />
<img width="2361" height="1839" alt="AdobeExpressPhotos_f47b585be7104484bcadf5e92eb9fea8_CopyEdited" src="https://github.com/user-attachments/assets/408657a7-1161-4291-90b9-9f022302ec55" />


---

#### Screenshot 8 — Output of `bash -n scripts/linux-triage.sh` (no syntax errors) and `ls -l scripts/linux-triage.sh` showing executable permission

<img width="1370" height="341" alt="AdobeExpressPhotos_293dd1287324488486b19cb6b76c09a4_CopyEdited" src="https://github.com/user-attachments/assets/bd6f35bb-9265-45cb-a062-559b18f1bee4" />


---

### Notes

Answer the following in your own words:

**1. What is stored in the checks array?**

The CHECKS array stores the names of the five health checks: Nginx service status, HTTP port, HTTP response, disk usage, and memory usage. These names tell the script which checks it needs to perform.

---

**2. How does the `for` loop use that array?**

The for loop goes through each item in the CHECKS array one by one. The case statement identifies each item and calls its corresponding function to perform the health check.

---

**3. Why are the health checks separated into functions?**

Functions make the script organized, readable, and easier to maintain. Each function performs one specific check, making it easier to identify problems, test individual checks, and update the script without changing unrelated sections.

---

**4. What is the purpose of `$(...)` in this script?**

$(...) is called command substitution. It runs a command and stores its output in a variable.

For example:

HOST_NAME="$(hostname)"

This runs the hostname command and stores the computer's hostname in the HOST_NAME variable

---

**5. Why does the script use different exit codes for HEALTHY, WARN, and FAIL?**

Different exit codes help users and automation tools understand the result of the health checks.

Exit code 0 — HEALTHY: All checks passed without warnings.
Exit code 1 — WARN: One or more warnings were detected.
Exit code 2 — FAIL: One or more incidents were detected.

These codes make it easier to identify the result and decide whether further investigation is needed.

---

# Task 5 — Run and Understand the Healthy-State Report

## Goal

Run the Bash script against the healthy server and verify that it creates a report.

### Evidence

#### Screenshot 9 — Output of `./scripts/linux-triage.sh` showing your Full Name and all five check results

<img width="1562" height="1944" alt="AdobeExpressPhotos_7dc88c118bd547b6bb68412f9710856d_CopyEdited" src="https://github.com/user-attachments/assets/30e44c34-12b4-4b7b-a5f2-62421a8a2e96" />


---

#### Screenshot 10 — Output showing the captured exit code and final summary

<img width="1357" height="188" alt="AdobeExpressPhotos_2de4114ecf4d45eca5c4b799b91d1e34_CopyEdited" src="https://github.com/user-attachments/assets/5853e6b0-538c-484a-90bc-010c14c16d3d" />


---

### Notes

Answer the following in your own words:

**1. What is the overall status of your healthy baseline?**

The overall status of my healthy baseline is healthy when all five checks pass without warnings or incidents. The script checks Nginx, port 80, the HTTP response, disk usage, and memory usage.

---

**2. Which exact Linux evidence proves the application is serving traffic?**

The systemctl is-active nginx command returns active, and ss -ltn shows port 80 in the LISTEN state. Also, curl -I --max-time 5 http://localhost returns HTTP 200 OK, confirming that the application responds successfully to a local HTTP request.

---

**3. Did your script return exit code 0 or 1? Explain why.**

My script returned exit code 2 in the captured output because it incorrectly detected an incident in the port 80 check. Although port 80 was listening, the script reported that no listening socket was detected. Exit code 0 indicates all checks passed, while exit code 1 indicates warnings without incidents. After fixing the port check, I should run the script again to verify the correct exit code.

---

**4. What is the difference between a warning and a failure in this script?**

A warning indicates a potential issue that needs attention, such as resource usage exceeding the configured warning threshold. A failure or incident indicates a check did not meet its required condition, such as a service being inactive or a required port not listening. The script uses exit code 1 for warnings and exit code 2 when an incident is detected.

---

# Task 6 — Create and Run the /linux-triage Skill

## Goal

Turn the Bash script into a reusable, manually invoked Agentic AI workflow.

### Evidence

#### Screenshot 11 — `SKILL.md` showing the frontmatter, allowed tool restrictions, and safety rules

<img width="2335" height="2198" alt="AdobeExpressPhotos_421a1e7afc1e49cbb5c936c33e1c71d2_CopyEdited" src="https://github.com/user-attachments/assets/e75df911-6f70-47f2-ae03-9617118875e8" />


---

#### Screenshot 12 — `/linux-triage` output for the healthy ser

<img width="1977" height="2132" alt="AdobeExpressPhotos_20e0a10e61c049189b5a245e7f276656_CopyEdited" src="https://github.com/user-attachments/assets/9ea12076-4864-406b-859e-76f107cfed7e" />

---

### Notes

Answer the following in your own words:

**1. Why does this skill have Bash, Read, and Grep, but not Write?**

Bash is used to run Linux health-check commands, Read is used to inspect files, and Grep is used to search for specific information in files. Write is not included because the skill should only collect and analyze evidence, not modify files or system configurations. This makes the workflow safer.

---

**2. Why is `disable-model-invocation: true` useful for this skill?**

It prevents Claude from automatically invoking the skill on its own. The user must manually run /linux-triage when they want to check the server. This provides better control over when the skill runs.

---

**3. What part is performed by Bash, and what part is performed by Claude?**

Bash executes the Linux commands and triage script to collect actual system information, such as Nginx status, port 80, HTTP response, disk usage, and memory usage. Claude analyzes the collected evidence, identifies warnings or incidents, explains the results, and recommends next steps.

---

**4. Why is this better than asking Claude "Is my server healthy?" without giving it evidence?**

The triage script provides actual system data instead of relying on assumptions. Claude can use this evidence to give a more accurate assessment, identify potential problems, and explain its conclusions. This makes the process more reliable and helps avoid unsupported guesses.

---

# Task 7 — Simulate an Nginx Incident and Let the Skill Diagnose It

## Goal

Create a controlled service failure, gather evidence through Bash, and let Claude analyze the evidence without taking recovery action.

### Evidence

#### Screenshot 13 — Output showing Nginx is inactive and the HTTP request fails

<img width="2456" height="306" alt="AdobeExpressPhotos_d3b593fe84d74a01a5784542eb641627_CopyEdited" src="https://github.com/user-attachments/assets/8e9f560c-c98d-4fee-aa59-c53386bdc211" />


---

#### Screenshot 14 — `/linux-triage` output showing failed evidence, most likely cause, and a suggested recovery command

<img width="2714" height="1845" alt="AdobeExpressPhotos_b41b0ef4b19a4219873abc8cd79429b8_CopyEdited" src="https://github.com/user-attachments/assets/0db2c432-1599-473f-ba0f-d4e165c4f5ab" />


---

#### Screenshot 15 — `incident-failure-report.txt` showing the failed checks and your Full Name

<img width="2709" height="2167" alt="AdobeExpressPhotos_f5b5bb32a6924a779aa513a044a9bda7_CopyEdited" src="https://github.com/user-attachments/assets/60c7c673-ea2d-4533-a0d8-d1f51879a31e" />


---

### Notes

Answer the following in your own words:

**1. Which three checks failed?**

The three checks were the Nginx service status check, the attempt to stop the Nginx service, and the HTTP connectivity check. Initially, Nginx remained active because the stop command failed.

---

**2. What evidence supports the conclusion that Nginx is unavailable?**

The evidence includes the Nginx service showing an inactive state and the curl command failing to connect to localhost on port 80. Together, these results indicate that the local web server is unavailable.

---

**3. Did Claude execute the recovery command? Why is that important?**

No, Claude only suggested the recovery command and did not execute it. This is important because the skill must diagnose the problem without making unauthorized changes to the system.

---

**4. Which phase of the Agentic Loop is represented by the Bash report?**

The Bash report represents the Observation phase because Bash collects system information, checks the Nginx status, and records the results as evidence.

---

**5. Which phase is represented by Claude's explanation?**

Claude's explanation represents the Reasoning phase because Claude analyzes the collected evidence, identifies the likely cause, and suggests a possible recovery command without executing it.

---

# Task 8 — Recover Manually, Verify Again, and Write the Incident Summary

## Goal

Recover the service as the human operator and prove that the system is healthy again.

### Evidence

#### Screenshot 16 — Output showing Nginx is active and `curl -I http://localhost` returns 200 OK

<img width="2456" height="1926" alt="AdobeExpressPhotos_e6dd7c5da06c43269d10f20b911ed03f_CopyEdited" src="https://github.com/user-attachments/assets/68ff7b23-9614-4c3b-8b8e-613a41be1288" />


---

#### Screenshot 17 — Second `/linux-triage` output showing successful recovery with no FAIL results

<img width="2377" height="1743" alt="AdobeExpressPhotos_9a168d9b024146c4b196891f3abf44c1_CopyEdited" src="https://github.com/user-attachments/assets/95bd13da-ecc2-41af-b0c3-1950d465fded" />


---

#### Screenshot 18 — Output of `ls -lah reports` showing both `incident-failure-report.txt` and `recovery-report.txt`

<img width="2404" height="468" alt="AdobeExpressPhotos_d00b3da98da64126bbc8a1bd98c4fcc1_CopyEdited" src="https://github.com/user-attachments/assets/273858c7-d348-4491-86fd-aa136f548b82" />


---

#### Screenshot 19 — `incident-summary.md` showing all required sections and your Full Name

<img width="2620" height="2183" alt="AdobeExpressPhotos_ecd75a8670da4aa5adbb4ce30794e10c_CopyEdited" src="https://github.com/user-attachments/assets/ee428e7c-a8ab-4b3d-8ee5-5f353c73c1dd" />



---

### Notes

Answer the following in your own words:

**1. What action did you execute manually?**

I manually restarted the Nginx service using the command sudo systemctl start nginx to recover the web server after the simulated incident.

---

**2. What evidence proves that the service recovered?**

The command systemctl is-active nginx returned active, and curl -I http://localhost returned HTTP/1.1 200 OK. These results confirm that Nginx was running and responding to HTTP requests.

---

**3. Why is the second triage run necessary?**

The second triage run verifies that the recovery was successful and checks whether any failures remain. It provides fresh evidence that the service is healthy after the recovery action.

---

**4. What could go wrong if an AI agent automatically restarted every failed service?**

An AI agent might restart a service unnecessarily, interrupt important operations, cause data loss, or hide the actual problem. Therefore, recovery actions should require proper checks and human approval when necessary.

---

**5. In one sentence, explain the difference between using AI as a chatbot and using AI in this agentic workflow.**

A chatbot mainly responds to questions, whereas an AI agentic workflow uses tools such as Bash to collect evidence, analyses the results, and recommends actions within defined permissions.

---

# Incident Summary

Fill in all seven sections below in your own words.

**Full Name:** Dasari Lavan Kumar

**Date:** 15/10/2026

---

**1. Reported Symptom**

The Nginx web server became unavailable during the simulated incident. HTTP requests to localhost failed because the service was stopped. The goal was to diagnose the problem, recover the service manually, and verify that it was working again.

---

**2. Evidence Collected**

Bash was used to collect evidence about the Nginx service and HTTP connectivity.

systemctl is-active nginx showed inactive after the service was stopped.
systemctl status nginx --no-pager showed that Nginx was inactive.
curl -I http://localhost failed to connect while the service was stopped.
After recovery, the service status was checked again and the HTTP request was repeated.

---

**3. Most Likely Cause**

The most likely cause of the simulated incident was that the Nginx service had been stopped. As a result, the local web server could not respond to HTTP requests. The collected evidence helped identify the service state as the cause of the outage.

---

**4. Human-Approved Recovery Action**

After reviewing the diagnosis, I manually started Nginx using the following command:

sudo systemctl start nginx

The AI skill suggested the recovery command but did not execute it. I performed the recovery as the human operator.

---

**5. Verification**

systemctl is-active nginx

The expected output was active.

I then checked HTTP connectivity using:

curl -I http://localhost

The expected response was HTTP/1.1 200 OK. These results indicate that Nginx had recovered and was responding to HTTP requests.

---

**6. Safety Decision**

The AI skill was allowed to collect evidence, analyse the results, identify the likely cause, and recommend a recovery command. It was not allowed to execute the recovery action. Keeping the recovery under human control helped prevent unintended changes and ensured that the action was reviewed before execution.

---

**7. Agentic Loop Mapping**

The Bash commands represented the Observation phase by collecting evidence about the service and HTTP response. Claude's analysis represented the Reasoning phase by interpreting the evidence and identifying the likely cause. The suggested recovery command represented the Planning phase. I performed the recovery manually, and the second triage run represented Verification, confirming whether the service had returned to a healthy state.

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

# GitHub Repository URL

Paste the URL of your GitHub folder or repository containing the assignment files here:

`Add your URL here`

---

# Submission Instructions

- Add all required screenshots in your submission
- Full Name must be visible in required screenshots and the Bash report
- All written answers must be in your own words
- Do not expose sensitive information (keys, passwords, AWS account IDs, tokens)
- GitHub URL must be included in this document

---

# Completion Checklist

- [ ] Task 1: Healthy baseline confirmed, workspace created (Screenshots 1–2, Notes answered)
- [ ] Task 2: CLAUDE.md created with all four sections (Screenshot 3, Notes answered)
- [ ] Task 3: Five-check plan produced by Claude using read-only tools (Screenshot 4, Notes answered)
- [ ] Task 4: `linux-triage.sh` created, syntax validated, executable permission set (Screenshots 5–8, Notes answered)
- [ ] Task 5: Healthy-state report generated with no FAIL result (Screenshots 9–10, Notes answered)
- [ ] Task 6: `/linux-triage` skill created and run successfully on healthy server (Screenshots 11–12, Notes answered)
- [ ] Task 7: Nginx incident simulated, failed evidence captured, Claude did not execute recovery (Screenshots 13–15, Notes answered)
- [ ] Task 8: Nginx recovered manually, recovery verified, reports saved, incident summary complete (Screenshots 16–19, Notes answered)
- [ ] Incident summary contains all seven required sections
- [ ] LinkedIn post published and URL submitted
- [ ] Full Name visible in all required screenshots and the Bash report
- [ ] Skill does not have Write permission
- [ ] Skill did not execute any recovery commands
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
