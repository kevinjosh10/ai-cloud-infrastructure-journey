# Week 06 – Networking Fundamentals II

**Focus:** VPNs, Firewalls, Load Balancers, HTTP/HTTPS, SSL/TLS, Ports, Protocols & Advanced Troubleshooting  

---

## 🎯 Objective

Build a strong understanding of real-world networking used in cloud environments.  
Learn how web communication works, how systems are secured, and how to troubleshoot issues like an engineer.  

---

## 🌐 1️⃣ HTTP & HTTPS Deep Dive

### 🔹 HTTP Request Structure
- **Method:** GET, POST, PUT, DELETE, PATCH  
- **URL:** Endpoint being accessed  
- **Headers:** Metadata (Content-Type, Authorization)  
- **Body:** Data sent (mainly in POST/PUT)  

Example:
    curl -X POST -H "Content-Type: application/json" -d '{"key":"value"}' https://httpbin.org/post  

---

### 🔹 HTTP Response Structure
- **Status Code:** Result of request  
- **Headers:** Metadata  
- **Body:** Response content  

#### Common Status Codes
- 200 → OK  
- 201 → Created  
- 301 → Moved Permanently  
- 302 → Redirect  
- 400 → Bad Request  
- 401 → Unauthorized  
- 403 → Forbidden  
- 404 → Not Found  
- 500 → Internal Server Error  
- 502 → Bad Gateway  
- 503 → Service Unavailable  

---

### 🔹 Stateless Nature of HTTP
- Each request is independent  
- No memory of previous requests  

#### Solution:
- Cookies  
- Sessions  
- Tokens  

---

### 🔹 Practice Commands
    curl https://httpbin.org/get  
    curl https://httpbin.org/headers  

---

## 🔐 2️⃣ SSL/TLS & Certificates

### 🔹 TLS Handshake Process
1. ClientHello  
2. ServerHello  
3. Certificate Exchange  
4. Key Exchange  
5. Secure Connection Established  

---

### 🔹 Certificates
- Issued by Certificate Authorities (CA)  
- Used to verify identity of server  

#### Types:
- CA-signed certificate  
- Self-signed certificate  

---

### 🔹 Certificate Components
- Domain name  
- Issuer (CA)  
- Expiry date  
- Public key  
- Digital signature  

---

### 🔹 HTTPS
- HTTP + TLS encryption  
- Uses Port 443  

#### Why HTTPS?
- Encrypts data in transit  
- Prevents man-in-the-middle attacks  

---

### 🔹 TLS Versions
- TLS 1.2 → widely used  
- TLS 1.3 → faster & more secure  

---

### 🔹 Practice
    openssl s_client -connect google.com:443  

---

## 🔌 3️⃣ Common Ports & Protocols

### 🔹 Important Ports
- 22 → SSH  
- 80 → HTTP  
- 443 → HTTPS  
- 21 → FTP  
- 25 → SMTP  
- 53 → DNS  
- 3306 → MySQL  
- 5432 → PostgreSQL  
- 6379 → Redis  
- 27017 → MongoDB  

---

### 🔹 Additional Ports
- 8080 → HTTP (alt)  
- 8443 → HTTPS (alt)  
- 9090 → Prometheus  
- 3000 → Grafana  
- 9200 → Elasticsearch  

---

### 🔹 TCP vs UDP
- TCP → Reliable, connection-based (SSH, HTTP, HTTPS)  
- UDP → Fast, connectionless (DNS default)  

---

### 🔹 Practice Commands
    sudo nmap -sV -p 1-1000 localhost  
    ss -tulpn  

---

## 🔥 4️⃣ Firewalls & Security Groups

### 🔹 Firewall Basics
- Controls network traffic  
- Types:
    Stateful → Tracks connections  
    Stateless → No memory  

---

### 🔹 Rules
- Ingress → Incoming traffic  
- Egress → Outgoing traffic  

---

### 🔹 iptables Basics
    sudo iptables -L  

- Chains:
    INPUT → Incoming  
    OUTPUT → Outgoing  
    FORWARD → Routing  

---

### 🔹 UFW (Uncomplicated Firewall)
    sudo ufw enable  
    sudo ufw allow 22  
    sudo ufw allow 80  

---

### 🔹 AWS Security Groups
- Acts as a stateful firewall  
- If inbound allowed → response automatically allowed  

---

### 🔹 Practice
- Allow HTTP (port 80) in EC2 Security Group  
- Verify nginx is accessible via browser  

---

## ⚖️ 5️⃣ Load Balancers & VPNs

### 🔹 Load Balancer
- Distributes traffic across multiple servers  
- Improves availability and scalability  

---

### 🔹 Algorithms
- Round Robin  
- Least Connections  
- IP Hash  
- Weighted Round Robin  

---

### 🔹 Types
- Layer 4 → TCP/UDP  
- Layer 7 → HTTP/HTTPS  

---

### 🔹 AWS Mapping
- ALB → Layer 7  
- NLB → Layer 4  

---

### 🔹 VPN (Virtual Private Network)
- Encrypts traffic between networks over the internet  

---

### 🔹 Types of VPN
- Site-to-Site VPN  
- Client VPN  

---

### 🔹 AWS Networking
- VPN Gateway  
- Direct Connect  

---

## 🛠️ 6️⃣ Advanced Network Troubleshooting

### 🔹 Methodology
1. Check DNS  
2. Check routing  
3. Check firewall  
4. Check application  

---

### 🔹 DNS Check
    dig +short example.com  

---

### 🔹 Port Connectivity
    telnet host port  

---

### 🔹 Packet Analysis
    sudo tcpdump -i eth0 port 80  

---

### 🔹 Network Path Analysis
    mtr google.com  

---

### 🔹 Scenario Practice
If web app is down:
- Check DNS resolution  
- Check Security Groups / firewall  
- Check Load Balancer health  
- Check server/service status  

---

## 🧠 Key Concepts Learned

- HTTP request/response lifecycle  
- TLS encryption and certificates  
- Critical ports and protocols  
- Firewall and security group behavior  
- Load balancing strategies  
- VPN fundamentals  
- Real-world troubleshooting workflow  

---

## 🔄 Mindset Shift

Moved from:

> Learning networking theory  

To:

> Thinking like a real-world cloud/network engineer diagnosing and fixing systems  

---

## 💭 Reflection

Week 6 focused on real-world networking and system behavior.

Built:
- Strong understanding of web communication  
- Clarity on security and encryption  
- Ability to identify and debug network issues  
- Confidence in handling production-level scenarios  

---

**Status:** Week 6 Complete  
**Progress:** Strong Foundation in Networking 🚀  