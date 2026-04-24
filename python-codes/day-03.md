# Day 045 – Lists & Tuples Practice Code

**Date:** 15 April 2026  
**Day in Python Journey:** Day 3  

---

## 🎯 Objective

Practice Python data structures by working with lists and tuples.  
Understand how to store, modify, and process grouped data efficiently.

---

## 🧾 lists_basics.py

    servers = ['web-01', 'web-02', 'db-01']

    print("All servers:", servers)
    print("First server:", servers[0])
    print("Last server:", servers[-1])

---

## 🧾 list_methods.py

    servers = ['web-01', 'web-02', 'db-01']

    servers.append('web-03')
    print("After append:", servers)

    servers.remove('db-01')
    print("After remove:", servers)

    servers.sort()
    print("Sorted:", servers)

    servers.reverse()
    print("Reversed:", servers)

    servers.pop()
    print("After pop:", servers)

    print("Total servers:", len(servers))

---

## 🧾 list_slicing.py

    servers = ['web-01', 'web-02', 'web-03', 'db-01']

    print("First two:", servers[0:2])
    print("First three:", servers[:3])
    print("Last server:", servers[-1])

---

## 🧾 list_comprehension.py

    servers = ['web-01', 'web-02', 'db-01']

    upper_servers = [s.upper() for s in servers]
    print("Uppercase:", upper_servers)

    web_servers = [s for s in servers if 'web' in s]
    print("Web servers:", web_servers)

---

## 🧾 tuples.py

    config = ('prod', '10.0.0.1', 443)

    print("Environment:", config[0])
    print("IP Address:", config[1])
    print("Port:", config[2])

---

## 🧾 aws_regions.py

    regions = ['us-east-1', 'us-west-2', 'ap-south-1', 'eu-west-1', 'us-east-2']

    regions.sort()
    print("Sorted regions:", regions)

    us_regions = [r for r in regions if r.startswith('us-')]
    print("US regions:", us_regions)

---

## 🧠 Concepts Practiced

- Lists (creation, indexing)  
- List Methods (`append`, `remove`, `sort`, `reverse`, `pop`, `len`)  
- List Slicing  
- List Comprehensions  
- Tuples (immutable data)  
- Working with grouped data  

---

## ▶️ Commands Used

    python3 lists_basics.py
    python3 list_methods.py
    python3 list_slicing.py
    python3 list_comprehension.py
    python3 tuples.py
    python3 aws_regions.py

---

## 💭 Reflection

Learned how to handle multiple data values efficiently using lists and tuples.  
Understood how real-world data like servers and regions can be managed using Python.  
Improved ability to write cleaner and more optimized code.

---

**Status:** Day 3 of Python Complete ✅
