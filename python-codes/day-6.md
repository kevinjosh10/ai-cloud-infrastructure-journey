# Day 048 – Python Practice Code

**Date:** 18 April 2026  
**Day in Python Journey:** Day 6  

---

## 🎯 Objective

Practice writing Python functions, using return values, and organizing code with modules.  
Build reusable helper functions similar to real-world cloud automation scripts.

---

## 🧾 functions_basic.py

    def greet_user(name):
        print(f"Hello {name}, welcome back!")

    def add_numbers(a, b):
        return a + b

    greet_user("Kevin")
    result = add_numbers(10, 5)
    print("Sum:", result)

---

## 🧾 multiple_return.py

    def get_instance_info():
        status = "running"
        ip_address = "192.168.1.10"
        return status, ip_address

    status, ip = get_instance_info()

    print("Status:", status)
    print("IP Address:", ip)

---

## 🧾 flexible_args.py

    def print_services(*services):
        for service in services:
            print(service)

    def create_instance(**details):
        for key, value in details.items():
            print(f"{key}: {value}")

    print_services("EC2", "S3", "Lambda")

    create_instance(instance_type="t2.micro", region="ap-south-1")

---

## 🧾 aws_helpers.py

    import datetime

    def format_instance_id(instance_id):
        return instance_id.strip().lower()

    def get_region_from_az(availability_zone):
        return availability_zone[:-1]

    def calculate_runtime_hours(start_time):
        now = datetime.datetime.now()
        runtime = now - start_time
        return round(runtime.total_seconds() / 3600, 2)

---

## 🧾 main.py

    import datetime
    import aws_helpers

    instance_id = " I-ABC123 "
    formatted_id = aws_helpers.format_instance_id(instance_id)

    region = aws_helpers.get_region_from_az("ap-south-1a")

    start_time = datetime.datetime(2026, 4, 18, 10, 0, 0)
    runtime = aws_helpers.calculate_runtime_hours(start_time)

    print("Instance ID:", formatted_id)
    print("Region:", region)
    print("Runtime (hours):", runtime)

---

## 🧠 Concepts Practiced

- Function Definition (`def`)  
- Return Values (single & multiple)  
- `*args` and `**kwargs`  
- Code Reusability  
- Python Modules (`import`)  
- Working with `datetime`  

---

## ▶️ Commands Used

    python3 functions_basic.py
    python3 multiple_return.py
    python3 flexible_args.py
    python3 main.py

---

## 💭 Reflection

Learned how to write reusable functions and organize code into modules.  
Understood how real-world scripts are structured for scalability.  
Built first helper module similar to cloud automation tools.

---

**Status:** Day 6 of Python Complete ✅  