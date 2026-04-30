# Day 018 – Python Practice Code

**Date:** 30 March 2026  
**Day in Python Journey:** Day 18  

---

## 🎯 Objective

Practice working with file handling and JSON data in Python.  
Learn to read, write, and manipulate structured data for real-world cloud and automation use cases.

---

## 🧾 json_user_manager.py

    import json
    import os

    FILE_NAME = "users.json"

    def load_users():
        if not os.path.exists(FILE_NAME):
            return []
        with open(FILE_NAME, "r") as file:
            return json.load(file)

    def save_users(users):
        with open(FILE_NAME, "w") as file:
            json.dump(users, file, indent=4)

    def add_user(name, age):
        users = load_users()
        users.append({"name": name, "age": age})
        save_users(users)
        print(f"User {name} added successfully")

    def list_users():
        users = load_users()
        if not users:
            print("No users found")
            return
        for i, user in enumerate(users, start=1):
            print(f"{i}. Name: {user['name']}, Age: {user['age']}")

    def delete_user(name):
        users = load_users()
        updated_users = [user for user in users if user["name"] != name]

        if len(users) == len(updated_users):
            print("User not found")
        else:
            save_users(updated_users)
            print(f"User {name} deleted successfully")

    def main():
        while True:
            print("\n1. Add User")
            print("2. List Users")
            print("3. Delete User")
            print("4. Exit")

            choice = input("Enter choice: ")

            if choice == "1":
                name = input("Enter name: ")
                age = int(input("Enter age: "))
                add_user(name, age)

            elif choice == "2":
                list_users()

            elif choice == "3":
                name = input("Enter name to delete: ")
                delete_user(name)

            elif choice == "4":
                print("Exiting...")
                break

            else:
                print("Invalid choice")

    if __name__ == "__main__":
        main()

---

## 🧠 Concepts Practiced

- Reading JSON files using `json.load()`  
- Writing JSON data using `json.dump()`  
- File handling in Python (`open`, `read`, `write`)  
- Checking file existence using `os.path.exists()`  
- Basic CRUD operations (Create, Read, Delete)  
- Working with lists and dictionaries  

---

## ▶️ Commands Used

    python json_user_manager.py

---

## 💭 Reflection

Learned how structured data is stored and managed using JSON in Python applications.  
Understood how real-world tools persist data using files instead of temporary variables.  
Gained hands-on experience in building a simple data management system.

---

**Status:** Day 18 of Python Complete ✅  