# Day 049 – Python Practice Code

**Date:** 19 April 2026  
**Day in Python Journey:** Day 7  

---

## 🎯 Objective

Practice file handling and JSON parsing by reading, processing, and writing structured data.  
Simulate a real-world cloud scenario by filtering AWS instance data.

---

## 🧾 read_file.py

    with open('config.txt', 'r') as f:
        content = f.read()
        print("File Content:")
        print(content)

---

## 🧾 write_file.py

    with open('output.log', 'w') as f:
        f.write("Log Start\n")
        f.write("System initialized\n")

    with open('output.log', 'a') as f:
        f.write("New log entry added\n")

---

## 🧾 json_parse.py

    import json

    json_string = '{"name": "Kevin", "role": "AI Cloud Engineer"}'

    data = json.loads(json_string)

    print("Parsed Data:")
    print(data)
    print("Name:", data["name"])

---

## 🧾 json_write.py

    import json

    data = {
        "name": "Kevin",
        "skills": ["Python", "AWS", "DevOps"]
    }

    json_output = json.dumps(data, indent=2)

    print(json_output)

---

## 🧾 aws_filter.py

    import json

    # Sample AWS instance data
    instances = [
        {"id": "i-123", "state": "running"},
        {"id": "i-456", "state": "stopped"},
        {"id": "i-789", "state": "running"}
    ]

    # Write sample data to file
    with open('instances.json', 'w') as f:
        json.dump(instances, f, indent=2)

    # Read the file
    with open('instances.json', 'r') as f:
        data = json.load(f)

    # Filter running instances
    running_instances = []

    for instance in data:
        if instance["state"] == "running":
            running_instances.append(instance)

    # Write filtered data
    with open('running_instances.json', 'w') as f:
        json.dump(running_instances, f, indent=2)

    print("Filtered running instances saved.")

---

## 🧠 Concepts Practiced

- File Reading (`r` mode)  
- File Writing (`w` mode)  
- File Appending (`a` mode)  
- JSON Parsing (`json.loads`)  
- JSON Serialization (`json.dumps`)  
- Reading JSON files (`json.load`)  
- Writing JSON files (`json.dump`)  
- Data Filtering using loops and conditions  

---

## ▶️ Commands Used

    python3 read_file.py
    python3 write_file.py
    python3 json_parse.py
    python3 json_write.py
    python3 aws_filter.py

---

## 💭 Reflection

Learned how real-world applications handle data using files and JSON.  
Understood how cloud systems exchange structured data.  
Built a mini data pipeline: Read → Process → Filter → Save.  
This is a core skill for automation, DevOps, and cloud engineering.

---

**Status:** Day 7 of Python Complete ✅  