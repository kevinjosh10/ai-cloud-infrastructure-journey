# Week 7 – Python Fundamentals for Cloud Engineering

**Duration:** Day 43 – Day 49  
**Focus:** Core Python for Automation, Data Handling & Cloud Workflows  

---

## 🎯 Objective

Build a strong Python foundation for cloud and DevOps engineering by learning variables, data structures, control flow, functions, and file/JSON handling.  
Focus on real-world applications like AWS data processing and automation.

---

## 📘 Day 43 – Python Setup & Variables

### Key Learnings
- Installed Python 3.x and verified setup  
- Created virtual environment for isolated development  
- Configured VS Code with Python interpreter  

### Variables & Data Types
- No type declaration required  
- Dynamic typing  

Examples:
- `str` → text  
- `int` → whole numbers  
- `float` → decimal numbers  
- `bool` → True/False  

### Type Conversion
- Convert between types:
  - string → int  
  - int → string  
  - string → float  

### Outcome
- Wrote first Python script  
- Understood how programs run  
- Built base for scripting  

---

## 📘 Day 44 – Strings & String Operations

### Key Learnings

#### String Methods
- Modify and clean text:
  - uppercase / lowercase  
  - remove spaces  
  - replace words  
  - split and join  

#### f-Strings
- Modern way to format strings  
- Embed variables directly into text  

#### String Slicing
- Extract parts of strings  
- Useful for parsing structured data  

#### Multiline Strings
- Handle large text blocks (logs, configs, SQL)  

### Real-World Use
- Parsed server hostname:
  - Extracted environment  
  - Extracted role  
  - Extracted domain  

---

## 📘 Day 45 – Lists & Tuples

### Lists
- Ordered, mutable collection  
- Can add, remove, sort elements  

### List Operations
- Add elements  
- Remove elements  
- Sort and reverse  
- Access using index  

### List Comprehension
- Create new lists efficiently  
- Used for filtering and transformation  

### Tuples
- Immutable data structure  
- Used for fixed values (e.g., IP + port)  

### Outcome
- Managed collections of servers  
- Filtered AWS regions  
- Learned efficient data handling  

---

## 📘 Day 46 – Dictionaries & Sets

### Dictionaries
- Key-value pairs  
- Represent structured data (like AWS instances)  

### Operations
- Access values  
- Handle missing keys safely  
- Iterate over keys and values  

### Dict Comprehension
- Transform data easily  

### Sets
- Store unique values  
- Perform operations:
  - Union  
  - Intersection  

### Real-World Use
- Modeled EC2 instance:
  - instance_id  
  - type  
  - state  
  - region  
  - tags  

---

## 📘 Day 47 – Loops & Conditionals

### For Loops
- Iterate over lists and dictionaries  
- Access index + value  

### While Loops
- Useful for retry logic in automation  

### Conditionals
- Decision making:
  - if / elif / else  

### Control Statements
- `break` → stop loop  
- `continue` → skip iteration  
- `pass` → placeholder  

### Real-World Use
- Filtered EC2 instances:
  - Only "running"  
  - Only specific region  

---

## 📘 Day 48 – Functions & Modules

### Functions
- Reusable blocks of logic  
- Accept parameters  
- Return values  

### Advanced Concepts
- Default parameters  
- Multiple return values  
- Flexible arguments (*args, **kwargs)  

### Modules
- Use built-in libraries:
  - os  
  - sys  
  - json  
  - datetime  

### Real-World Use
- Created helper module:
  - Format instance IDs  
  - Extract region  
  - Calculate runtime  

---

## 📘 Day 49 – File I/O & JSON Parsing

### File Handling
- Read files safely using context manager  
- Write and append data to files  

### JSON Handling
- Standard format for APIs and cloud systems  

### Key Operations
- Parse JSON → usable data  
- Convert data → JSON format  

### JSON Files
- Read structured data from files  
- Write processed results back  

### Real-World Use
- Simulated AWS data pipeline:
  - Read instance data  
  - Filter by state  
  - Save results  

---

## 🧠 Key Concepts Learned This Week

- Python fundamentals for scripting  
- Data structures (lists, dicts, sets, tuples)  
- String processing for real-world parsing  
- Control flow for automation logic  
- Functions and modular programming  
- File handling and JSON (core for cloud & APIs)  

---

## 🔄 Mindset Shift

Moved from:

> Learning syntax  

To:

> Thinking like an engineer handling real-world data and automation  

---

## 💭 Reflection

Week 7 was a major step toward becoming an AI Cloud Infrastructure Engineer.

Built:
- Strong Python foundation  
- Ability to process and filter real-world data  
- Understanding of cloud-like workflows  
- Confidence to build automation scripts  

This week connects directly to:
- AWS scripting  
- API handling  
- DevOps automation  
- Data pipelines  

---

**Status:** Week 7 Complete ✅  
**Progress:** 49 / 1000 Days 🚀  