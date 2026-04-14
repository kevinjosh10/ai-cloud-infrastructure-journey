# Day 044 – Python Practice Code

**Date:** 14 April 2026  
**Day in Python Journey:** Day 2  

---

## 🎯 Objective

Practice string operations in Python including string methods, slicing, formatting, and text parsing for real-world scenarios.

---

## 🧾 string_methods.py

    text = "hello world"

    print(text.upper())
    print(text.lower())

    text2 = "   python   "
    print(text2.strip())

    sentence = "I like Java"
    print(sentence.replace("Java", "Python"))

    data = "apple,banana,grape"
    fruits = data.split(",")
    print(fruits)

    words = ["Hello", "World"]
    print(" ".join(words))

---

## 🧾 f_strings.py

    name = "Kevin"
    age = 22

    print(f"Hello {name}, you are {age} years old")
    print(f"Next year, you will be {age + 1}")

---

## 🧾 slicing.py

    text = "HelloWorld"

    print(text[0:5])
    print(text[-3:])
    print(text[::2])

---

## 🧾 hostname_parser.py

    hostname = "prod-web-001.example.com"

    parts = hostname.split(".")
    name_part = parts[0]
    domain = ".".join(parts[1:])

    name_parts = name_part.split("-")
    environment = name_parts[0]
    role = name_parts[1]

    print(f"Environment: {environment}")
    print(f"Role: {role}")
    print(f"Domain: {domain}")

---

## 🧠 Concepts Practiced

- String Methods (`upper`, `lower`, `strip`, `replace`, `split`, `join`)  
- f-Strings (formatted strings)  
- String Slicing  
- Text Parsing  
- Working with structured strings  

---

## ▶️ Commands Used

    python3 string_methods.py
    python3 f_strings.py
    python3 slicing.py
    python3 hostname_parser.py

---

## 💭 Reflection

Learned how powerful string manipulation is in Python.  
Understood how to process and extract meaningful data from text.  
This is essential for handling logs, APIs, and cloud infrastructure naming.

---

**Status:** Day 2 of Python Complete ✅