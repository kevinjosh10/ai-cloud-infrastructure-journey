# Week 001 Recap — Orientation & Setup

## Overview

Week 1 focused on setting up the core tools and foundational knowledge required for the **AI Cloud Infrastructure Engineer journey**.

The goal of this week was to:

- Refresh AWS fundamentals
- Set up the development environment
- Learn Git and GitHub workflow
- Understand networking fundamentals (OSI & TCP/IP)
- Begin using AWS CLI
- Prepare the system for Linux and cloud development work

This week built the **foundation layer** for everything that follows in the roadmap.

---

# Key Topics Learned

## 1. AWS Foundations Review

Reviewed concepts from the **AWS Cloud Practitioner certification**.

Core AWS services revisited:

- EC2 (Elastic Compute Cloud)
- S3 (Simple Storage Service)
- IAM (Identity and Access Management)
- VPC (Virtual Private Cloud)

Key understanding reinforced:

- Cloud compute resources
- Object storage
- Identity and permissions
- Virtual networking in AWS

---

## 2. Development Environment Setup

Installed and configured the primary tools used for cloud engineering and infrastructure development.

Tools installed:

- **VS Code**
- **AWS CLI v2**
- **Git**
- **Python 3**
- **pip**
- **Virtual environments**

VS Code extensions configured:

- AWS Toolkit
- Python
- GitLens
- YAML
- Docker

These tools will be used throughout the entire 1000-day journey.

---

## 3. Git & GitHub Workflow

Set up version control and created the main learning repository.

Repository created:

```
ai-cloud-infrastructure-journey
```

Core Git commands practiced:

```
git init
git add
git commit
git push
```

Learned the basic Git workflow:

```
modify files → stage → commit → push
```

This repository will track all learning progress, notes, and projects.

---

## 4. Networking Fundamentals

Studied the **OSI model** and **TCP/IP model**, which are critical concepts for cloud infrastructure.

### OSI Model (7 Layers)

| Layer | Name |
|-----|-----|
| 1 | Physical |
| 2 | Data Link |
| 3 | Network |
| 4 | Transport |
| 5 | Session |
| 6 | Presentation |
| 7 | Application |

Key concepts learned:

- bits vs frames vs packets
- MAC addressing
- IP addressing
- TCP vs UDP communication

---

### TCP/IP Model (4 Layers)

| Layer | Function |
|-----|-----|
| Network Access | Physical + Data Link |
| Internet | IP routing |
| Transport | TCP / UDP |
| Application | HTTP, DNS, SMTP |

Understanding how the TCP/IP model maps to the OSI model is essential for troubleshooting networks and cloud systems.

---

## 5. IP Addressing Basics

Studied IPv4 structure and private IP ranges.

IPv4 format:

```
x.x.x.x
```

Private IP ranges:

```
10.0.0.0 – 10.255.255.255
172.16.0.0 – 172.31.255.255
192.168.0.0 – 192.168.255.255
```

Practiced basic networking commands:

```
ping google.com
traceroute google.com
```

These commands help observe how packets travel across networks.

---

## 6. AWS CLI Usage

Started using the **AWS Command Line Interface**.

Example commands practiced:

```
aws s3 ls
aws ec2 describe-instances
```

Additional skills learned:

- creating S3 buckets
- uploading files
- listing bucket contents
- deleting files
- filtering CLI outputs

Example output formats:

```
--output json
--output table
```

Profiles were also configured for environment separation.

```
aws configure --profile dev
```

---

## 7. Python Development Environment

Installed Python and created virtual environments.

Example setup:

```
python3 -m venv myenv
source myenv/bin/activate
```

Installed useful packages:

```
pip install boto3 requests pyyaml
```

These libraries are commonly used for:

- AWS automation
- API requests
- configuration management

---

## 8. AWS Console Exploration

Spent time exploring core AWS services through the AWS Console.

Services explored:

- EC2
- S3
- IAM
- VPC
- CloudWatch

Practical exercise completed:

- launched a free-tier **EC2 t2.micro instance**
- terminated the instance to avoid costs

This reinforced the basics of provisioning compute resources.

---

## 9. Learning System Setup

Established a system for retaining knowledge long term.

Methods used:

- written notes
- GitHub documentation
- Anki flashcards

Created flashcards for:

- OSI layers
- TCP vs UDP
- IP ranges
- AWS CLI commands

---

# Key Skills Developed

By the end of Week 1, the following skills were established:

- Basic AWS infrastructure understanding
- Git and GitHub workflow
- Networking fundamentals
- AWS CLI usage
- Python development environment setup
- Cloud console navigation
- Learning documentation practices

These form the **technical base layer** for cloud infrastructure engineering.

---

# Outcome of Week 1

Environment successfully prepared for the journey.

Completed:

- tool installation
- GitHub repository setup
- networking fundamentals study
- AWS CLI introduction
- development environment configuration

This week ensured the system and workflow were ready before diving into deeper technical topics.

---

# Progress

```
Week 1 Completed
Day 7 / 1000
```

The foundation for cloud infrastructure learning has been successfully established.

Next focus:

```
Week 2 → Linux Fundamentals
```

Mastering Linux is essential because most cloud infrastructure runs on Linux systems.

---