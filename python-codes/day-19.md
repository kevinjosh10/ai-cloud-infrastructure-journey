# Day 019 – Python Practice Code

**Date:** 31 March 2026  
**Day in Python Journey:** Day 19  

---

## 🎯 Objective

Practice working with CSV files and data processing in Python.  
Learn to read, write, and manipulate tabular data commonly used in cloud logs, reports, and automation workflows.

---

## 🧾 csv_task_manager.py

    import csv
    import os

    FILE_NAME = "tasks.csv"

    def initialize_file():
        if not os.path.exists(FILE_NAME):
            with open(FILE_NAME, "w", newline="") as file:
                writer = csv.writer(file)
                writer.writerow(["Task", "Status"])

    def add_task(task):
        with open(FILE_NAME, "a", newline="") as file:
            writer = csv.writer(file)
            writer.writerow([task, "Pending"])
        print(f"Task '{task}' added successfully")

    def list_tasks():
        with open(FILE_NAME, "r") as file:
            reader = csv.reader(file)
            next(reader)  # Skip header

            tasks = list(reader)
            if not tasks:
                print("No tasks found")
                return

            for i, (task, status) in enumerate(tasks, start=1):
                print(f"{i}. {task} - {status}")

    def update_task(task_name):
        tasks = []
        updated = False

        with open(FILE_NAME, "r") as file:
            reader = csv.reader(file)
            header = next(reader)

            for row in reader:
                if row[0] == task_name:
                    row[1] = "Completed"
                    updated = True
                tasks.append(row)

        if updated:
            with open(FILE_NAME, "w", newline="") as file:
                writer = csv.writer(file)
                writer.writerow(header)
                writer.writerows(tasks)
            print(f"Task '{task_name}' marked as completed")
        else:
            print("Task not found")

    def delete_task(task_name):
        tasks = []
        deleted = False

        with open(FILE_NAME, "r") as file:
            reader = csv.reader(file)
            header = next(reader)

            for row in reader:
                if row[0] != task_name:
                    tasks.append(row)
                else:
                    deleted = True

        if deleted:
            with open(FILE_NAME, "w", newline="") as file:
                writer = csv.writer(file)
                writer.writerow(header)
                writer.writerows(tasks)
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

- Reading CSV files using `csv.reader()`  
- Writing CSV files using `csv.writer()`  
- File handling with `newline=""` for CSV correctness  
- Creating and managing tabular data  
- CRUD operations (Create, Read, Update, Delete)  
- Data persistence using CSV format  

---

## ▶️ Commands Used

    python csv_task_manager.py

---

## 💭 Reflection

Learned how tabular data is stored and processed using CSV files.  
Understood how real-world systems handle logs, reports, and structured datasets.  
Built a simple task manager that simulates real automation workflows.

---

**Status:** Day 19 of Python Complete ✅