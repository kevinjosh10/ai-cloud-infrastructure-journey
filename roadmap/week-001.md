# 🚀 Week 01 Roadmap — Orientation & Setup

**Journey:** 1000 Days to Become an AI Cloud Infrastructure Engineer  
**Week Focus:** Cloud Foundations, Development Environment Setup, and Networking Basics

---

# 🎯 Week Objective

The goal of Week 1 is to establish a **strong technical foundation** for cloud engineering by:

- Reviewing AWS fundamentals
- Setting up a professional development environment
- Learning Git and GitHub workflows
- Understanding networking basics
- Practicing AWS CLI operations
- Preparing for Linux system administration

These skills form the **core base of modern cloud infrastructure engineering**.

---

# 🧰 Resources Used

📚 **Learning Platforms**

- AWS Skill Builder → https://skill.aws.amazon.com  
- GitHub Documentation → https://docs.github.com  
- Linux Journey → https://linuxjourney.com  

🎥 **Video Learning**

- NetworkChuck YouTube Channel

💻 **Development Tools**

- VS Code
- Git
- AWS CLI
- Python

---

# 📅 Week 1 Learning Plan

---

# 📘 Day 1 — AWS Review & Environment Setup ☁️

### Goals

- Refresh AWS foundational knowledge
- Configure the development environment

### Tasks

1️⃣ Review **AWS Cloud Practitioner notes** (45 minutes)

Focus services:

- EC2
- S3
- IAM
- VPC

2️⃣ Install **VS Code** and configure extensions:

- AWS Toolkit
- Python
- GitLens
- YAML
- Docker

3️⃣ Install **AWS CLI v2**

Run:

```
aws configure
```

Enter:

- Access Key
- Secret Access Key
- Default region
- Output format

4️⃣ Create an **AWS Free Tier Account** (if not already created)

Enable:

🔐 **Multi-Factor Authentication (MFA)** on the root account.

5️⃣ Document installed tools in **Notion or Obsidian**.

---

# 📘 Day 2 — Git & GitHub Setup 🧑‍💻

### Goals

Understand **version control and Git workflows**.

### Tasks

1️⃣ Install Git locally.

Configure identity:

```
git config --global user.name "Your Name"
git config --global user.email "youremail@example.com"
```

2️⃣ Create a **GitHub account** with a professional username.

3️⃣ Create your first repository:

```
ai-cloud-infrastructure-journey
```

4️⃣ Push a **README.md** explaining:

- Your learning goals
- The 1000-day roadmap

5️⃣ Practice the basic Git workflow **5 times**:

```
git init
git add .
git commit -m "message"
git push
```

---

# 📘 Day 3 — OSI Model (Layers 1–4) 🌐

### Goals

Understand **network communication fundamentals**.

### Topics

**Layer 1 — Physical**

- Electrical signals
- Network cables
- Bits transmission

**Layer 2 — Data Link**

- MAC addresses
- Switches
- Frames

**Layer 3 — Network**

- IP addressing
- Packet routing
- Internet communication

**Layer 4 — Transport**

Protocols:

- TCP
- UDP

Understand the **TCP 3-way handshake**:

1. SYN  
2. SYN-ACK  
3. ACK  

🎥 Watch NetworkChuck’s **OSI Model video (~20 minutes)**.

✍ Write a **one-paragraph summary of each layer**.

---

# 📘 Day 4 — OSI Layers 5–7 & TCP/IP Model 🌍

### Goals

Understand **higher-level communication protocols**.

### OSI Layers

**Layer 5 — Session**

Manages active connections between systems.

**Layer 6 — Presentation**

Handles:

- Encryption
- Compression
- Data formatting

**Layer 7 — Application**

Protocols used by applications:

- HTTP
- HTTPS
- FTP
- DNS
- SMTP

---

### TCP/IP Model

The **practical networking model used by the internet**.

| TCP/IP Layer | Corresponding OSI Layers |
|--------------|-------------------------|
| Application | OSI Layers 5–7 |
| Transport | OSI Layer 4 |
| Internet | OSI Layer 3 |
| Network Access | OSI Layers 1–2 |

---

### IP Addressing Basics

IPv4 format:

```
x.x.x.x
```

Example:

```
192.168.1.1
```

Private ranges:

- 192.168.x.x
- 10.x.x.x
- 172.16–31.x.x

---

### Network Testing Commands

Ping a server:

```
ping google.com
```

Trace network route:

Mac/Linux:

```
traceroute google.com
```

Windows:

```
tracert google.com
```

---

# 📘 Day 5 — AWS CLI Deep Dive ⚡

### Goals

Learn to manage AWS resources through the **command line**.

### Practice Commands

List S3 buckets:

```
aws s3 ls
```

List EC2 instances:

```
aws ec2 describe-instances
```

Create S3 bucket:

```
aws s3 mb s3://my-test-bucket
```

Upload file:

```
aws s3 cp file.txt s3://my-test-bucket
```

Delete file:

```
aws s3 rm s3://my-test-bucket/file.txt
```

---

### AWS CLI Profiles

Create a profile:

```
aws configure --profile dev
```

Use the profile:

```
aws s3 ls --profile dev
```

---

### Output Formatting

JSON format:

```
aws ec2 describe-instances --output json
```

Table format:

```
aws ec2 describe-instances --output table
```

Query filtering:

```
aws ec2 describe-instances --query 'Reservations[*].Instances[*].InstanceId'
```

---

# 📘 Day 6 — Developer Environment & AWS Console ⚙️

### Goals

Prepare the development environment for cloud projects.

### Tasks

Install **Python 3**.

Create a virtual environment:

```
python3 -m venv myenv
```

Activate environment (Linux/Mac):

```
source myenv/bin/activate
```

Install required packages:

```
pip install boto3 requests pyyaml
```

---

### AWS Console Exploration

Explore these services:

- EC2
- S3
- IAM
- VPC
- CloudWatch

---

### EC2 Practice

Launch a **t2.micro instance**.

Then **terminate it immediately** to avoid charges.

---

### Update GitHub README

Document what you learned during Week 1.

---

# 📘 Day 7 — Week Review & Practice 🧠

### Goals

Reinforce everything learned this week.

### Review Topics

- OSI Model
- TCP/IP Model
- Git workflow
- AWS CLI commands

---

### Self Quiz

Ask yourself:

- Can I explain all **7 OSI layers**?
- Can I run **AWS CLI commands from memory**?

---

### Watch AWS re:Invent Talk

Search:

```
AWS re:Invent Getting Started
```

Learn about **cloud fundamentals and AWS architecture**.

---

### Create Anki Flashcards

Minimum **20 flashcards** covering:

- OSI layers
- TCP vs UDP
- Private IP ranges
- AWS CLI commands

---

### Prepare for Week 2

Read the **Linux Journey introduction**.

Website:

```
https://linuxjourney.com
```

---

# 📊 Week 1 Outcome

By the end of this week, you should understand:

✔ AWS core services  
✔ Git and GitHub workflows  
✔ Networking fundamentals  
✔ AWS CLI usage  
✔ Development environment setup

These are the **foundational building blocks for cloud infrastructure engineering**.

---

# 🔜 Next Week Preview

**Week 2 Focus: Linux Fundamentals**

Topics include:

- Linux filesystem
- Shell commands
- Permissions
- Processes
- Networking tools

Linux mastery is essential because **most cloud servers run Linux-based systems**.

---

# 🔑 Consistency builds expertise.

One week down.  
**999 days to go.** 🚀