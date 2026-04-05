# 📘 Week 5 – Networking Fundamentals I (Notes)

**Focus:** IP Addressing, Subnetting, CIDR, DNS, DHCP, NAT  
**Goal:** Build a strong networking foundation required for cloud engineering  

---

## 🌐 1. IPv4 Addressing Fundamentals

### 📌 Structure
- IPv4 = **32 bits**
- Divided into **4 octets (8 bits each)**
- Range per octet: **0–255**

Example:
    192.168.1.100

---

### 🔒 Private IP Ranges (RFC 1918)
- 10.0.0.0 – 10.255.255.255 (/8)
- 172.16.0.0 – 172.31.255.255 (/12)
- 192.168.0.0 – 192.168.255.255 (/16)

✔ Not routable on the internet  
✔ Used inside local networks  

---

### 🌍 Public vs Private IP
- **Public IP** → Accessible on the internet  
- **Private IP** → Used internally  
- **NAT** converts private → public  

---

### 🔁 Loopback Address
- 127.0.0.1 → localhost  
- Refers to your own machine  

---

## 📊 2. Subnetting & CIDR

### 📌 CIDR Notation
- Format: IP/Prefix

Example:
    /24 → 24 bits network, 8 bits host

---

### 📐 Subnet Calculation Example

Given:
    192.168.1.0/24

- Network Address: 192.168.1.0  
- Broadcast Address: 192.168.1.255  
- Usable Range: 192.168.1.1 – 192.168.1.254  
- Total IPs: 256  
- Usable IPs: 254  

---

### 📊 Common CIDR Blocks

| CIDR | Total IPs | Usable Hosts |
|------|----------|-------------|
| /32  | 1        | 1           |
| /31  | 2        | 2           |
| /30  | 4        | 2           |
| /29  | 8        | 6           |
| /28  | 16       | 14          |
| /27  | 32       | 30          |
| /26  | 64       | 62          |
| /25  | 128      | 126         |
| /24  | 256      | 254         |
| /16  | 65536    | 65534       |

---

### 🛠️ Tool
    ipcalc 10.0.0.0/16

---

## 🌐 3. IPv6 Basics

### 📌 Structure
- IPv6 = **128 bits**
- Written in **hexadecimal**
- 8 groups of 4 hex digits

Example:
    2001:0db8:85a3::8a2e:0370:7334

---

### ✂️ Abbreviation Rules
- Remove leading zeros
- Replace consecutive zeros with ::

---

### 📍 IPv6 Types
- Global Unicast → 2000::/3  
- Link-local → fe80::/10  
- Loopback → ::1  

---

### ☁️ Importance in Cloud
- Supports massive address space  
- Used in AWS, Azure, GCP (dual-stack)  

---

## 🌍 4. DNS (Domain Name System)

### 🔄 DNS Resolution Flow
1. Browser cache  
2. OS cache  
3. Resolver  
4. Root nameserver  
5. TLD nameserver  
6. Authoritative nameserver  

---

### 📄 DNS Record Types

| Record | Purpose |
|--------|--------|
| A      | Domain → IPv4 |
| AAAA   | Domain → IPv6 |
| CNAME  | Alias |
| MX     | Mail servers |
| TXT    | Verification |
| NS     | Nameservers |
| SOA    | Start of authority |

---

### 🛠️ Commands

    nslookup google.com  
    dig google.com  
    dig google.com MX  
    dig +trace google.com  

---

### ⏱️ TTL (Time to Live)
- Duration DNS records are cached  
- Lower TTL → faster updates  

---

## 🔁 5. DHCP (Dynamic Host Configuration Protocol)

### 📌 Purpose
Automatically assigns:
- IP address  
- Subnet mask  
- Default gateway  
- DNS servers  

---

### 🔄 DORA Process
1. Discover  
2. Offer  
3. Request  
4. Acknowledge  

---

## 🔄 6. NAT (Network Address Translation)

### 📌 Purpose
- Converts private IP → public IP  
- Enables internet access for private networks  

---

### 📊 NAT Types

| Type        | Description |
|------------|------------|
| Static NAT | 1:1 mapping |
| Dynamic NAT| Many:many |
| PAT        | Many:1 (most common) |

✔ Home routers use PAT  

---

## 🛠️ 7. Networking Commands

### 🔍 Connectivity
    ping google.com  

---

### 🧭 Path Tracing
    traceroute google.com  

---

### 🌐 DNS Queries
    nslookup google.com  
    dig google.com  

---

### 🔌 Ports & Services
    ss -tulpn  
    netstat -tulpn  

---

### 🌍 HTTP Requests
    curl -v https://example.com  

---

### 🧾 IP Info
    ip addr show  

---

### 📊 Subnet Calculation
    ipcalc 10.0.0.0/16  

---

## 🧠 8. Real-World Flow (How Internet Works)

1. Device gets IP via DHCP  
2. User enters domain (google.com)  
3. DNS resolves domain → IP  
4. Request goes through router  
5. NAT converts private IP → public IP  
6. Request reaches server  
7. Server responds back  

---

## 🔗 9. Cloud Connection (AWS Perspective)

- VPC uses private IP ranges  
- Subnets divide networks  
- Route tables control traffic  
- NAT Gateway allows private subnet internet access  
- Route 53 handles DNS  

---

## 🚀 Key Takeaways

- Subnetting is a **core skill** (must be fast)  
- DNS is the **phonebook of the internet**  
- NAT enables private networks to access the internet  
- DHCP automates network configuration  
- Networking commands are essential for debugging  

---

## ✅ End of Week 5

You now understand:
- How IP addressing works  
- How networks are divided  
- How domains resolve to IPs  
- How devices communicate over the internet  

👉 This is your **foundation for cloud networking (AWS VPC, Load Balancers, Security Groups)**  