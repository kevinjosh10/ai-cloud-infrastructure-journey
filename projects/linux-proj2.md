# Project — Text Processing & User Automation (Day 026) 🔎⚙️

---

## 📌 Overview

This project demonstrates practical **text processing and system automation in Linux** by combining tools like `awk`, `sed`, and `cut` with Bash scripting.

The goal is to simulate how a Cloud/DevOps Engineer handles **log processing, user management, and data extraction** in real-world systems.

---

## 🎯 Objectives

- Process and analyze structured text using `awk`  
- Extract data using `cut`  
- Modify logs using `sed`  
- Automate user creation using Bash scripts  
- Implement logging for system operations  
- Work with real system files like `/etc/passwd`  

---

## 🏗️ Architecture

Input Files (users.txt / logs) → Text Processing Tools (awk, sed, cut) → Bash Script Automation → System Changes (Users, Logs) → Output Logs

---

## 🔎 1. Data Processing with awk

- Print first column:
  awk '{print $1}' file.txt

- Use delimiter (CSV):
  awk -F',' '{print $2}' data.csv

- Extract system usernames:
  awk -F':' '{print $1}' /etc/passwd

- Practice:
  Create a file and extract specific columns

---

## ✂️ 2. Column Extraction with cut

- Basic usage:
  cut -d',' -f1,3 data.csv

- Extract usernames:
  cut -d':' -f1 /etc/passwd

- Practice:
  Compare output with awk

---

## 🔁 3. Text Transformation with sed

- Replace text:
  sed 's/old/new/g' file.txt

- Modify file directly:
  sed -i 's/error/warning/g' logfile.txt

- Print specific lines:
  sed -n '5,10p' file.txt

- Practice:
  Create a sample log file and replace text

---

## 👤 4. User Management Automation Script

- Create script:
  nano create_users.sh

- Script:
  #!/bin/bash

  INPUT="users.txt"
  LOG="user_creation.log"

  read -s -p "Enter default password: " DEFAULT_PASS
  echo ""

  while read username
  do
      [ -z "$username" ] && continue

      if id "$username" &>/dev/null; then
          echo "User $username already exists. Skipping..."
          echo "$(date) - Skipped existing user: $username" >> "$LOG"
      else
          sudo useradd "$username"
          echo "$username:$DEFAULT_PASS" | sudo chpasswd
          echo "User $username created."
          echo "$(date) - Created user: $username" >> "$LOG"
      fi

  done < "$INPUT"

  echo "Process completed!"

---

## 📂 5. Input & Log Files

- users.txt:
  user1
  user2
  user3

- logfile.txt:
  error: failed connection
  info: retrying
  error: timeout

- user_creation.log:
  Stores script execution logs

---

## 🧪 6. Log Processing Task

- Replace all errors:
  sed -i 's/error/warning/g' logfile.txt

- Verify:
  cat logfile.txt

---

## 🔍 7. System Data Extraction

- Extract all system users:
  cut -d':' -f1 /etc/passwd

- Alternative:
  awk -F':' '{print $1}' /etc/passwd

---

## ⚙️ 8. Script Testing & Validation

- Test script:
  bash create_users.sh

- Check users:
  id username

- View logs:
  cat user_creation.log

- Analyze script:
  Use ShellCheck (shellcheck.net)

---

## 🧠 Key Learnings

- Learned how to process and transform text efficiently  
- Understood real-world log handling techniques  
- Built automation for system-level user management  
- Applied multiple tools together in a workflow  
- Strengthened debugging and scripting skills  

---

## 🚀 Future Improvements

- Generate random passwords per user  
- Add validation for usernames  
- Process multiple log files automatically  
- Integrate with cron jobs for scheduling  
- Extend script for user deletion and updates  

---

## 🏁 Conclusion

This project marks the transition from basic scripting to **real-world data processing and automation workflows**. It builds a strong foundation for handling logs, system data, and automation tasks in **Cloud and DevOps environments**.  