# 🧠 Week 4 — Linux Fundamentals III: Bash Scripting Notes ⚙️🐧

---

## 🎯 Overview
This week focused on learning **Bash scripting fundamentals** and applying them to build **real-world automation scripts**.

Bash scripting allows automation of repetitive tasks, system management, and DevOps workflows.

---

## 🧱 Bash Basics

### 🔹 Shebang
    #!/bin/bash
- Tells the system to use Bash interpreter

---

### 🔹 Variables
    NAME="Kevin"
    echo $NAME

- No spaces around `=`
- Access using `$`

---

### 🔹 Command Substitution
    DATE=$(date)

- Runs a command and stores output

---

### 🔹 User Input
    read -p "Enter name: " USER

---

### 🔹 Arithmetic
    result=$((5 + 3))

---

## 🔀 Conditionals & Comparisons

### 🔹 If-Else Syntax
    if [ condition ]; then
        command
    elif [ condition ]; then
        command
    else
        command
    fi

---

### 🔹 Numeric Comparisons
- `-eq` → equal  
- `-ne` → not equal  
- `-gt` → greater than  
- `-lt` → less than  

---

### 🔹 String Comparisons
- `==` → equal  
- `!=` → not equal  
- `-z` → empty string  
- `-n` → not empty  

---

### 🔹 File Tests
- `-f` → file exists  
- `-d` → directory exists  
- `-r` → readable  
- `-x` → executable  

---

## 🔁 Loops

### 🔹 For Loop
    for i in {1..5}; do
        echo $i
    done

---

### 🔹 While Loop
    count=1
    while [ $count -le 5 ]; do
        echo $count
        ((count++))
    done

---

### 🔹 Until Loop
    until [ $count -gt 5 ]; do
        echo $count
        ((count++))
    done

---

### 🔹 Loop Control
- `break` → exit loop  
- `continue` → skip iteration  

---

## 🧩 Functions & Arguments

### 🔹 Function Definition
    greet() {
        echo "Hello $1"
    }

---

### 🔹 Call Function
    greet Kevin

---

### 🔹 Special Variables
- `$1` → first argument  
- `$2` → second argument  
- `$@` → all arguments  
- `$#` → number of arguments  
- `$0` → script name  

---

## ⚙️ Exit Codes & Debugging

### 🔹 Exit Codes
    exit 0   # success
    exit 1   # failure

    echo $?  # last command status

---

### 🔹 Debugging
    bash -x script.sh
    set -x   # enable debug
    set +x   # disable debug

---

### 🔹 Safety Options
    set -e   # exit on error
    set -u   # undefined variable error

---

## 🧠 Text Processing Tools

### 🔹 awk
    awk '{print $1}' file.txt
    awk -F',' '{print $2}' data.csv

- Used for column-based processing

---

### 🔹 sed
    sed 's/old/new/g' file.txt
    sed -n '5,10p' file.txt

- Used for replacing and filtering text

---

### 🔹 cut
    cut -d',' -f1,3 data.csv

- Extract specific columns

---

## 🛠️ Useful Commands

- `grep` → search text  
- `wc -l` → count lines  
- `df -h` → disk usage  
- `ls -lh` → file details  
- `chmod +x` → make executable  

---

## 📝 Editors

### 🔹 nano
- Simple and beginner-friendly  
- Ctrl + O → Save  
- Ctrl + X → Exit  

---

### 🔹 vim
- Advanced editor  
- `i` → insert mode  
- `Esc` → exit insert  
- `:wq` → save & quit  

---

## 🚀 Scripts Built (Portfolio)

### 🔹 1. Backup Script
- Copies directories with timestamp

---

### 🔹 2. Log Analyzer
- Counts ERROR, WARN, INFO

---

### 🔹 3. User Creation Script
- Reads users from file and creates them

---

### 🔹 4. Disk Usage Monitor
- Alerts if usage > 80%

---

### 🔹 5. AWS Resource Checker
- Lists EC2, S3, IAM resources

---

## ☁️ Real-World Applications

- Server automation  
- Log monitoring  
- Backup systems  
- User management  
- Cloud infrastructure checks  

---

## 🧠 Key Takeaways

- Bash = automation power  
- Combine loops + conditionals → real workflows  
- Text processing is critical in DevOps  
- Debugging is essential skill  
- Scripts = real engineering output  

---

## 🏁 Final Outcome

By the end of Week 4:
- You can write Bash scripts confidently  
- You can debug and optimize scripts  
- You built 5 real automation scripts  
- You are thinking like a DevOps engineer  

---

## 🚀 Progress Mindset

From:
👉 Running commands manually  

To:
👉 Automating systems with scripts ⚙️🔥  