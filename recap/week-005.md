# 🔁 Week 5 Recap – Networking Fundamentals I

**Focus:** IP Addressing, Subnetting, CIDR, DNS, DHCP, NAT  
**Goal:** Reinforce core networking concepts required for cloud infrastructure  

---

## 🎯 What This Week Was About

Week 5 built the **foundation of networking**, which is critical for:
- Cloud infrastructure (AWS, Azure, GCP)
- System design
- Debugging real-world connectivity issues  

👉 This week connected how devices communicate **from your machine → internet → server**

---

## 🌐 1. IPv4 Addressing (Core Foundation)

### 📌 Key Learnings
- IPv4 = **32-bit address**, divided into 4 octets  
- Each octet ranges from **0–255**

Example:
    192.168.1.100  

---

### 🔒 Private IP Ranges (Must Memorize)
- 10.0.0.0/8  
- 172.16.0.0/12  
- 192.168.0.0/16  

✔ Used inside networks  
✔ Not accessible from the internet  

---

### 🌍 Public vs Private IP
- Public IP → internet-facing  
- Private IP → internal use  
- NAT translates private → public  

---

### 🔁 Loopback
- 127.0.0.1 → localhost  

---

## 📊 2. Subnetting & CIDR (Most Important Skill)

### 📌 What You Learned
- CIDR defines **network vs host bits**
- Helps divide networks efficiently  

Example:
    192.168.1.0/24  

---

### 📐 You Can Now Identify:
- Network address  
- Broadcast address  
- Usable host range  

---

### ⚡ Key CIDR Memory Table

| CIDR | Total IPs | Usable |
|------|----------|--------|
| /30  | 4        | 2      |
| /29  | 8        | 6      |
| /28  | 16       | 14     |
| /27  | 32       | 30     |
| /26  | 64       | 62     |
| /25  | 128      | 126    |
| /24  | 256      | 254    |

---

### 🧠 Outcome
- Faster subnet calculations  
- Ability to solve subnetting problems confidently  

---

## 🌐 3. IPv6 Basics (Future of Networking)

### 📌 Key Learnings
- IPv6 = **128-bit address**
- Written in hexadecimal  

Example:
    2001:db8::1  

---

### 📍 Address Types
- Global Unicast → internet routable  
- Link-local → local network  
- Loopback → ::1  

---

### ☁️ Importance
- Solves IPv4 exhaustion  
- Used in modern cloud environments (dual-stack)  

---

## 🌍 4. DNS (Domain Name System)

### 🔄 DNS Resolution Flow
1. Browser cache  
2. OS cache  
3. Resolver  
4. Root server  
5. TLD server  
6. Authoritative server  

---

### 📄 Record Types

| Record | Purpose |
|--------|--------|
| A      | Domain → IPv4 |
| AAAA   | Domain → IPv6 |
| CNAME  | Alias |
| MX     | Mail |
| TXT    | Verification |

---

### 🛠️ Commands Learned
    nslookup domain.com  
    dig domain.com  
    dig +trace domain.com  

---

### ⏱️ TTL
- Controls DNS caching duration  

---

## 🔁 5. DHCP (Automatic IP Assignment)

### 📌 What It Does
Assigns:
- IP address  
- Subnet mask  
- Gateway  
- DNS server  

---

### 🔄 DORA Process
1. Discover  
2. Offer  
3. Request  
4. Acknowledge  

---

## 🔄 6. NAT (Network Address Translation)

### 📌 Why It Exists
- Allows private networks to access the internet  

---

### 📊 Types

| Type        | Description |
|------------|------------|
| Static NAT | 1:1 |
| Dynamic NAT| Many:many |
| PAT        | Many:1 (most common) |

---

## 🛠️ 7. Troubleshooting Commands

### 🔍 Connectivity
    ping google.com  

---

### 🧭 Path Analysis
    traceroute google.com  

---

### 🌐 DNS Debugging
    dig google.com  

---

### 🔌 Ports & Services
    ss -tulpn  
    netstat -tulpn  

---

### 🌍 HTTP Testing
    curl -v https://example.com  

---

### 🧾 IP & Network Info
    ip addr show  
    ipcalc 10.0.0.0/16  

---

## 🌐 8. End-to-End Network Flow

### 🧠 You Now Understand:

1. Device gets IP via DHCP  
2. User enters domain (google.com)  
3. DNS resolves domain → IP  
4. Request goes through router  
5. NAT converts private IP → public IP  
6. Request reaches server  
7. Server responds back  

---

## 🔗 9. Cloud Connection

- VPC = isolated network  
- Subnets = segmented networks  
- Route tables = traffic control  
- NAT Gateway = internet access for private subnet  
- Route 53 = DNS service  

---

## 🧠 Final Mindset Upgrade

Moved from:

> “Networking is confusing”  

To:

> “I understand how the internet actually works”  

---

## 🚀 What You Can Do Now

- Solve subnetting problems quickly  
- Debug DNS issues using real tools  
- Explain NAT, DHCP, and DNS clearly  
- Understand how cloud networking works  

---

## 📈 What’s Next

👉 Week 6 will build on this foundation and move deeper into:
- Linux networking  
- Cloud networking (VPC, subnets, routing)  
- Real infrastructure design  

---

## ✅ Week 5 Complete

You’ve built one of the **most important foundations in cloud engineering**.

**Progress:** 5 Weeks Down 🔥  
**Momentum:** Strong 🚀  