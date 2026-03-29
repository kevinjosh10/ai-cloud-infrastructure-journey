# 🚀 Project — Bash Automation Scripts Portfolio (Week 4) ⚙️🐧

---

## 📌 Overview
This project demonstrates practical **Bash scripting and automation skills** by building a collection of real-world scripts used in DevOps and system administration. The goal is to simulate how a **Cloud/DevOps Engineer automates tasks**, manages systems, processes logs, and interacts with cloud infrastructure using Bash.

---

## 🎯 Objectives
- Automate repetitive system tasks using Bash  
- Apply conditionals, loops, and functions in real scripts  
- Process and analyze text data using `awk`, `sed`, and `cut`  
- Debug and optimize scripts using proper techniques  
- Build a **portfolio of 5 practical automation scripts**

---

## 🛠️ Technologies Used
- Bash (Shell scripting)  
- Linux CLI tools (`grep`, `awk`, `sed`, `cut`, `df`, `wc`)  
- nano / vim (file editing)  
- ShellCheck (script linting)  
- AWS CLI (for cloud interaction)

---

## 📂 Project Structure
bash-scripts/
├── backup.sh
├── log_analyzer.sh
├── user_creation.sh
├── disk_check.sh
├── aws_check.sh
└── README.md

---

## 🔥 Scripts Implemented

### 1️⃣ Backup Script (`backup.sh`)
**Description:** Creates backups of directories with a timestamp.  
**Features:**  
- Loops through directories  
- Copies files to backup folder  
- Adds timestamp for versioning  

---

### 2️⃣ Log Analyzer (`log_analyzer.sh`)
**Description:** Analyzes log files and counts log levels.  
**Features:**  
- Counts ERROR, WARN, INFO  
- Uses `grep` for pattern matching  

---

### 3️⃣ User Creation Script (`user_creation.sh`)
**Description:** Creates system users from a list.  
**Features:**  
- Reads usernames from file  
- Creates users automatically  
- Logs actions  

---

### 4️⃣ Disk Usage Monitor (`disk_check.sh`)
**Description:** Monitors disk usage and alerts if usage exceeds threshold.  
**Features:**  
- Uses `df -h`  
- Parses output using `awk` and `sed`  
- Alerts when usage > 80%  

---

### 5️⃣ AWS Resource Checker (`aws_check.sh`)
**Description:** Fetches and displays AWS resources.  
**Features:**  
- Lists EC2 instances  
- Lists S3 buckets  
- Lists IAM users  
- Uses AWS CLI  

---

## ⚙️ How to Run
Make scripts executable:
chmod +x *.sh

Run a script:
./script_name.sh

---

## 🧪 Testing & Debugging
Run in debug mode:
bash -x script_name.sh

Lint scripts:
Use ShellCheck to analyze and fix issues in your scripts.

---

## 📈 Learning Outcomes
- Wrote production-style Bash scripts  
- Automated system and cloud tasks  
- Processed real-world data using CLI tools  
- Debugged and optimized scripts  
- Built a portfolio-ready project  

---

## ☁️ Real-World Applications
- Server backup automation  
- Log monitoring and analysis  
- User provisioning  
- Disk monitoring and alerting  
- Cloud infrastructure inspection  

---

## 🧠 Key Takeaways
- Bash scripting is a core DevOps skill  
- Automation improves efficiency and reliability  
- Text processing tools are powerful in real systems  
- Debugging is essential for maintaining scripts  
- Projects demonstrate real engineering ability  

---

## 🚀 Future Improvements
- Add logging to all scripts  
- Add input validation and error handling  
- Add CLI argument support  
- Schedule scripts using cron jobs  
- Integrate with monitoring tools  

---

## 🏁 Conclusion
This project marks a major step from learning Linux commands to building real automation systems. It demonstrates the ability to think like a DevOps engineer by solving real problems using Bash scripting and automation.