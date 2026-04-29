# WEEK 8 – PYTHON FOR CLOUD II: APIs, boto3 & OOP BASICS

**Focus:** REST APIs, AWS automation with boto3, OOP fundamentals, error handling, and testing  
**Goal:** Build real-world cloud automation skills used daily by cloud engineers  

---

## 🎯 Weekly Objective

Develop the ability to:
- Handle errors gracefully in production scripts  
- Work with REST APIs using Python  
- Automate AWS services using boto3  
- Structure code using Object-Oriented Programming  
- Write testable and maintainable cloud automation scripts  

---

## 📘 Day 50 – Error Handling with try/except

### 🔑 Key Concepts

Basic structure:
    try:
        risky_code()
    except ValueError as e:
        print(e)
    finally:
        cleanup()

Common Exceptions:
- FileNotFoundError  
- KeyError  
- ValueError  
- TypeError  
- ConnectionError  

Raising Exceptions:
    raise ValueError(f"Invalid region: {region}")

Best Practices:
- Catch specific exceptions before general ones  
- Always include meaningful error messages  

### 🧠 What You Learned
- Writing robust scripts that don’t crash  
- Handling real-world failure scenarios  
- Improving debugging and reliability  

---

## 🌐 Day 51 – REST APIs with requests

### 🔑 Key Concepts

Install:
    pip install requests

GET Request:
    response = requests.get(url, params={}, headers={})
    data = response.json()

POST Request:
    requests.post(url, json={"key": "value"}, headers={"Authorization": "Bearer token"})

Sessions:
    session = requests.Session()

Timeout:
    requests.get(url, timeout=5)

### 🧠 What You Learned
- Calling external APIs  
- Parsing JSON responses  
- Handling API reliability (timeouts, sessions)  

---

## ☁️ Day 52 – boto3 Basics (AWS SDK)

### 🔑 Key Concepts

Install:
    pip install boto3

Clients vs Resources:
- Client → low-level API  
- Resource → high-level abstraction  

S3 Operations:
    s3 = boto3.client('s3')
    s3.list_buckets()

Create Bucket:
    s3.create_bucket(Bucket='unique-name')

Upload/Download:
    s3.upload_file('local.txt', 'bucket', 'remote.txt')

### 🧠 What You Learned
- AWS automation fundamentals  
- Working with S3 programmatically  

---

## ⚡ Day 53 – EC2 Automation

### 🔑 Key Concepts

List Instances:
    ec2.describe_instances()

Filtering:
    Filters=[{'Name': 'instance-state-name', 'Values': ['running']}]

Extract Data:
- Instance ID  
- Type  
- State  
- Private/Public IP  
- Tags  

Start/Stop:
    ec2.start_instances(InstanceIds=['id'])
    ec2.stop_instances(InstanceIds=['id'])

### 🧠 What You Learned
- Navigating nested AWS responses  
- Automating EC2 lifecycle  
- Multi-region scripting  

---

## 🔐 Day 54 – IAM & CloudWatch

### 🔑 Key Concepts

IAM:
    iam.list_users()
    iam.list_roles()

CloudWatch Metrics:
    cw.get_metric_statistics()

Logs:
    logs.describe_log_groups()

Pagination:
    paginator = client.get_paginator('operation')

### 🧠 What You Learned
- Monitoring and security auditing  
- Handling large datasets with pagination  
- Real-world cloud visibility  

---

## 🧱 Day 55 – Python OOP Basics

### 🔑 Key Concepts

Classes:
    class EC2Manager:
        def __init__(self, region):
            self.region = region

Inheritance:
    class DevEC2Manager(EC2Manager):
        pass

Special Methods:
- __init__ → constructor  
- __str__ → readable output  
- __repr__ → debug output  

Decorators:
- @staticmethod  
- @classmethod  

### 🧠 What You Learned
- Structuring large applications  
- Writing reusable cloud components  
- Cleaner, modular design  

---

## 🧪 Day 56 – Virtual Environments & Testing

### 🔑 Key Concepts

Virtual Environments:
    python3 -m venv venv
    source venv/bin/activate

Requirements:
    pip freeze > requirements.txt
    pip install -r requirements.txt

Pytest:
    pip install pytest
    pytest

Basic Test:
    def test_example():
        assert func() == expected

Mocking:
    from unittest.mock import patch

### 🧠 What You Learned
- Isolated development environments  
- Writing testable code  
- Mocking AWS calls safely  

---

## 🧠 Key Concepts of the Week

- Error handling in production scripts  
- REST API integration  
- AWS automation using boto3  
- Object-Oriented Programming basics  
- Testing and debugging workflows  
- Writing scalable and maintainable cloud tools  

---

## 🔄 Mindset Shift

Moved from:

> Writing simple scripts  

To:

> Building production-ready cloud automation systems  

---

## 💭 Weekly Reflection

Week 8 was a major leap into real cloud engineering work.

Built:
- Strong API handling skills  
- Practical AWS automation experience  
- Ability to structure applications using OOP  
- Understanding of testing and reliability  

This week marks the transition from:
Learning Python → Using Python as a cloud engineering tool  

---

**Status:** Week 8 Complete ✅  
**Progress:** 56 / 1000 Days 🚀  