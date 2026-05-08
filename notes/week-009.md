# WEEK 9 NOTES — PYTHON FOR CLOUD III  
## CLI SCRIPTS, YAML & AWS AUTOMATION

**Focus:**  
Build production-quality Python CLI tools using argparse, logging, YAML configuration, and real AWS automation workflows.

---

# 📌 WEEK 9 OVERVIEW

This week focused on transforming basic Python scripts into professional cloud automation tools.

Main goals:
- Build CLI-based tools
- Add structured logging
- Use YAML config files
- Automate AWS infrastructure tasks
- Organize projects professionally
- Create portfolio-quality repositories

---

# 🟢 DAY 57 — CLI SCRIPTS WITH ARGPARSE

# 🎯 Goal
Learn how to create professional command-line tools using Python’s `argparse` module.

---

# ✅ IMPORT ARGPARSE

```python
import argparse
```

---

# ✅ CREATE A PARSER

```python
parser = argparse.ArgumentParser(
    description="AWS EC2 Tool"
)
```

Purpose:
- Defines CLI application
- Adds help menus automatically
- Parses user arguments

---

# ✅ POSITIONAL ARGUMENTS

Required arguments.

Example:

```python
parser.add_argument("region")
```

Usage:

```bash
python app.py us-east-1
```

---

# ✅ OPTIONAL ARGUMENTS

Optional flags using `--`

Example:

```python
parser.add_argument(
    "--profile",
    default="default"
)
```

Usage:

```bash
python app.py us-east-1 --profile dev
```

---

# ✅ ARGUMENT TYPES

```python
parser.add_argument(
    "--count",
    type=int
)
```

Supported:
- `str`
- `int`
- `float`
- `bool`

---

# ✅ CHOICES

Restrict allowed values.

```python
parser.add_argument(
    "--action",
    choices=["start", "stop"]
)
```

---

# ✅ REQUIRED OPTIONAL ARGUMENTS

```python
parser.add_argument(
    "--region",
    required=True
)
```

---

# ✅ HELP TEXT

```python
parser.add_argument(
    "--state",
    help="Filter EC2 state"
)
```

---

# ✅ PARSE ARGUMENTS

```python
args = parser.parse_args()
```

Access values:

```python
print(args.region)
```

---

# ✅ SUBCOMMANDS

Used in professional CLI tools.

Example:
- list
- start
- stop

---

## Create Subparsers

```python
subparsers = parser.add_subparsers(dest="command")
```

---

## Example Subcommand

```python
list_parser = subparsers.add_parser("list")
```

---

# ✅ PRACTICAL EC2 CLI TOOL

Example command:

```bash
python ec2_tool.py list \
    --region us-east-1 \
    --state running \
    --output table
```

---

# 🧠 KEY LEARNINGS

- Professional CLI structure
- User-friendly automation tools
- Standard Linux-style tooling
- Reusable cloud scripts

---

# 🟢 DAY 58 — PYTHON LOGGING MODULE

# 🎯 Goal
Replace print statements with professional logging.

---

# ✅ LOGGING LEVELS

| Level | Purpose |
|---|---|
| DEBUG | Detailed debugging |
| INFO | General operations |
| WARNING | Unexpected but non-fatal |
| ERROR | Operation failed |
| CRITICAL | Severe failure |

---

# ✅ BASIC LOGGING CONFIGURATION

```python
import logging

logging.basicConfig(
    level=logging.INFO,
    format="%(asctime)s - %(name)s - %(levelname)s - %(message)s"
)
```

---

# ✅ CREATE LOGGER

```python
logger = logging.getLogger(__name__)
```

---

# ✅ LOG MESSAGES

```python
logger.info("Starting scan")
logger.warning("Low disk space")
logger.error("Failed to connect")
```

---

# ✅ LOGGING TO FILE

```python
from logging import FileHandler

file_handler = FileHandler("app.log")
```

---

# ✅ CONSOLE LOGGING

```python
from logging import StreamHandler

console_handler = StreamHandler()
```

---

# ✅ LOG ROTATION

Prevents massive log files.

```python
from logging.handlers import RotatingFileHandler

RotatingFileHandler(
    "app.log",
    maxBytes=10*1024*1024,
    backupCount=5
)
```

---

# ✅ SHARED LOGGER MODULE

Example:

```python
# logger.py

import logging

logger = logging.getLogger("aws-tool")
```

---

# 🧠 KEY LEARNINGS

- Industry-standard logging
- Easier debugging
- Persistent application logs
- Better observability

---

# 🟢 DAY 59 — YAML PARSING & CONFIG FILES

# 🎯 Goal
Use YAML configuration files in automation tools.

---

# ✅ INSTALL PYYAML

```bash
pip install pyyaml
```

---

# ✅ YAML BASICS

Example:

```yaml
region: us-east-1

instances:
  - web
  - db

logging:
  level: INFO
```

---

# ✅ YAML RULES

- Indentation-based
- Uses key:value pairs
- Lists use `-`
- Supports nested objects

---

# ✅ READ YAML

```python
import yaml

with open("config.yaml") as file:
    config = yaml.safe_load(file)
```

---

# ✅ WHY safe_load()?

More secure than `load()`

Avoids arbitrary code execution.

---

# ✅ WRITE YAML

```python
yaml.dump(
    data,
    file,
    default_flow_style=False
)
```

---

# ✅ CONFIG.YAML FOR AWS TOOL

Example:

```yaml
regions:
  - us-east-1
  - us-west-2

output: table

log_level: INFO
```

---

# ✅ CLI OVERRIDES CONFIG

Priority:

```text
CLI Arguments > YAML Config > Defaults
```

Example:

```bash
python app.py --region ap-south-1
```

Overrides YAML value.

---

# 🧠 KEY LEARNINGS

- External configuration management
- Cleaner applications
- Real-world DevOps practices
- Environment flexibility

---

# 🟢 DAY 60 — AWS RESOURCE INVENTORY TOOL

# 🎯 Goal
Build a multi-service AWS inventory scanner.

---

# ✅ SERVICES SCANNED

- EC2
- S3
- RDS
- Lambda

---

# ✅ MULTI-REGION SCANNING

Used AWS regions dynamically.

---

# ✅ PARALLEL EXECUTION

```python
from concurrent.futures import ThreadPoolExecutor
```

Example:

```python
with ThreadPoolExecutor(max_workers=5) as executor:
```

Purpose:
- Faster scanning
- Concurrent AWS API calls

---

# ✅ OUTPUT FORMATS

## JSON

```python
json.dump(data, file)
```

---

## TABLE FORMAT

Used:

```bash
pip install tabulate
```

Example:

```python
from tabulate import tabulate
```

---

# ✅ COST ESTIMATION

Mapped:
- EC2 type
- Hourly pricing
- Monthly estimate

Example:

```python
monthly_cost = hourly_cost * 24 * 30
```

---

# ✅ GITHUB PROJECT

Repository:

```text
aws-resource-inventory
```

---

# 🧠 KEY LEARNINGS

- Real AWS automation
- Multi-threading
- Infrastructure visibility
- Cost awareness

---

# 🟢 DAY 61 — EC2 LIFECYCLE MANAGER

# 🎯 Goal
Automate EC2 operations safely.

---

# ✅ OPERATIONS

- Start
- Stop
- Reboot
- Terminate

---

# ✅ TARGETING INSTANCES

By:
- Instance ID
- Tags

Example:

```bash
python ec2_lifecycle.py stop \
    --tag Environment=dev
```

---

# ✅ DRY RUN MODE

```bash
--dry-run
```

Purpose:
- Show planned actions
- Avoid accidental changes

---

# ✅ CONFIRMATION PROMPTS

Example:

```python
confirm = input("Continue? (y/n): ")
```

---

# ✅ YAML SCHEDULING

Example:

```yaml
schedule:
  stop: "22:00"
  start: "08:00"
```

---

# ✅ ERROR HANDLING

Used:

```python
from botocore.exceptions import ClientError
```

---

# 🧠 KEY LEARNINGS

- Safe infrastructure automation
- Scheduling operations
- Tag-based resource management
- Production safety mechanisms

---

# 🟢 DAY 62 — S3 BACKUP TOOL

# 🎯 Goal
Build a production-ready S3 backup system.

---

# ✅ FEATURES

- Upload backups
- Download backups
- Sync directories
- Incremental uploads

---

# ✅ TIMESTAMPED BACKUPS

Example:

```text
backup-2026-05-01/
```

---

# ✅ INCREMENTAL BACKUP

Compared:
- Local MD5
- S3 ETag

Only changed files uploaded.

---

# ✅ ENCRYPTION

Used:

```python
ServerSideEncryption='AES256'
```

OR

```python
SSEKMSKeyId='key-id'
```

---

# ✅ LIFECYCLE POLICIES

Automated:
- 30 days → IA
- 90 days → Glacier
- 365 days → Delete

---

# ✅ GITHUB REPOSITORY

```text
s3-backup-tool
```

---

# 🧠 KEY LEARNINGS

- Backup automation
- Storage optimization
- Secure uploads
- Lifecycle management

---

# 🟢 DAY 63 — WEEK 9 REVIEW & PORTFOLIO

# 🎯 Goal
Standardize all Python projects professionally.

---

# ✅ AUDITED ALL CODE

Checked:
- Logging
- Error handling
- argparse usage
- YAML support

---

# ✅ RAN flake8

Install:

```bash
pip install flake8
```

Run:

```bash
flake8 *.py
```

Fixed:
- Formatting issues
- Style problems
- Unused imports

---

# ✅ ADDED DOCSTRINGS

Example:

```python
def list_instances(region):
    """
    Fetch EC2 instances.

    Args:
        region (str)

    Returns:
        list
    """
```

---

# ✅ ORGANIZED MASTER REPO

Repository:

```text
aws-python-tools
```

Structure:

```text
aws-python-tools/
│
├── ec2/
├── s3/
├── iam/
├── utils/
├── config/
├── README.md
├── requirements.txt
```

---

# ✅ CREATED README

Included:
- Features
- Installation
- Usage examples
- Config setup
- Dependencies

---

# 🧠 WEEK 9 CORE CONCEPTS

- Professional CLI development
- Structured logging
- YAML configuration management
- AWS automation
- Threading & concurrency
- Production-grade scripting
- Portfolio organization

---

# 🔥 MAJOR MINDSET SHIFT

Moved from:

> Writing simple Python scripts

To:

> Building production-quality cloud automation systems

---

# 🚀 WEEK 9 OUTCOME

By the end of Week 9, I built:
- Professional CLI tools
- Config-driven AWS automation
- Logging-enabled applications
- Real infrastructure management tools
- Portfolio-ready GitHub projects

---

# 📌 PORTFOLIO PROJECTS CREATED

1. aws-resource-inventory  
2. ec2-lifecycle-manager  
3. s3-backup-tool  
4. aws-python-tools  

---

# 💭 FINAL REFLECTION

Week 9 was one of the most important phases in the journey.

Learned:
- Real DevOps scripting practices
- Infrastructure automation
- Project organization
- Professional coding standards

Built confidence in:
- Python for cloud engineering
- AWS automation workflows
- Writing maintainable production code

---

**Week 9 Status:** Complete ✅  
**Days Completed:** 57–63 / 1000 🚀