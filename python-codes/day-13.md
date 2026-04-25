# Day 055 – Python Practice Code

**Date:** 25 April 2026  
**Day in Python Journey:** Day 13  

---

## 🎯 Objective

Practice Python Object-Oriented Programming (OOP) fundamentals by creating classes, using inheritance, and applying methods for cloud-related use cases.

---

## 🧾 ec2_manager.py

    class EC2Manager:
        def __init__(self, region):
            self.region = region

        def list_instances(self):
            print(f"Listing instances in {self.region}")

        def __str__(self):
            return f"EC2Manager in {self.region}"

        def __repr__(self):
            return f"EC2Manager(region='{self.region}')"

    ec2 = EC2Manager("ap-south-1")
    print(ec2)
    print(repr(ec2))
    ec2.list_instances()

---

## 🧾 inheritance_example.py

    class EC2Manager:
        def __init__(self, region):
            self.region = region

        def list_instances(self):
            print("Listing all instances")

    class DevEC2Manager(EC2Manager):
        def list_instances(self):
            print("Listing DEV instances only")

    dev_ec2 = DevEC2Manager("ap-south-1")
    dev_ec2.list_instances()

---

## 🧾 methods_example.py

    class EC2Manager:
        def __init__(self, region):
            self.region = region

        @staticmethod
        def validate_region(region):
            return region.startswith("ap-")

        @classmethod
        def default_region(cls):
            return cls("ap-south-1")

    print(EC2Manager.validate_region("ap-south-1"))

    default_ec2 = EC2Manager.default_region()
    print(default_ec2.region)

---

## 🧾 cloud_resource.py

    class CloudResource:
        def __init__(self, name, region):
            self.name = name
            self.region = region

        def create(self):
            raise NotImplementedError

        def delete(self):
            raise NotImplementedError

        def status(self):
            raise NotImplementedError


    class EC2Instance(CloudResource):
        def create(self):
            print(f"Creating EC2 instance: {self.name}")

        def delete(self):
            print(f"Deleting EC2 instance: {self.name}")

        def status(self):
            print(f"Checking EC2 status: {self.name}")


    class S3Bucket(CloudResource):
        def create(self):
            print(f"Creating S3 bucket: {self.name}")

        def delete(self):
            print(f"Deleting S3 bucket: {self.name}")

        def status(self):
            print(f"Checking S3 bucket status: {self.name}")


    ec2 = EC2Instance("my-ec2", "ap-south-1")
    s3 = S3Bucket("my-bucket", "ap-south-1")

    ec2.create()
    ec2.status()
    s3.create()
    s3.status()

---

## 🧠 Concepts Practiced

- Classes and Objects  
- Constructors (`__init__`)  
- Instance Methods  
- Inheritance  
- Method Overriding  
- Static Methods (`@staticmethod`)  
- Class Methods (`@classmethod`)  
- Special Methods (`__str__`, `__repr__`)  
- Code Reusability using OOP  

---

## ▶️ Commands Used

    python3 ec2_manager.py
    python3 inheritance_example.py
    python3 methods_example.py
    python3 cloud_resource.py

---

## 💭 Reflection

Learned how to structure Python code using OOP principles.  
Understood how to model cloud resources like EC2 and S3 as classes.  
Gained confidence in writing scalable and reusable automation scripts.

---

**Status:** Day 13 of Python Complete ✅  