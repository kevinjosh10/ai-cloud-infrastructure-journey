# Day 047 – Python Practice Code

**Date:** 17 April 2026  
**Day in Python Journey:** Day 5  

---

## 🎯 Objective

Practice loops and conditionals in Python by writing scripts that simulate real-world cloud automation tasks like iterating over resources and filtering data.

---

## 🧾 loop_servers.py

    servers = ["web-1", "web-2", "db-1"]

    for server in servers:
        print("Checking server:", server)

---

## 🧾 enumerate_servers.py

    servers = ["web-1", "web-2", "db-1"]

    for i, server in enumerate(servers):
        print("Index:", i, "| Server:", server)

---

## 🧾 retry_logic.py

    retries = 0

    while retries < 3:
        print("Attempt", retries + 1)
        retries += 1

---

## 🧾 condition_check.py

    state = "running"

    if state == "running":
        print("Server is active")
    elif state == "stopped":
        print("Server is stopped")
    else:
        print("Unknown state")

---

## 🧾 ec2_filter.py

    instances = [
        {"id": "i-001", "state": "running", "region": "us-east-1"},
        {"id": "i-002", "state": "stopped", "region": "us-east-1"},
        {"id": "i-003", "state": "running", "region": "us-west-2"},
        {"id": "i-004", "state": "running", "region": "us-east-1"},
    ]

    print("Running instances in us-east-1:\n")

    for instance in instances:
        if instance["state"] == "running" and instance["region"] == "us-east-1":
            print("Instance ID:", instance["id"])

---

## 🧠 Concepts Practiced

- `for` loops (iteration over lists)  
- `enumerate()` for index tracking  
- `while` loops for retry logic  
- Conditional statements (`if`, `elif`, `else`)  
- Logical operators (`and`)  
- Working with lists of dictionaries  
- Filtering data based on conditions  

---

## ▶️ Commands Used

    python3 loop_servers.py
    python3 enumerate_servers.py
    python3 retry_logic.py
    python3 condition_check.py
    python3 ec2_filter.py

---

## 💭 Reflection

Learned how to control the flow of programs using loops and conditions.  
Understood how real-world cloud scripts iterate through resources and apply logic.  
Built the foundation for automation tasks like filtering EC2 instances and retrying operations.

---

**Status:** Day 5 of Python Complete ✅  
