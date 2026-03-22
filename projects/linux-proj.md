# Project — Linux Server Automation & Management (Week 003) ⚙️☁️

---

## 📌 Overview

This project demonstrates practical Linux system administration by combining process management, package management, service control, automation, and user management into one complete workflow.

The goal is to simulate how a Cloud/DevOps Engineer manages a real server — including deploying services, automating tasks, handling system processes, and securing access.

---

## 🎯 Objectives

- Manage Linux processes and system resources  
- Install and manage software using package managers  
- Deploy and manage a web server (nginx)  
- Automate tasks using cron jobs  
- Manage users, groups, and permissions  
- Work with systemd for service management  
- Practice on a real or virtual Linux environment  

---

## 🏗️ Architecture

Local Linux / EC2 Instance → Linux OS → Processes + Packages + Services → Automation (Script + Cron) → Logs

---

## ⚙️ 1. Process Management

- View processes:
  ps aux

- Monitor in real time:
  top
  htop

- Kill processes:
  kill PID
  kill -9 PID

- Job control:
  Ctrl+Z → pause  
  bg → background  
  fg → foreground  
  jobs → list jobs  

- Practice:
  sleep 1000  
  (send to background, bring to foreground, kill)

---

## 📦 2. Package Management

- Update system:
  sudo apt update
  sudo apt upgrade

- Install package:
  sudo apt install nginx

- Search:
  apt search nginx

- Show details:
  apt show nginx

- Remove:
  sudo apt remove nginx

- Other managers:
  sudo yum install package-name
  yum list installed

- List packages:
  dpkg -l
  rpm -qa

---

## ☁️ 3. EC2 Setup

- Connect to server:
  ssh -i mykey.pem ubuntu@your-ec2-ip

- System info:
  uname -a
  df -h
  free -h

- Install monitoring:
  sudo apt install htop

---

## 🔐 4. SSH & Remote Access

- Generate key:
  ssh-keygen -t ed25519 -C "your-email@example.com"

- Test GitHub:
  ssh -T git@github.com

- Transfer files:
  scp -i mykey.pem file.txt ubuntu@ec2-ip:~/

- SSH config file:
  ~/.ssh/config (Host, HostName, User, IdentityFile)

---

## 👤 5. Users, Groups & Sudo

- Create user:
  sudo useradd -m devuser
  sudo passwd devuser

- Delete user:
  sudo userdel -r devuser

- Create group:
  sudo groupadd devteam

- Add to group:
  sudo usermod -aG devteam devuser

- Switch user:
  su - devuser

- Test sudo:
  sudo apt update

- Important files:
  /etc/passwd
  /etc/shadow
  /etc/group

---

## ⏰ 6. Cron Jobs (Automation)

- Cron syntax:
  * * * * *
  (minute hour day month weekday)

- Edit cron:
  crontab -e

- View cron:
  crontab -l

- Script:
  #!/bin/bash
  echo "Server time: $(date)" >> ~/server.log

- Schedule:
  */5 * * * * /home/yourusername/logtime.sh

- Verify:
  cat ~/server.log

---

## ⚙️ 7. systemd (Service Management)

- Start service:
  sudo systemctl start nginx

- Stop service:
  sudo systemctl stop nginx

- Restart:
  sudo systemctl restart nginx

- Enable at boot:
  sudo systemctl enable nginx

- Disable:
  sudo systemctl disable nginx

- Status:
  systemctl status nginx

- Logs:
  journalctl -u nginx
  journalctl -u nginx -f

---

## 🌐 8. NGINX Deployment

- Install:
  sudo apt install nginx -y

- Start:
  sudo systemctl start nginx

- Enable:
  sudo systemctl enable nginx

- Verify:
  curl localhost

---

## 📂 Project Files

- logtime.sh → automation script  
- server.log → log output  
- crontab → scheduler  

---

## 🧠 Key Learnings

- Learned how Linux systems are managed in real environments  
- Understood automation using cron jobs  
- Gained experience with service management using systemd  
- Practiced user and permission control  
- Improved debugging and troubleshooting skills  

---

## 🚀 Future Improvements

- Add CPU, RAM, disk monitoring  
- Build alert system  
- Deploy fully on EC2  
- Integrate with cloud logging  

---

## 🏁 Conclusion

This project marks the transition from learning Linux commands to building real system workflows. It forms a strong foundation for Cloud Engineering, DevOps, and Infrastructure Management.