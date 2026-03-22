# Week 003 — Linux Fundamentals II Notes 🐧📘  
**Focus:** Process Management, Package Managers, SSH, Cron Jobs, Users & Groups  

---

## ⚙️ Process Management

### 🔹 Viewing Processes
    ps aux

- Lists all running processes  
- Shows user, PID, CPU, memory, command  

---

### 🔹 Real-Time Monitoring
    top
    htop

- Interactive process viewers  
- `q` → quit  
- `k` → kill process (inside top/htop)  

---

### 🔹 Killing Processes
    kill PID
    kill -9 PID

- `kill` → sends SIGTERM (graceful stop)  
- `kill -9` → sends SIGKILL (force kill)  

---

### 🔹 Job Control
    Ctrl + Z   → pause process  
    bg         → run in background  
    fg         → bring to foreground  
    jobs       → list background jobs  

---

## 📦 Package Management

### 🔹 APT (Ubuntu/Debian)
    sudo apt update
    sudo apt upgrade
    sudo apt install package-name

---

### 🔹 Searching & Info
    apt search nginx
    apt show nginx

---

### 🔹 Removing Packages
    sudo apt remove package-name

---

### 🔹 Other Package Managers
- YUM / DNF (CentOS/RHEL)
    sudo yum install package-name
    yum list installed

---

### 🔹 Package Listing
    dpkg -l     (Debian)
    rpm -qa     (CentOS)

---

## ☁️ EC2 Basics

### 🔹 Connect to Instance
    ssh -i mykey.pem ubuntu@your-ec2-ip

---

### 🔹 System Info
    uname -a
    df -h
    free -h

---

### 🔹 Monitoring Tool
    sudo apt install htop

---

## 🔐 SSH & Remote Access

### 🔹 Generate Key Pair
    ssh-keygen -t ed25519 -C "your-email@example.com"

---

### 🔹 Key Files
- Private key → `~/.ssh/id_ed25519` (keep secret)  
- Public key → `~/.ssh/id_ed25519.pub` (share)  

---

### 🔹 GitHub SSH Test
    ssh -T git@github.com

---

### 🔹 SSH Config
- File: `~/.ssh/config`  
- Used to simplify SSH connections  

---

### 🔹 File Transfer
    scp -i mykey.pem file.txt ubuntu@ec2-ip:~/

---

## 👤 Users, Groups & Sudo

### 🔹 User Management
    sudo useradd -m newuser
    sudo passwd newuser
    sudo userdel -r newuser

---

### 🔹 Group Management
    sudo groupadd devteam
    sudo usermod -aG devteam username

---

### 🔹 Important Files
- `/etc/passwd` → user details  
- `/etc/shadow` → password hashes  
- `/etc/group` → group info  

---

### 🔹 Sudo
    sudo visudo

- Used to safely edit sudo permissions  

---

## ⏰ Cron Jobs

### 🔹 Cron Syntax
    * * * * *
    | | | | |
    | | | | └── Day of week
    | | | └──── Month
    | | └────── Day of month
    | └──────── Hour
    └────────── Minute

---

### 🔹 Common Examples
    * * * * *        → Every minute
    */5 * * * *      → Every 5 minutes
    0 * * * *        → Every hour

---

### 🔹 Edit Cron Jobs
    crontab -e

---

### 🔹 View Cron Jobs
    crontab -l

---

### 🔹 Example Task
    */5 * * * * /home/user/script.sh

---

## ⚙️ systemd (Service Management)

### 🔹 Basic Commands
    sudo systemctl start service
    sudo systemctl stop service
    sudo systemctl restart service

---

### 🔹 Enable at Boot
    sudo systemctl enable service
    sudo systemctl disable service

---

### 🔹 Check Status
    systemctl status service

---

### 🔹 Logs
    journalctl -u service-name
    journalctl -u service-name -f

---

## 🔧 Shell Scripting Basics

### 🔹 Simple Script
    #!/bin/bash
    echo "Hello World"

---

### 🔹 Logging Example
    #!/bin/bash
    echo "Server time: $(date)" >> ~/server.log

---

### 🔹 Permissions
    chmod +x script.sh

---

### 🔹 Run Script
    ./script.sh

---

## 🧠 Key Concepts Summary

- Linux processes can be monitored and controlled  
- Packages are installed and managed using system tools  
- SSH enables secure remote access to servers  
- Cron automates repetitive tasks  
- systemd manages background services  
- Users and permissions control system access  
- Scripts help automate workflows  

---

## 🚀 Final Understanding

Week 3 focused on transforming Linux knowledge into **practical system management skills**.  

Instead of just running commands, I learned how to:
- Monitor systems  
- Automate tasks  
- Manage services  
- Control access  
- Work on real cloud servers  

This forms the foundation for **DevOps, Cloud Engineering, and Infrastructure Management** ☁️  