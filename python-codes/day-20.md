# Day 020 – Python Practice Code

**Date:** 01 April 2026  
**Day in Python Journey:** Day 20  

---

## 🎯 Objective

Practice working with JSON files and structured data in Python.  
Learn to store, read, and manipulate data in JSON format used widely in APIs, cloud services, and automation workflows.

---

## 🧾 json_task_manager.py

    import json
    import os

    FILE_NAME = "tasks.json"

    def initialize_file():
        if not os.path.exists(FILE_NAME):
            with open(FILE_NAME, "w") as file:
                json.dump([], file)

    def load_tasks():
        with open(FILE_NAME, "r") as file:
            return json.load(file)

    def save_tasks(tasks):
        with open(FILE_NAME, "w") as file:
            json.dump(tasks, file, indent=4)

    def add_task(task):
        tasks = load_tasks()
        tasks.append({"task": task, "status": "Pending"})
        save_tasks(tasks)
        print(f"Task '{task}' added successfully")

    def list_tasks():
        tasks = load_tasks()

        if not tasks:
            print("No tasks found")
            return

        for i, t in enumerate(tasks, start=1):
            print(f"{i}. {t['task']} - {t['status']}")

    def update_task(task_name):
        tasks = load_tasks()
        updated = False

        for t in tasks:
            if t["task"] == task_name:
                t["status"] = "Completed"
                updated = True

        if updated:
            save_tasks(tasks)
            print(f"Task '{task_name}' marked as completed")
        else:
            print("Task not found")

    def delete_task(task_name):
        tasks = load_tasks()
        new_tasks = []
        deleted = False

        for t in tasks:
            if t["task"] != task_name:
                new_tasks.append(t)
            else:
                deleted = True

        if deleted:
            save_tasks(new_tasks)
            print(f"Task '{task_name}' deleted successfully")
        else:
            print("Task not found")

    def main():
        initialize_file()

        while True:
            print("\n1. Add Task")
            print("2. List Tasks")
            print("3. Complete Task")
            print("4. Delete Task")
            print("5. Exit")

            choice = input("Enter choice: ")

            if choice == "1":
                task = input("Enter task: ")
                add_task(task)

            elif choice == "2":
                list_tasks()

            elif choice == "3":
                task = input("Enter task to complete: ")
                update_task(task)

            elif choice == "4":
                task = input("Enter task to delete: ")
                delete_task(task)

            elif choice == "5":
                print("Exiting...")
                break

            else:
                print("Invalid choice")

    if __name__ == "__main__":
        main()

---

## 🧠 Concepts Practiced

- Reading JSON files using `json.load()`  
- Writing JSON files using `json.dump()`  
- Working with dictionaries and lists  
- Data persistence using JSON format  
- CRUD operations (Create, Read, Update, Delete)  
- Structured data handling similar to APIs  

---

## ▶️ Commands Used

    python json_task_manager.py

---

## 💭 Reflection

Learned how structured data is handled using JSON, which is widely used in APIs and cloud systems.  
Understood how to manage dynamic data using dictionaries and lists.  
Built a task manager that simulates real-world backend data handling.

---

**Status:** Day 20 of Python Complete ✅