# Week 003 — Linux Fundamentals II 🐧⚙️  
**Focus:** Process Management, Package Managers, SSH, Cron Jobs, Users & Groups  
**Environment:** Local Linux + AWS EC2 (t2.micro)  
**⏱ Total Time Spent:** ~15–18 Hours  

---

## 💻 Transitioning from Basics to Real System Management

Week 3 was a major shift from learning isolated Linux commands to applying them in real-world scenarios. The focus was on understanding how systems actually run — processes, services, users, and automation — and practicing them on a live EC2 instance.

This week built the foundation for **DevOps and Cloud Engineering**, where systems are not just used, but actively managed, automated, and secured.

---

## ⚙️ Process Management (Day 15)

### 🔹 Key Concepts Learned
- Viewing processes using `ps aux`
- Real-time monitoring with `top` and `htop`
- Managing processes using signals (`kill`, `kill -9`)
- Understanding SIGTERM vs SIGKILL
- Job control (`bg`, `fg`, `jobs`, `Ctrl+Z`)

---

### 🔹 Hands-on Practice
- Ran long processes using `sleep 1000`
- Sent processes to background
- Brought them to foreground and terminated them

---

### ⚡ Outcome
- Understood how Linux handles running programs
- Learned to monitor and control system activity

---

## 📦 Package Management (Day 16)

### 🔹 Tools Explored
- APT (Debian/Ubuntu)
- YUM/DNF (CentOS/RHEL)

---

### 🔹 Commands Practiced
    sudo apt update  
    sudo apt upgrade  
    sudo apt install nginx  
    apt search nginx  
    apt show nginx  
    apt remove nginx  

---

### 🔹 Additional Tools
- `dpkg -l` → list installed packages (Debian)
- `rpm -qa` → list installed packages (CentOS)

---

### ⚡ Outcome
- Learned how software is installed and managed in Linux
- Deployed nginx as a real package-based service

---

## ☁️ AWS EC2 Setup (Day 17)

### 🔹 Tasks Completed
- Launched Ubuntu 22.04 EC2 instance (t2.micro)
- Created and downloaded `.pem` key pair
- Set permissions using:
    chmod 400 mykey.pem  

---

### 🔹 Connected via SSH
    ssh -i mykey.pem ubuntu@your-ec2-ip  

---

### 🔹 System Inspection
    uname -a  
    df -h  
    free -h  

---

### 🔹 Installed Monitoring Tool
    sudo apt install htop  

---

### ⚡ Outcome
- Gained hands-on experience with a real cloud server
- Learned how to access and inspect remote systems

---

## 🔐 SSH & Remote Access (Day 18)

### 🔹 Key Concepts
- SSH key pair generation
- Private vs Public key usage
- Secure authentication without passwords

---

### 🔹 Commands Practiced
    ssh-keygen -t ed25519 -C "your-email@example.com"  

---

### 🔹 GitHub Integration
- Added SSH key to GitHub
- Verified using:
    ssh -T git@github.com  

---

### 🔹 SSH Config Setup
- Simplified connections using `~/.ssh/config`

---

### 🔹 File Transfer
    scp -i mykey.pem file.txt ubuntu@ec2-ip:~/  

---

### ⚡ Outcome
- Understood secure remote communication
- Learned real-world server access workflow

---

## 👤 Users, Groups & Sudo (Day 19)

### 🔹 User Management
    sudo useradd -m newuser  
    sudo passwd newuser  
    sudo userdel -r newuser  

---

### 🔹 Group Management
    sudo groupadd devteam  
    sudo usermod -aG devteam kevin  

---

### 🔹 System Files
- `/etc/passwd` → user info  
- `/etc/shadow` → password hashes  
- `/etc/group` → group info  

---

### 🔹 Sudo Configuration
    sudo visudo  

---

### ⚡ Outcome
- Learned how Linux handles permissions and access
- Simulated multi-user environments

---

## ⏰ Cron Jobs & systemd (Day 20)

### 🔹 Cron Jobs
- Learned scheduling syntax (`* * * * *`)
- Automated tasks using `crontab -e`

---

### 🔹 systemd
    sudo systemctl start nginx  
    sudo systemctl stop nginx  
    sudo systemctl enable nginx  

---

### 🔹 Monitoring Services
    systemctl status nginx  
    journalctl -u nginx  

---

### 🔹 Custom Service
- Created Python script
- Converted into systemd service

---

### ⚡ Outcome
- Automated system tasks
- Managed background services like real infrastructure

---

## 🚀 EC2 Practice & Integration (Day 21)

### 🔹 Tasks Completed
- Installed and configured nginx on EC2  
- Enabled nginx to run on boot  
- Verified using `curl` and browser  

---

### 🔹 Automation
- Created script:
    #!/bin/bash  
    echo "Server time: $(date)" >> ~/server.log  

- Scheduled with cron:
    */5 * * * * /home/kevz/logtime.sh  

---

### 🔹 User Management
- Created new user
- Granted sudo access
- Tested switching users

---

### 🔹 Debugging Experience
- Fixed path issues (`/home/ubuntu` vs `~/`)
- Corrected script formatting errors
- Verified cron execution

---

### ⚡ Outcome
- Combined all concepts into a working system
- Simulated real DevOps workflow

---

## 🧪 Additional Practice

- Completed Bandit levels 6–12 on OverTheWire  
- Practiced file searching, permissions, and command chaining  

---

## ☁️ Cloud Mapping

| Linux Concept | Cloud Equivalent |
|--------------|------------------|
| Process Management | System Monitoring (CloudWatch) |
| Package Manager | AMI / Software Setup |
| SSH | EC2 Secure Access |
| Users & Groups | IAM Roles & Policies |
| Cron Jobs | Scheduled Tasks (CloudWatch Events) |
| systemd | Background Services / EC2 Daemons |

---

## 🧠 Key Takeaways

- Learned how Linux systems actually function internally  
- Understood process management and system monitoring  
- Gained real experience with package installation and services  
- Mastered SSH-based remote access  
- Built automation using cron jobs  
- Managed users and permissions securely  
- Combined everything in a real EC2 environment  

---

## 🚀 Progress Update

Week 3 / 1000 — Transitioned from basic Linux usage → to managing real systems, automation, and cloud servers ⚡  

Building the foundation for **Cloud Engineering, DevOps, and Infrastructure Systems** ☁️  