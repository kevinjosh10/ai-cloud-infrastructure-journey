# Day 051 – Python Practice Code

**Date:** 21 April 2026  
**Day in Python Journey:** Day 51  

---

## 🎯 Objective

Practice working with REST APIs using the `requests` library.  
Learn how to fetch, send, and process data from real-world APIs.

---

## 🧾 get_request.py

    import requests

    url = "https://api.github.com"

    response = requests.get(url)

    print("Status Code:", response.status_code)
    print("Response:", response.json())

---

## 🧾 post_request.py

    import requests

    url = "https://httpbin.org/post"

    data = {
        "name": "Kevin",
        "goal": "AI Cloud Engineer"
    }

    response = requests.post(url, json=data)

    print("Response:", response.json())

---

## 🧾 github_repos.py

    import requests

    username = "kevinjosh10"
    url = f"https://api.github.com/users/{username}/repos"

    response = requests.get(url)

    if response.status_code == 200:
        repos = response.json()

        for repo in repos:
            print(repo["name"], "-", repo["language"])
    else:
        print("Failed to fetch repositories")

---

## 🧾 session_example.py

    import requests

    session = requests.Session()

    session.headers.update({
        "User-Agent": "python-script"
    })

    response = session.get("https://api.github.com")

    print(response.status_code)

---

## 🧾 timeout_handling.py

    import requests

    try:
        response = requests.get("https://api.github.com", timeout=5)
        print(response.json())
    except requests.exceptions.Timeout:
        print("Request timed out")

---

## 🧠 Concepts Practiced

- REST API basics  
- GET and POST requests  
- JSON handling (`response.json()`)  
- Headers and sessions  
- Timeout handling  
- Working with real-world APIs (GitHub API)  

---

## ▶️ Commands Used

    pip install requests
    python3 get_request.py
    python3 post_request.py
    python3 github_repos.py
    python3 session_example.py
    python3 timeout_handling.py

---

## 💭 Reflection

Learned how real-world applications communicate using APIs.  
Built scripts to fetch and send data over the internet.  
Took a big step towards backend, cloud, and automation skills.

---

**Status:** Day 51 of Python Complete ✅  
