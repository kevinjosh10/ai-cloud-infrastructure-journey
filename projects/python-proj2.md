# WEEK 8 – PROJECT: Cloud Multi-Tool CLI (APIs + boto3 + OOP)

**Date:** 29 April 2026  
**Duration:** ~4–6 Hours  
**Focus:** Build a production-style CLI tool integrating REST APIs, AWS boto3 automation, YAML config, OOP design, logging, and error handling  

---

## 🎯 Objective

Build a real-world **Cloud Multi-Tool CLI** that:
- Fetches data from external APIs (GitHub)  
- Automates AWS resources (S3 + EC2)  
- Uses YAML config for flexibility  
- Follows OOP design principles  
- Implements logging and error handling  
- Is testable and production-ready  

---

## 🧾 Project Overview

You will build:

    cloud_tool.py

A CLI tool with multiple commands:

    github → Fetch GitHub repos  
    s3 → List S3 buckets  
    ec2 → List EC2 instances  
    ec2-report → Multi-region EC2 report  

---

## 🏗️ Project Structure

    project/
    ├── cloud_tool.py
    ├── config.yaml
    ├── utils/
    │   ├── config_loader.py
    │   ├── logger.py
    │   └── helpers.py
    ├── services/
    │   ├── github_service.py
    │   ├── s3_service.py
    │   └── ec2_service.py
    ├── tests/
    │   └── test_ec2.py
    ├── requirements.txt
    └── README.md

---

## ⚙️ config.yaml

    aws:
      default_region: ap-south-1

    filters:
      instance_state: running

    output:
      format: table

    logging:
      level: INFO

    github:
      username: your_username

---

## 🧱 Core Features to Implement

### 1️⃣ YAML Config Integration
- Load config using `yaml.safe_load()`  
- Allow CLI args to override config values  

---

### 2️⃣ Logging System
- Use `logging` module  
- Log to console + file  
- Include levels: INFO, DEBUG, ERROR  

---

### 3️⃣ Error Handling
Handle:
- FileNotFoundError (config missing)  
- ConnectionError (API failure)  
- KeyError (bad JSON)  
- ValueError (invalid inputs)  

---

### 4️⃣ REST API Integration (GitHub)

Command:

    python cloud_tool.py github

Functionality:
- Call GitHub API:
      https://api.github.com/users/<username>/repos  
- Print:
      Repo Name | Language  

---

### 5️⃣ S3 Automation

Command:

    python cloud_tool.py s3 list

Functionality:
- List all S3 buckets  
- Print bucket names  

---

### 6️⃣ EC2 Automation

Command:

    python cloud_tool.py ec2 list --region ap-south-1

Functionality:
- List instances  
- Filter by state  
- Print:
      Instance ID | Type | State | IP  

---

### 7️⃣ Multi-Region EC2 Report

Command:

    python cloud_tool.py ec2-report

Functionality:
- Loop through all AWS regions  
- Collect all EC2 instances  
- Output table:

      Region | Instance ID | Type | State  

---

## 🧠 OOP Design

Create base class:

    class CloudResource:
        def create(self):
            pass

        def delete(self):
            pass

        def status(self):
            pass

Extend:

    class EC2Instance(CloudResource)
    class S3Bucket(CloudResource)

---

## 🧪 Testing Requirements

- Use pytest  
- Mock boto3 using unittest.mock  

Example:

    def test_format_instance():
        assert format_instance_id("i-ABC") == "i-abc"

---

## ▶️ Commands to Test

    python cloud_tool.py github
    python cloud_tool.py s3 list
    python cloud_tool.py ec2 list --region us-east-1
    python cloud_tool.py ec2-report

---

## 📦 requirements.txt

    boto3
    requests
    pyyaml
    pytest

---

## 🧠 Key Concepts Practiced

- REST API integration using requests  
- AWS automation using boto3  
- YAML-based configuration  
- CLI design using argparse  
- Object-Oriented Programming  
- Logging and error handling  
- Writing testable code  

---

## 🔄 Mindset Shift

Moved from:

> Writing small scripts  

To:

> Building modular, production-ready cloud tools  

---

## 💭 Reflection

This project simulates real cloud engineering work.

Built:
- Multi-service integration (API + AWS)  
- Clean project structure  
- Config-driven architecture  
- Scalable CLI design  

This is the foundation of tools used in:
- DevOps pipelines  
- Cloud automation platforms  
- Internal engineering tooling  

---

## 🚀 Bonus Challenges (Optional)

- Add support for multiple config files (dev/prod)  
- Export output as JSON or CSV  
- Add caching for API responses  
- Add colored CLI output  
- Deploy as a pip-installable package  

---

**Status:** Week 8 Project Complete ✅  
**Level:** Intermediate → Advancing 🚀  