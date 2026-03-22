# Week 003 — Linux Fundamentals II 🐧⚙️  
**Focus:** Process Management, Package Managers, SSH, Cron Jobs, Users & Groups  
**Goal:** Move from basic Linux usage → to managing real systems on a cloud server (EC2)  

---

## 🎯 Week Objectives

- Understand how Linux handles processes and system resources  
- Learn how to install and manage software using package managers  
- Gain hands-on experience with AWS EC2 (real cloud server)  
- Master SSH for secure remote access  
- Implement task automation using cron jobs  
- Manage users, groups, and permissions securely  
- Work with services using systemd  

---

## 🗓️ Day-wise Roadmap

---

### 📅 Day 15 — Process Management

#### 🔹 Learn
- `ps aux` — list all running processes  
- `top`, `htop` — interactive process monitoring  
- `kill`, `kill -9` — terminate processes  
- Signals: SIGTERM vs SIGKILL  
- Job control: `bg`, `fg`, `jobs`, `Ctrl+Z`  

#### 🔹 Practice
- Run:
    sleep 1000  
- Send to background, bring to foreground  
- Kill the process  

---

### 📅 Day 16 — Package Managers

#### 🔹 Learn (APT)
    sudo apt update  
    sudo apt upgrade  
    sudo apt install package-name  

#### 🔹 Explore
    apt search nginx  
    apt show nginx  
    apt remove nginx  

#### 🔹 Learn (YUM/DNF)
    sudo yum install package-name  
    yum list installed  

#### 🔹 Practice
- Install nginx  
- Start service and verify:
    systemctl status nginx  

#### 🔹 Additional
    dpkg -l  
    rpm -qa  

---

### 📅 Day 17 — Launch EC2 Instance

#### 🔹 Tasks
- Launch Ubuntu 22.04 EC2 (t2.micro)  
- Create key pair (.pem file)  
- Set permissions:
    chmod 400 mykey.pem  

#### 🔹 Connect via SSH
    ssh -i mykey.pem ubuntu@your-ec2-ip  

#### 🔹 Inspect System
    uname -a  
    df -h  
    free -h  

#### 🔹 Install Tool
    sudo apt install htop  

---

### 📅 Day 18 — SSH & Remote Access

#### 🔹 Generate SSH Key
    ssh-keygen -t ed25519 -C "your-email@example.com"  

#### 🔹 Understand
- Private key (`~/.ssh/id_ed25519`)  
- Public key (`~/.ssh/id_ed25519.pub`)  

#### 🔹 GitHub Setup
- Add SSH key → Settings → SSH Keys  
- Test:
    ssh -T git@github.com  

#### 🔹 SSH Config
- Configure `~/.ssh/config` for easy access  

#### 🔹 File Transfer
    scp -i mykey.pem file.txt ubuntu@ec2-ip:~/  

---

### 📅 Day 19 — Users, Groups & Sudo

#### 🔹 User Management
    sudo useradd -m newuser  
    sudo passwd newuser  
    sudo userdel -r newuser  

#### 🔹 Group Management
    sudo groupadd devteam  
    sudo usermod -aG devteam kevin  

#### 🔹 System Files
- `/etc/passwd`  
- `/etc/shadow`  
- `/etc/group`  

#### 🔹 Sudo
    sudo visudo  

#### 🔹 Practice
- Create user  
- Add to group  
- Switch user:
    su - newuser  

---

### 📅 Day 20 — Cron Jobs & systemd

#### 🔹 Cron Syntax
    * * * * *  

#### 🔹 Schedule Tasks
    crontab -e  

#### 🔹 Example
    * * * * * date >> ~/log.txt  

---

#### 🔹 systemd Basics
    systemctl start service  
    systemctl stop service  
    systemctl enable service  

---

#### 🔹 Monitoring
    systemctl status service  
    journalctl -u service-name  

---

#### 🔹 Practice
- Create Python script  
- Convert into systemd service  

---

### 📅 Day 21 — Week 3 Review & EC2 Practice

#### 🔹 Tasks
- Install nginx on EC2  
- Start and enable nginx  
- Verify using curl  

---

#### 🔹 Automation
- Create script:
    #!/bin/bash  
    echo "Server time: $(date)" >> ~/server.log  

- Schedule:
    */5 * * * * /home/yourusername/logtime.sh  

---

#### 🔹 User Management
- Create new user  
- Grant sudo access  
- Test switching users  

---

#### 🔹 Practice
- Complete Bandit levels 6–12  

---

#### 🔹 Reflection
- Write Week 3 summary in GitHub README (min 3 paragraphs)  

---

## 🧠 Expected Outcomes

By the end of Week 3, you should be able to:

- Manage running processes and system resources  
- Install and manage software packages  
- Access and control a remote server via SSH  
- Automate tasks using cron jobs  
- Manage users, groups, and permissions  
- Run and monitor services using systemd  
- Work confidently on a real EC2 instance  

---

## 🚀 Progress Marker

Week 3 / 1000 — From learning Linux basics → to managing real systems and automation ⚡  