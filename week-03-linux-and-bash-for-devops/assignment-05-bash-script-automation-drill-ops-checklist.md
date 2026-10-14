# Assignment 5 — Bash Script Automation Drill (OPS Checklist)

Part of the DevOps Micro Internship (DMI) with Agentic AI

---

## Purpose

In this assignment, you will practice Bash scripting by building a series of small automation scripts covering environment setup, variables, arrays, loops, file conditionals, if-else logic, and functions. These scripts form the foundation of real-world Linux automation used in DevOps, cloud, and production support environments.

---

# Task 1 — Bash Environment & Workspace Setup

## Goal

Verify that Bash is available on your system and create a clean workspace for this assignment.

### Evidence

#### Screenshot 1 — Output of `echo $SHELL` and `bash --version`

<img width="2986" height="487" alt="AdobeExpressPhotos_4afaf5223d684a3b9516de8c37254d4e_CopyEdited" src="https://github.com/user-attachments/assets/6dc2493e-cf14-4c6c-88cf-5e08ad92d34a" />


---

#### Screenshot 2 — Output of `pwd` and `ls -lah` showing the scripts directory

<img width="3278" height="468" alt="AdobeExpressPhotos_f6d30d327e8844d795279bd680a00c6d_CopyEdited" src="https://github.com/user-attachments/assets/aaeeb185-7dfd-4552-957c-45a8d8f1758e" />


---

### Notes

Answer the following in your own words:

**1. What is Bash?**

Bash stands for Bourne Again Shell. It is a command-line interpreter used in Linux to execute commands and run scripts. It helps automate tasks such as creating files, managing directories, and running programs.

---

**2. What is the difference between shell and Bash?**

A shell is a program that allows users to interact with an operating system using commands. Bash is one specific type of shell. Other shells include Zsh, Fish, and Dash. Bash provides features such as variables, loops, conditions, and functions for writing scripts.

---

**3. Why is it important to confirm the Bash version before writing scripts?**

Checking the Bash version helps ensure that the system supports the commands and features used in a script. Different versions may support different features, so checking the version helps avoid compatibility problems and unexpected errors.

---

# Task 2 — Your First Bash Script

## Goal

Create your first Bash script, make it executable, and run it from the terminal.

### Evidence

#### Screenshot 1 — Content of `first-script.sh`

<img width="1278" height="437" alt="AdobeExpressPhotos_4a58133b187d47098f23cfda1449f168_CopyEdited" src="https://github.com/user-attachments/assets/1f547542-a8d9-468d-9874-7260c41d1696" />


---

#### Screenshot 2 — Output of `./first-script.sh`

<img width="1458" height="336" alt="AdobeExpressPhotos_6f0e55dca6014a3a974840b8c871fd0b_CopyEdited" src="https://github.com/user-attachments/assets/86e6d323-76ed-43e5-9087-ca1057852172" />

---

#### Screenshot 3 — Output of `ls -l first-script.sh` showing executable permission

<img width="1422" height="311" alt="AdobeExpressPhotos_516fe9298cb54532b35088d5dbde2b74_CopyEdited" src="https://github.com/user-attachments/assets/7a05dbe1-c065-4e36-9d86-3c6029560661" />


---

### Notes

Answer the following in your own words:

**1. What is the purpose of `#!/bin/bash`?**

The #!/bin/bash line tells the operating system to use the Bash shell to execute the script. It is called a shebang. It helps the system know which interpreter should run the script.

---

**2. Why do we use `chmod +x` before running a script?**

We use chmod +x to give a file execute permission. This allows us to run the script directly from the terminal using ./script.sh.

---

**3. What is the difference between running a script using `./script.sh` and `bash script.sh`?**

When we use ./script.sh, the script must have execute permission, and the system uses the interpreter specified in the shebang. When we use bash script.sh, Bash executes the script directly, so execute permission is not required. Both methods can run the same script, but they invoke it differently.

---

# Task 3 — Variables: User Information Script

## Goal

Use variables to store and display user-related information.

### Evidence

#### Screenshot 1 — Content of `user-info.sh`


<img width="1310" height="686" alt="AdobeExpressPhotos_20114d3199b34f2fa14a402664bc3d21_CopyEdited" src="https://github.com/user-attachments/assets/5eeede18-9f5a-4d2f-82d1-0641dde505aa" />


---

#### Screenshot 2 — Output of `./user-info.sh`


<img width="1260" height="362" alt="AdobeExpressPhotos_38c0dbfd9bb640c5bb1ff8e62d1ed2cb_CopyEdited" src="https://github.com/user-attachments/assets/d16dbe2d-5801-432e-b724-38c890d841d8" />


---

### Notes

Answer the following in your own words:

**1. What is a variable in Bash?**

A variable in Bash is used to store information such as a name, number, or text. We can use the stored value later in the script whenever we need it.

---

**2. Why should we avoid spaces around the `=` sign when creating variables?**

In Bash, we should not use spaces around the = sign when assigning a value to a variable. If we add spaces, Bash may treat the variable name and value as separate commands or arguments, causing an error.

Correct: name="Lavan Kumar"

Incorrect: name = "Lavan Kumar"

---

**3. How do you access the value stored inside a Bash variable?**

We use the $ symbol followed by the variable name to access its value. For example, if we create a variable using name="Lavan Kumar", we can display its value using echo "$name".

---

# Task 4 — Arrays & Loops: Tools Checklist Script

## Goal

Use arrays and loops to print a checklist of tools used in Bash scripting.

### Evidence

#### Screenshot 1 — Content of `tools-checklist.sh`

Add your screenshot here.

---

#### Screenshot 2 — Output of `./tools-checklist.sh`

Add your screenshot here.

---

### Notes

Answer the following in your own words:

**1. What is an array in Bash?**

Add your answer here.

---

**2. Why are arrays useful in scripts?**

Add your answer here.

---

**3. What does `"${tools[@]}"` mean?**

Add your answer here.

---

**4. What is the purpose of the `for` loop in this script?**

Add your answer here.

---

# Task 5 — Loops: Number Counter Script

## Goal

Use loops to repeat a task multiple times.

### Evidence

#### Screenshot 1 — Content of `counter.sh`

Add your screenshot here.

---

#### Screenshot 2 — Output of `./counter.sh`

Add your screenshot here.

---

### Notes

Answer the following in your own words:

**1. What is a loop?**

Add your answer here.

---

**2. Why do we use loops in Bash scripting?**

Add your answer here.

---

**3. How many times did the loop run in your script?**

Add your answer here.

---

**4. What would you change if you wanted the loop to run 10 times?**

Add your answer here.

---

# Task 6 — Files & Conditionals: File Validation Script

## Goal

Use file checks and conditionals to verify whether files and directories exist.

### Evidence

#### Screenshot 1 — Output of `ls -lah ../test-folder`

Add your screenshot here.

---

#### Screenshot 2 — Content of `file-check.sh`

Add your screenshot here.

---

#### Screenshot 3 — Output of `./file-check.sh`

Add your screenshot here.

---

### Notes

Answer the following in your own words:

**1. What does `-d` check in Bash?**

Add your answer here.

---

**2. What does `-f` check in Bash?**

Add your answer here.

---

**3. Why should file and directory paths be stored in variables?**

Add your answer here.

---

**4. What happens if the file does not exist?**

Add your answer here.

---

# Task 7 — Conditionals: Pass or Retry Script

## Goal

Use if-else conditionals to make decisions based on a variable value.

### Evidence

#### Screenshot 1 — Content of `score-check.sh` with `score=85`

Add your screenshot here.

---

#### Screenshot 2 — Output showing `Result: Pass`

Add your screenshot here.

---

#### Screenshot 3 — Content of `score-check.sh` with `score=55`

Add your screenshot here.

---

#### Screenshot 4 — Output showing `Result: Retry`

Add your screenshot here.

---

### Notes

Answer the following in your own words:

**1. What is the purpose of if-else in Bash?**

Add your answer here.

---

**2. What does `-ge` mean?**

Add your answer here.

---

**3. Why should conditions be tested with different values?**

Add your answer here.

---

**4. How can conditionals help in automation scripts?**

Add your answer here.

---

# Task 8 — Functions: Final Bash Automation Script

## Goal

Create a final Bash script using functions to organize reusable code.

### Evidence

#### Screenshot 1 — Content of `final-automation.sh`

Add your screenshot here.

---

#### Screenshot 2 — Output of `./final-automation.sh`

Add your screenshot here.

---

#### Screenshot 3 — Output of `ls -lah` showing all created scripts

Add your screenshot here.

---

### Notes

Answer the following in your own words:

**1. What is a function in Bash?**

Add your answer here.

---

**2. Why are functions useful in scripts?**

Add your answer here.

---

**3. Which functions did you create in this script?**

Add your answer here.

---

**4. How does this final script combine variables, arrays, loops, conditionals, files, and functions?**

Add your answer here.

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
- All script files must be created and run successfully
- Required notes must be answered clearly for every task
- Do not expose sensitive information (keys, passwords, credentials)

---

# Completion Checklist

- [ ] Task 1: Environment setup verified, workspace created (Screenshots 1–2, Notes answered)
- [ ] Task 2: First script created, executed, permissions verified (Screenshots 1–3, Notes answered)
- [ ] Task 3: Variables script created and run (Screenshots 1–2, Notes answered)
- [ ] Task 4: Arrays and loops script created and run (Screenshots 1–2, Notes answered)
- [ ] Task 5: Counter loop script created and run (Screenshots 1–2, Notes answered)
- [ ] Task 6: File validation script created and run (Screenshots 1–3, Notes answered)
- [ ] Task 7: Pass/Retry conditional script tested with both values (Screenshots 1–4, Notes answered)
- [ ] Task 8: Final automation script created and run (Screenshots 1–3, Notes answered)
- [ ] All scripts run without errors
- [ ] Full Name visible in all required screenshots
- [ ] LinkedIn post published and URL submitted
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
