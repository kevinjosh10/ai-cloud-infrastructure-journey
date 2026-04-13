# Week 06 – Networking Fundamentals II Project

**Date:** Week 6 Completion  
**Duration:** ~3–5 Hours  
**Focus:** HTTP/HTTPS, TLS, Ports, Firewalls, Load Balancing & Troubleshooting  

---

## 🎯 Objective

Apply networking concepts in a real-world cloud setup.  
Deploy a web server, secure it, expose it via HTTP, and troubleshoot connectivity issues like an engineer.  

---

## ✅ What I Built

### 🌐 Project: NGINX Web Server Deployment on EC2

- Deployed a Linux server on AWS EC2  
- Installed and configured NGINX  
- Served a static HTML page  
- Configured Security Groups for public access  
- Tested connectivity using browser and CLI tools  

---

## 🏗️ Architecture Overview

User (Browser)  
   ↓  
Internet  
   ↓  
AWS Security Group (Firewall Rules)  
   ↓  
EC2 Instance (Ubuntu)  
   ↓  
NGINX Web Server (Port 80)  
   ↓  
Static HTML Page  

---

## ⚙️ Step-by-Step Implementation

### 1️⃣ Launched EC2 Instance
- Selected Ubuntu AMI  
- Configured key pair for SSH  
- Enabled:
    Port 22 (SSH)  
    Port 80 (HTTP)  

---

### 2️⃣ Connected via SSH
    ssh -i key.pem ubuntu@<public-ip>  

---

### 3️⃣ Installed NGINX
    sudo apt update  
    sudo apt install nginx -y  

---

### 4️⃣ Started & Enabled NGINX
    sudo systemctl start nginx  
    sudo systemctl enable nginx  

---

### 5️⃣ Created Static Website
    cd /var/www/html  
    sudo nano index.html  

HTML Content:
    <h1>Week 6 Project 🚀</h1>  
    <p>Deployed using NGINX on AWS EC2</p>  

---

### 6️⃣ Accessed Website
- Opened browser:
    http://<EC2-Public-IP>  

- Verified successful deployment  

---

## 🔐 Security Configuration

### 🔹 Security Group Rules
- Allowed:
    Port 22 → SSH access  
    Port 80 → HTTP access  

- Blocked all unnecessary ports  

---

### 🔹 Firewall Understanding
- AWS Security Group = Stateful firewall  
- Allowed inbound → outbound automatically allowed  

---

## 🔍 Testing & Validation

### 🔹 Checked Running Services
    sudo systemctl status nginx  

---

### 🔹 Checked Open Ports
    ss -tulpn  

---

### 🔹 Tested HTTP Response
    curl http://<public-ip>  

---

### 🔹 Verified DNS (Optional)
    dig +short example.com  

---

## 🛠️ Troubleshooting Performed

### ❌ Issue: Website not loading

#### ✅ Debug Steps:
- Checked EC2 instance status  
- Verified Security Group rules (port 80 open)  
- Confirmed NGINX service running  
- Checked correct public IP  

---

### ❌ Issue: Connection refused

#### ✅ Fix:
- Restarted NGINX  
    sudo systemctl restart nginx  

---

## 🧠 Key Concepts Applied

- HTTP request/response cycle  
- Ports (80, 22) and protocols  
- Firewall rules (Security Groups)  
- Client-server communication  
- Basic troubleshooting methodology  

---

## 🚀 Improvements (Next Steps)

- Enable HTTPS using SSL/TLS  
- Use reverse proxy configuration  
- Deploy multiple EC2 instances  
- Add Load Balancer (ALB)  
- Attach domain using DNS  

---

## 🔄 Mindset Shift

Moved from:

> Learning networking concepts theoretically  

To:

> Deploying and debugging real cloud infrastructure  

---

## 💭 Reflection

This project simulated a real-world production setup.

Built:
- Confidence in deploying web servers  
- Understanding of traffic flow from browser to server  
- Ability to troubleshoot network issues  
- Strong foundation for cloud and DevOps workflows  

---

**Status:** Week 6 Project Complete  
**Outcome:** Real-world Networking Implementation Achieved 🚀  