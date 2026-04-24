# Day 012 – Python Practice Code

**Date:** 24 April 2026  
**Day in Python Journey:** Day 12  

---

## 🎯 Objective

Practice Python **loops (for & while)**, iteration control, and build logical thinking using repetitive tasks.

---

## 🧾 loops.py

    # FOR LOOP EXAMPLES

    print("Numbers from 1 to 5:")
    for i in range(1, 6):
        print(i)


    print("\nEven numbers from 1 to 10:")
    for i in range(1, 11):
        if i % 2 == 0:
            print(i)


    print("\nSum of numbers from 1 to 10:")
    total = 0
    for i in range(1, 11):
        total += i
    print("Total:", total)

---

## 🧾 while_loop.py

    # WHILE LOOP EXAMPLES

    print("Counting from 1 to 5:")
    count = 1

    while count <= 5:
        print(count)
        count += 1


    print("\nPassword Checker:")

    correct_password = "admin123"
    user_input = ""

    while user_input != correct_password:
        user_input = input("Enter password: ")

    print("Access Granted ✅")

---

## 🧠 Concepts Practiced

- for loops  
- while loops  
- range() function  
- Conditional statements inside loops  
- Loop control with counters  
- Basic logic building  

---

## ▶️ Commands Used

    python3 loops.py
    python3 while_loop.py

---

## 💭 Reflection

Learned how loops automate repetitive tasks.  
Understood the difference between for and while loops.  
Built problem-solving mindset using iteration and conditions.  

---

**Status:** Day 12 of Python Complete ✅  