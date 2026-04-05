# 🚀 Week 5 Project – Build & Debug a Real-World Network (Mini Cloud Lab)

**Project Name:** Local-to-Cloud Networking Simulation  
**Duration:** ~3–5 Hours  
**Focus:** Apply IP Addressing, Subnetting, DNS, DHCP, NAT, and Troubleshooting  

---

## 🎯 Objective

Simulate a real-world network environment and understand how devices communicate over the internet.  
Use networking tools to debug connectivity, resolve domains, and analyze traffic flow like a cloud engineer.

---

## 🧱 Project Overview

You will:
- Use your local machine or EC2 instance  
- Simulate a network flow from **client → router → internet → server**  
- Perform DNS queries, subnet calculations, and troubleshooting  
- Document everything like a real engineer  

---

## 🛠️ Setup Requirements

- Linux system / EC2 instance (Ubuntu preferred)  
- Internet connection  
- Basic terminal knowledge  

Install tools:
    sudo apt update  
    sudo apt install traceroute dnsutils net-tools ipcalc curl -y  

---

## 🔧 Step 1 – Identify Your Network

Run:
    ip addr show  

👉 Note:
- Your **private IP**
- Your **network interface (eth0 / ens5)**

---

## 🌐 Step 2 – Test Connectivity

Run:
    ping -c 4 8.8.8.8  
    ping -c 4 google.com  

✅ Understand:
- If IP ping works → internet is reachable  
- If domain ping works → DNS is working  

---

## 🧭 Step 3 – Trace Network Path

Run:
    traceroute google.com  

👉 Observe:
- Number of hops  
- ISP / cloud network transitions  

---

## 🌍 Step 4 – DNS Deep Dive

Run:
    dig google.com  
    dig google.com MX  
    dig google.com TXT  
    dig +trace google.com  

👉 Document:
- IPv4 addresses  
- Mail servers  
- DNS resolution path  

---

## 📊 Step 5 – Subnetting Practice

Use:
    ipcalc 192.168.1.0/24  

👉 Find:
- Network address  
- Broadcast address  
- Usable IP range  

---

## 🔌 Step 6 – Inspect Open Ports

Run:
    ss -tulpn  

👉 Identify:
- Running services  
- Open ports (e.g., 22 for SSH)

---

## 🌐 Step 7 – Test HTTP Requests

Run:
    curl -v http://google.com  

👉 Observe:
- HTTP headers  
- Response status (200 OK, redirects)

---

## 🔄 Step 8 – Understand Your Public IP

Run:
    curl ifconfig.me  

👉 This shows:
- Your **public IP (after NAT)**

---

## 🧠 Step 9 – Draw Network Flow

Create a diagram:

    [Your Machine]
       |
    Private IP
       |
    [Router / NAT]
       |
    Public IP
       |
    [Internet]
       |
    [DNS Server]
       |
    [Web Server]

👉 Label:
- Private IP  
- Public IP  
- Where NAT happens  
- Where DNS happens  

---

## 📝 Deliverables

Create a Markdown file and include:

### 1️⃣ System Info
- Private IP  
- Public IP  

---

### 2️⃣ Command Outputs
Include outputs of:
- ping  
- traceroute  
- dig  
- ss  
- curl  

---

### 3️⃣ Subnetting Results
- Network  
- Broadcast  
- Range  

---

### 4️⃣ DNS Analysis
- A record  
- MX record  
- Observations  

---

### 5️⃣ Network Diagram
- Hand-drawn or digital  

---

### 6️⃣ Key Learnings
- What you understood about networking  
- Challenges faced  

---

## 🧠 Concepts Applied

- IPv4 Addressing  
- Subnetting & CIDR  
- DNS Resolution  
- DHCP (conceptual)  
- NAT (real-world via ISP/router)  
- Network Troubleshooting  

---

## 🔥 Bonus Challenge (Optional)

- SSH into EC2 and repeat all steps  
- Host a simple web server:
    sudo apt install nginx -y  

- Test:
    curl localhost  
    curl http://<your-public-ip>  

---

## 🚀 Outcome

By completing this project, you will:
- Think like a network engineer  
- Debug connectivity issues confidently  
- Understand real-world cloud networking flow  
- Be ready for AWS VPC concepts  

---

## ✅ Project Status

**Week 5 Project Complete** 🎉  