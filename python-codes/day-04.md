# Day 046 – Python Practice Code

**Date:** 16 April 2026  
**Day in Python Journey:** Day 4  

---

## 🎯 Objective

Practice Python data structures by working with dictionaries, dictionary operations, comprehensions, and sets. Model a real-world AWS EC2 instance using Python.

---

## 🧾 dictionary_basics.py

    instance = {
        'id': 'i-abc123',
        'type': 't2.micro',
        'state': 'running'
    }

    print("Instance ID:", instance['id'])
    print("Instance State:", instance.get('state'))
    print("Instance Zone:", instance.get('zone', 'N/A'))

    print("Keys:", instance.keys())
    print("Values:", instance.values())
    print("Items:", instance.items())

---

## 🧾 dict_comprehension.py

    tags = {
        'env': 'dev',
        'owner': 'kevin'
    }

    upper_tags = {k: v.upper() for k, v in tags.items()}

    print("Original Tags:", tags)
    print("Uppercase Tags:", upper_tags)

---

## 🧾 sets_practice.py

    regions = {'us-east-1', 'us-west-2', 'us-east-1'}
    print("Unique Regions:", regions)

    a = {'us-east-1', 'eu-west-1'}
    b = {'us-east-1', 'ap-south-1'}

    print("Union:", a | b)
    print("Intersection:", a & b)
    print("Difference:", a - b)

---

## 🧾 ec2_model.py

    instance = {
        'instance_id': 'i-123456',
        'type': 't2.micro',
        'state': 'running',
        'region': 'ap-south-1',
        'tags': {
            'env': 'dev',
            'owner': 'kevin'
        }
    }

    def get_instance_value(inst, key):
        return inst.get(key, 'Not Found')

    def set_instance_value(inst, key, value):
        inst[key] = value

    def get_tag(inst, tag_key):
        return inst['tags'].get(tag_key, 'No Tag')

    def set_tag(inst, tag_key, tag_value):
        inst['tags'][tag_key] = tag_value

    print(get_instance_value(instance, 'state'))

    set_instance_value(instance, 'state', 'stopped')

    print(get_tag(instance, 'env'))

    set_tag(instance, 'project', 'ai-cloud')

    print(instance)

---

## 🧠 Concepts Practiced

- Dictionaries (key-value pairs)  
- Dictionary operations (`get`, `keys`, `values`, `items`)  
- Dictionary comprehensions  
- Sets (unique, unordered data)  
- Set operations (union, intersection, difference)  
- Nested dictionaries  
- Functions for data manipulation  

---

## ▶️ Commands Used

    python3 dictionary_basics.py
    python3 dict_comprehension.py
    python3 sets_practice.py
    python3 ec2_model.py

---

## 💭 Reflection

Learned how real-world cloud data is structured using dictionaries.  
Understood how to manipulate and transform data efficiently.  
Gained hands-on experience modeling an AWS EC2 instance.  
Built a strong foundation for working with APIs, JSON, and automation.

---

**Status:** Day 4 of Python Complete ✅  
