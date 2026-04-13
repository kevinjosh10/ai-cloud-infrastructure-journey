# Week 06 – Networking Fundamentals II Recap

**Date:** Week 6 Completion  
**Duration:** ~12–15 Hours (Total)  
**Focus:** HTTP/HTTPS, SSL/TLS, Ports, Firewalls, Load Balancers, VPNs & Troubleshooting  

---

## 🎯 Objective

Consolidate all networking concepts learned in Week 6.  
Strengthen understanding of real-world communication, security, and debugging in cloud environments.  

---

## ✅ What I Covered

### 1️⃣ HTTP & HTTPS
- Learned HTTP request structure:
    Method, URL, Headers, Body  

- Learned HTTP response structure:
    Status Code, Headers, Body  

- Memorized key status codes:
    200, 201, 301, 302, 400, 401, 403, 404, 500, 502, 503  

- Understood stateless nature of HTTP  
- Learned how cookies, sessions, and tokens maintain state  

---

### 2️⃣ SSL/TLS & Certificates
- Understood TLS handshake:
    ClientHello → ServerHello → Certificate → Key Exchange → Secure Connection  

- Learned about Certificate Authorities (CA)  
- Differentiated:
    CA-signed vs Self-signed certificates  

- Explored certificate components:
    Domain, Issuer, Expiry, Public Key, Signature  

- Understood HTTPS = HTTP + TLS (Port 443)  
- Learned TLS 1.2 vs TLS 1.3  

---

### 3️⃣ Ports & Protocols
- Memorized critical ports:
    22 (SSH), 80 (HTTP), 443 (HTTPS), 53 (DNS)  

- Learned database & system ports:
    3306 (MySQL), 5432 (PostgreSQL), 6379 (Redis), 27017 (MongoDB)  

- Learned additional ports:
    8080, 8443, 9090, 3000, 9200  

- Understood TCP vs UDP:
    TCP → Reliable  
    UDP → Fast  

---

### 4️⃣ Firewalls & Security Groups
- Learned firewall types:
    Stateful vs Stateless  

- Understood:
    Ingress (inbound)  
    Egress (outbound)  

- Practiced:
    iptables basics  
    UFW configuration  

- Learned AWS Security Groups:
    Stateful firewall controlling instance traffic  

---

### 5️⃣ Load Balancers & VPNs
- Understood load balancing:
    Distributes traffic across servers  

- Learned algorithms:
    Round Robin  
    Least Connections  
    IP Hash  
    Weighted Round Robin  

- Learned types:
    Layer 4 (TCP/UDP)  
    Layer 7 (HTTP/HTTPS)  

- Mapped to AWS:
    ALB → Layer 7  
    NLB → Layer 4  

- Understood VPN:
    Secure communication over internet  

- Learned:
    Site-to-Site VPN  
    Client VPN  

---

### 6️⃣ Advanced Network Troubleshooting
- Followed structured approach:
    1. DNS issue  
    2. Routing issue  
    3. Firewall issue  
    4. Application issue  

- Practiced tools:
    dig → DNS lookup  
    telnet → Port check  
    tcpdump → Packet capture  
    mtr → Network path analysis  

- Simulated real-world failure scenarios  

---

### 7️⃣ Hands-On Learning
- Used curl to test APIs  
- Scanned ports using nmap  
- Checked services using ss  
- Captured packets using tcpdump  
- Deployed NGINX on EC2  
- Verified access via browser  

---

## 🧠 Key Concepts Learned

- Complete HTTP communication lifecycle  
- TLS encryption and certificate validation  
- Port-level understanding of services  
- Firewall rules and cloud security groups  
- Load balancing strategies and system design basics  
- Real-world troubleshooting methodology  

---

## 🔄 Mindset Shift

Moved from:

> Knowing networking concepts individually  

To:

> Understanding how systems communicate, secure, and fail in real-world cloud environments  

---

## 💭 Reflection

Week 6 was one of the most practical and critical phases.

Built:
- Strong understanding of web communication  
- Confidence in debugging network issues  
- Hands-on cloud deployment experience  
- Clarity on security and encryption  
- Readiness for automation and scripting  

---

## 🚀 Outcome

- Can explain HTTP/HTTPS clearly  
- Can describe TLS handshake confidently  
- Can identify ports and protocols quickly  
- Can troubleshoot network issues step-by-step  
- Can deploy and access a web server in cloud  

---

**Status:** Week 6 Complete  
**Progress:** Networking Fundamentals Strengthened 🚀  