# Week 06 – Networking Fundamentals II Roadmap

**Focus:** HTTP/HTTPS, SSL/TLS, Ports, Firewalls, Load Balancers, VPNs & Troubleshooting  

---

## 🎯 Objective

Follow a structured path to master advanced networking concepts used in real-world cloud environments.  
Build both theoretical understanding and hands-on troubleshooting skills.  

---

## 🗺️ Weekly Breakdown

### 📅 Day 36 – HTTP & HTTPS Deep Dive
- Learn HTTP request structure:
    Method, URL, Headers, Body  

- Learn HTTP response structure:
    Status Code, Headers, Body  

- Memorize key status codes:
    200, 201, 301, 302, 400, 401, 403, 404, 500, 502, 503  

- Understand stateless nature of HTTP  
- Learn cookies, sessions, tokens  

- Practice:
    curl https://httpbin.org/get  
    curl https://httpbin.org/headers  

---

### 📅 Day 37 – SSL/TLS & Certificates
- Understand TLS handshake:
    ClientHello → ServerHello → Certificate → Key Exchange → Secure Connection  

- Learn:
    Certificate Authority (CA)  
    Self-signed vs CA-signed certificates  

- Study certificate components:
    Domain, Issuer, Expiry, Public Key, Signature  

- Understand HTTPS (Port 443)  
- Learn TLS 1.2 vs TLS 1.3  

- Practice:
    openssl s_client -connect google.com:443  

---

### 📅 Day 38 – Ports & Protocols
- Memorize critical ports:
    22, 80, 443, 21, 25, 53, 3306, 5432, 6379, 27017  

- Learn additional ports:
    8080, 8443, 9090, 3000, 9200  

- Understand TCP vs UDP  

- Practice:
    sudo nmap -sV -p 1-1000 localhost  
    ss -tulpn  

---

### 📅 Day 39 – Firewalls & Security Groups
- Understand firewall concepts:
    Stateful vs Stateless  

- Learn:
    Ingress vs Egress rules  

- Practice iptables:
    sudo iptables -L  

- Configure UFW:
    sudo ufw enable  
    sudo ufw allow 22  
    sudo ufw allow 80  

- Apply in AWS:
    Modify Security Groups to allow HTTP access  

---

### 📅 Day 40 – Load Balancers & VPNs
- Understand load balancer concepts  
- Learn algorithms:
    Round Robin  
    Least Connections  
    IP Hash  
    Weighted Round Robin  

- Learn types:
    Layer 4 vs Layer 7  

- Map to AWS:
    ALB vs NLB  

- Understand VPN:
    Site-to-Site VPN  
    Client VPN  

- Learn AWS networking:
    VPN Gateway, Direct Connect  

---

### 📅 Day 41 – Advanced Network Troubleshooting
- Follow troubleshooting flow:
    1. DNS issue  
    2. Routing issue  
    3. Firewall issue  
    4. Application issue  

- Practice tools:
    dig +short example.com  
    telnet host port  
    sudo tcpdump -i eth0 port 80  
    mtr google.com  

- Simulate:
    Web app downtime scenario  

---

### 📅 Day 42 – Review & Foundation Check
- Review all networking concepts (Weeks 1–6)  
- Self-assessment:
    Subnetting /24 → /27  
    TLS handshake explanation  
    DNS troubleshooting  

- Hands-on:
    Deploy NGINX on EC2  
    Serve static HTML page  

- Update GitHub:
    Notes, scripts, projects  

- Prepare for next phase:
    Install Python 3  
    Start automation learning  

---

## 🧠 Learning Strategy

- Learn → Practice → Break → Debug → Repeat  
- Focus on understanding, not memorization  
- Use CLI tools daily  
- Simulate real-world failures  

---

## 📈 Progress Milestones

By end of Week 6, you should:

- Understand HTTP/HTTPS deeply  
- Explain TLS handshake confidently  
- Identify ports and protocols instantly  
- Configure firewalls and security groups  
- Understand load balancing concepts  
- Troubleshoot network issues step-by-step  
- Deploy and access a web server on cloud  

---

## 🔄 Mindset Shift

Moved from:

> Basic networking understanding  

To:

> Thinking like a cloud/network engineer solving real-world problems  

---

## 💭 Reflection

Week 6 is where networking becomes practical.

You are no longer just learning concepts —  
you are:
- Testing APIs  
- Debugging failures  
- Deploying services  
- Securing communication  

---

**Status:** Roadmap Defined  
**Outcome:** Ready to Execute Week 6 with Clarity 🚀  