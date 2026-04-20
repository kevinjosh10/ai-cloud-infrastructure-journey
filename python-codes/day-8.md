# Day 050 – Python Practice Code

**Date:** 20 April 2026  
**Day in Python Journey:** Day 8  

---

## 🎯 Objective

Practice error handling in Python using try/except/finally.  
Learn how to handle invalid input, file errors, and build robust scripts.

---

## 🧾 safe_division.py

    try:
        num1 = int(input("Enter first number: "))
        num2 = int(input("Enter second number: "))

        result = num1 / num2
        print("Result:", result)

    except ValueError:
        print("Invalid input! Please enter numbers only.")

    except ZeroDivisionError:
        print("Cannot divide by zero!")

    finally:
        print("Execution completed.")

---

## 🧾 dictionary_access.py

    data = {"name": "Kevin", "role": "AI Engineer"}

    try:
        key = input("Enter key to access: ")
        print("Value:", data[key])

    except KeyError:
        print("Key not found in dictionary!")

---

## 🧾 file_reader.py

    try:
        file_name = input("Enter file name: ")

        with open(file_name, "r") as f:
            content = f.read()
            print(content)

    except FileNotFoundError:
        print("File does not exist!")

    finally:
        print("File read attempt finished.")

---

## 🧾 custom_exception.py

    def validate_region(region):
        valid_regions = ["us-east-1", "ap-south-1"]

        if region not in valid_regions:
            raise ValueError(f"Invalid region: {region}")

        return region

    try:
        region = input("Enter region: ")
        validated = validate_region(region)
        print("Valid region:", validated)

    except ValueError as e:
        print(e)

---

## 🧠 Concepts Practiced

- try / except / finally  
- Handling ValueError, KeyError, FileNotFoundError  
- Preventing crashes from invalid input  
- Raising custom exceptions  
- Writing safe and reliable Python code  

---

## ▶️ Commands Used

    python3 safe_division.py
    python3 dictionary_access.py
    python3 file_reader.py
    python3 custom_exception.py

---

## 💭 Reflection

Learned how to handle errors instead of letting programs crash.  
Understood how to make scripts more reliable and user-friendly.  
Built confidence in writing production-ready Python code.

---

**Status:** Day 8 of Python Complete ✅