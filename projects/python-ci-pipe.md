# Day 069 Project – Python CI Pipeline with GitHub Actions

## 📌 Project Title
Python CI/CD Automation Pipeline using GitHub Actions

---

## 🎯 Project Objective

Build a professional GitHub Actions CI pipeline that automatically:

- Lints Python code using `flake8`
- Runs automated tests using `pytest`
- Triggers on every push and pull request
- Displays CI build status using a README badge

This project introduces real-world CI/CD automation workflows used in modern DevOps and cloud engineering teams.

---

## 🧱 Project Structure

```bash
python-ci-demo/
│
├── app.py
├── requirements.txt
├── README.md
├── tests/
│   └── test_math.py
│
└── .github/
    └── workflows/
        ├── lint.yml
        └── ci.yml
```

---

# ⚙️ Step 1 – Create Project Folder

```bash
mkdir python-ci-demo
cd python-ci-demo
```

---

# ⚙️ Step 2 – Create Python Application

## `app.py`

```python
def add(a, b):
    return a + b


print(add(2, 3))
```

---

# ⚙️ Step 3 – Create Test File

## `tests/test_math.py`

```python
from app import add


def test_add():
    assert add(2, 3) == 5
```

---

# ⚙️ Step 4 – Install Dependencies

```bash
pip install flake8 pytest
```

---

# ⚙️ Step 5 – Create Lint Workflow

## `.github/workflows/lint.yml`

```yaml
name: Python Linting

on:
  push:

jobs:
  lint:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout Repository
        uses: actions/checkout@v4

      - name: Set up Python
        uses: actions/setup-python@v5
        with:
          python-version: "3.11"

      - name: Install flake8
        run: |
          pip install flake8

      - name: Run flake8
        run: |
          flake8 .
```

---

# ⚙️ Step 6 – Create Full CI Workflow

## `.github/workflows/ci.yml`

```yaml
name: CI Pipeline

on:
  push:
  pull_request:

jobs:
  lint:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v4

      - uses: actions/setup-python@v5
        with:
          python-version: "3.11"

      - run: pip install flake8

      - run: flake8 .

  test:
    needs: lint

    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v4

      - uses: actions/setup-python@v5
        with:
          python-version: "3.11"

      - run: pip install pytest

      - run: pytest
```

---

# ⚙️ Step 7 – Create README Badge

## `README.md`

```md
# Python CI Demo

![CI](https://github.com/username/python-ci-demo/actions/workflows/ci.yml/badge.svg)

Simple Python project demonstrating CI/CD automation using GitHub Actions.
```

Replace:
```bash
username
```

with your GitHub username.

---

# ⚙️ Step 8 – Initialize Git Repository

```bash
git init
git add .
git commit -m "Initial CI pipeline setup"
```

---

# ⚙️ Step 9 – Push to GitHub

```bash
git remote add origin <your-repo-url>

git branch -M main

git push -u origin main
```

---

# 🔍 What Happens After Push?

GitHub automatically:

✅ Starts workflow  
✅ Creates Ubuntu runner  
✅ Installs Python  
✅ Installs flake8 & pytest  
✅ Runs lint checks  
✅ Runs automated tests  
✅ Shows success/failure in Actions tab  

---

# 🧪 Testing CI Failure

Intentionally break code:

```python
def add(a, b)
    return a + b
```

Push changes.

Observe:
- Workflow fails
- Error logs appear in Actions tab

Fix issue and push again.

This simulates real-world CI debugging workflows.

---

# 🧠 Concepts Practiced

- GitHub Actions workflows
- YAML syntax
- CI/CD fundamentals
- Workflow triggers
- Jobs & steps
- Runners
- Python linting
- Automated testing
- Workflow dependencies
- CI badges
- DevOps automation basics

---

# 🚀 Real-World Relevance

This project reflects real engineering practices used in:

- DevOps teams
- Cloud infrastructure teams
- Backend engineering
- AI/ML deployment pipelines
- Production software systems

CI/CD automation is a core skill for modern AI Cloud Infrastructure Engineers.

---

# 📈 Possible Future Improvements

Future upgrades:
- Add Docker build workflow
- Add Terraform validation
- Add AWS deployment pipeline
- Add Kubernetes deployment
- Add code coverage reports
- Add security scanning
- Add multi-version Python testing

---

# ✅ Final Outcome

Built a fully automated Python CI pipeline using GitHub Actions that:

- Validates code quality
- Runs tests automatically
- Detects issues early
- Demonstrates real DevOps engineering practices

---

**Project Status:** Complete ✅  
**Day:** 69 / 1000 🚀