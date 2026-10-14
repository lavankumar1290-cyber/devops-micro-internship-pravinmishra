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

<img width="1329" height="698" alt="AdobeExpressPhotos_4b02e5bee7ad4bd88ba18f2d592bfbcc_CopyEdited" src="https://github.com/user-attachments/assets/72b0c83a-ff46-41ef-9474-3e94bad6216e" />


---

#### Screenshot 2 — Output of `./tools-checklist.sh`

<img width="1328" height="432" alt="AdobeExpressPhotos_0b23b38663b14e96bcc6cae93c566317_CopyEdited" src="https://github.com/user-attachments/assets/ac071300-4375-4329-81d7-7027316901d2" />


---

### Notes

Answer the following in your own words:

**1. What is an array in Bash?**

An array in Bash is a variable that can store multiple values under a single name. For example, we can store tool names such as Bash, Git, Docker, and Linux in one array.

---

**2. Why are arrays useful in scripts?**

Arrays are useful because they allow us to store and manage multiple values easily. Instead of creating separate variables for every tool, we can store all the tool names in one array and process them using loops.

---

**3. What does `"${tools[@]}"` mean?**

"${tools[@]}" is used to access all the elements of the tools array. The double quotes help preserve each element as a separate item, even if an element contains spaces.

---

**4. What is the purpose of the `for` loop in this script?**

The for loop is used to go through each element in the tools array one by one. It prints every tool with a checklist symbol until all the tools have been displayed.

---

# Task 5 — Loops: Number Counter Script

## Goal

Use loops to repeat a task multiple times.

### Evidence

#### Screenshot 1 — Content of `counter.sh`

<img width="1177" height="596" alt="AdobeExpressPhotos_25cb5deb9cca4c58a2cc1caa9540a46b_CopyEdited" src="https://github.com/user-attachments/assets/13bffc21-0787-447b-a8ad-e6bcdfd5e9c4" />


---

#### Screenshot 2 — Output of `./counter.sh`

<img width="1263" height="605" alt="AdobeExpressPhotos_1855a9c701bc459b9b8e4bb8f7c7cc02_CopyEdited" src="https://github.com/user-attachments/assets/943423e0-5e8c-4815-9b2c-76a901af0664" />


---

### Notes

Answer the following in your own words:

**1. What is a loop?**

A loop is a programming structure that repeats a set of commands multiple times until a specified condition or range is completed.

---

**2. Why do we use loops in Bash scripting?**

We use loops in Bash scripting to repeat tasks automatically without writing the same commands multiple times. They make scripts shorter, easier to understand, and more efficient.

---

**3. How many times did the loop run in your script?**

The loop ran 10 times because it used {1..10} to generate numbers from 1 to 10. Each iteration printed one number.

---

**4. What would you change if you wanted the loop to run 10 times?**

The loop already runs 10 times using for i in {1..10}. If it were set to a different range, I would change the range to {1..10} to make it run 10 times.
---

# Task 6 — Files & Conditionals: File Validation Script

## Goal

Use file checks and conditionals to verify whether files and directories exist.

### Evidence

#### Screenshot 1 — Output of `ls -lah ../test-folder`

<img width="1361" height="341" alt="AdobeExpressPhotos_32411a62fe6e4f9f8c89be6329b6b541_CopyEdited" src="https://github.com/user-attachments/assets/3fadd824-a4a2-4e24-ad58-44ce371b2c8a" />


---

#### Screenshot 2 — Content of `file-check.sh`

<img width="1352" height="1111" alt="AdobeExpressPhotos_df45cddb796c4c8482be219601b465b6_CopyEdited" src="https://github.com/user-attachments/assets/b4c82488-f08a-470e-970d-48450ba7b81f" />


---

#### Screenshot 3 — Output of `./file-check.sh`

<img width="1301" height="316" alt="AdobeExpressPhotos_532b9d6acc0647d782a4c31cb4f2bab3_CopyEdited" src="https://github.com/user-attachments/assets/49caa32f-1f1e-40bd-a0ee-9eb9d2436b41" />


---

### Notes

Answer the following in your own words:

**1. What does `-d` check in Bash?**

In Bash, -d checks whether a given path exists and is a directory. If the directory exists, the condition returns true; otherwise, it returns false.

---

**2. What does `-f` check in Bash?**

In Bash, -f checks whether a given path exists and is a regular file. If the file exists, the condition returns true; otherwise, it returns false.

---

**3. Why should file and directory paths be stored in variables?**

Storing file and directory paths in variables makes scripts easier to read, maintain, and update. If a path changes, we can update the variable in one place instead of changing it throughout the script.

---

**4. What happens if the file does not exist?**

If the file does not exist, the -f condition returns false, and the script executes the else block. In our script, it displays an error message saying that the file does not exist.

---

# Task 7 — Conditionals: Pass or Retry Script

## Goal

Use if-else conditionals to make decisions based on a variable value.

### Evidence

#### Screenshot 1 — Content of `score-check.sh` with `score=85`

<img width="1353" height="794" alt="AdobeExpressPhotos_b5aacbc693a249198f117d41f635b5fa_CopyEdited" src="https://github.com/user-attachments/assets/43fee953-421a-4855-aeb9-2ae3aa06ac62" />


---

#### Screenshot 2 — Output showing `Result: Pass`

<img width="1338" height="274" alt="AdobeExpressPhotos_2563d79ce1d640e4af1d4b259a3f927e_CopyEdited" src="https://github.com/user-attachments/assets/dfd5ad55-efa9-41a2-bca2-4b23a7cf1b1a" />


---

#### Screenshot 3 — Content of `score-check.sh` with `score=55`

<img width="1434" height="798" alt="AdobeExpressPhotos_c3bbfac6173f437294c19dcb78d78e62_CopyEdited" src="https://github.com/user-attachments/assets/b1902a31-e8c3-4b9d-a176-386c5c2cd9f3" />


---

#### Screenshot 4 — Output showing `Result: Retry`

<img width="1310" height="790" alt="AdobeExpressPhotos_dcfa16aa240440e2ad86ae7c9edbd786_CopyEdited" src="https://github.com/user-attachments/assets/b1efb203-c21c-43ed-bd0d-9bbf90eaca23" />


---

### Notes

Answer the following in your own words:

**1. What is the purpose of if-else in Bash?**

The purpose of if-else in Bash is to make decisions based on a condition. If the condition is true, the commands inside the if block are executed. Otherwise, the commands inside the else block are executed.

---

**2. What does `-ge` mean?**

In Bash, -ge means "greater than or equal to." It is used to compare two numbers. For example, [ "$score" -ge 40 ] checks whether the score is 40 or higher.

---

**3. Why should conditions be tested with different values?**

We should test conditions with different values to make sure the script works correctly in different situations. For example, testing scores of 85, 55, and 30 helps verify that the script displays the correct result for both passing and failing scores.

---

**4. How can conditionals help in automation scripts?**

Conditionals help automation scripts make decisions automatically. They can check whether files exist, verify service status, validate user input, and perform different actions depending on the results. This makes automation more reliable and efficient.

---

# Task 8 — Functions: Final Bash Automation Script

## Goal

Create a final Bash script using functions to organize reusable code.

### Evidence

#### Screenshot 1 — Content of `final-automation.sh`

<img width="1831" height="2268" alt="AdobeExpressPhotos_53e4e26dda444d8d876a870b1ef4e9d4_CopyEdited" src="https://github.com/user-attachments/assets/3b524aa1-9ce1-4ae9-8a02-16e9725ac627" />


---

#### Screenshot 2 — Output of `./final-automation.sh`

<img width="1327" height="528" alt="AdobeExpressPhotos_7453b3d93693421a83239e748042d8f2_CopyEdited" src="https://github.com/user-attachments/assets/1dbd57c1-ae6f-48b4-9624-9dfe1e9d94f3" />


---

#### Screenshot 3 — Output of `ls -lah` showing all created scripts

<img width="1307" height="626" alt="AdobeExpressPhotos_50a9487ed65d4c58a088c1824e9d1666_CopyEdited" src="https://github.com/user-attachments/assets/7e9cb1bc-d7a0-418e-827d-86a7e8be875c" />


---

### Notes

Answer the following in your own words:

**1. What is a function in Bash?**

A function in Bash is a named block of code that performs a specific task. We can call the function whenever we need to execute that task in a script.

---

**2. Why are functions useful in scripts?**

Functions are useful because they help organize code into smaller, reusable sections. They reduce code repetition and make scripts easier to read, understand, test, and maintain.

---

**3. Which functions did you create in this script?**

I created five functions: show_header(), show_user_info(), show_tools(), check_directory(), and show_footer(). Each function performs a specific task, such as displaying user information, listing DevOps tools, checking whether a directory exists, or displaying a completion message.

---

**4. How does this final script combine variables, arrays, loops, conditionals, files, and functions?**

The script uses variables to store user information, an array to store DevOps tool names, and a loop to display each tool. It uses an if-else conditional to check whether the test directory exists. The script also works with file and directory paths and uses functions to organize these tasks into separate sections. This demonstrates how different Bash scripting concepts can work together to automate tasks.

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
