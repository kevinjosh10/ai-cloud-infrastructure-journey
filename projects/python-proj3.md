# WEEK 9 PROJECTS — PYTHON FOR CLOUD III

**Focus:**  
Production-Quality Python CLI Tools, YAML Configurations & AWS Automation

---

# 🚀 WEEK 9 PROJECT OVERVIEW

During Week 9, multiple real-world AWS automation tools were designed and built using Python.

Main technologies used:
- Python
- boto3
- argparse
- logging
- PyYAML
- concurrent.futures
- tabulate

---

# 📦 PROJECT 1 — EC2 CLI MANAGEMENT TOOL

## 🎯 Objective
Convert a simple EC2 reporting script into a professional command-line automation tool.

---

# ✅ Features

- List EC2 instances
- Filter by region
- Filter by instance state
- Multiple output formats
- AWS profile support
- CLI argument parsing

---

# ✅ Technologies Used

- Python
- argparse
- boto3

---

# ✅ Example Commands

```bash
python ec2_tool.py list \
    --region us-east-1 \
    --state running \
    --output table
```

---

# ✅ Key Concepts Practiced

- argparse CLI design
- Optional & positional arguments
- Subcommands
- AWS EC2 APIs
- User-friendly automation

---

# 📂 Example Structure

```text
ec2-cli-tool/
│
├── ec2_tool.py
├── requirements.txt
└── README.md
```

---

# 📦 PROJECT 2 — SHARED PYTHON LOGGER MODULE

## 🎯 Objective
Create a reusable centralized logging system for all AWS automation scripts.

---

# ✅ Features

- Console logging
- File logging
- Rotating log files
- Multiple log levels
- Shared logger import

---

# ✅ Technologies Used

- logging
- RotatingFileHandler

---

# ✅ Example Log Format

```text
2026-05-01 10:00:00 - app - INFO - Starting scan
```

---

# ✅ Key Concepts Practiced

- DEBUG / INFO / ERROR levels
- Logging best practices
- Centralized logging architecture
- Production observability

---

# 📂 Example Structure

```text
logger-module/
│
├── logger.py
├── app.log
└── README.md
```

---

# 📦 PROJECT 3 — YAML CONFIGURATION SYSTEM

## 🎯 Objective
Build configuration-driven AWS tools using YAML files.

---

# ✅ Features

- Read YAML configs
- Write YAML configs
- Environment customization
- CLI override support

---

# ✅ Technologies Used

- PyYAML

---

# ✅ Example Config

```yaml
regions:
  - us-east-1
  - ap-south-1

output: table

logging:
  level: INFO
```

---

# ✅ Key Concepts Practiced

- yaml.safe_load()
- Config-driven applications
- Nested YAML structures
- Environment flexibility

---

# 📂 Example Structure

```text
yaml-config-system/
│
├── config.yaml
├── config_loader.py
└── README.md
```

---

# 📦 PROJECT 4 — AWS RESOURCE INVENTORY TOOL

## 🎯 Objective
Create a multi-service AWS inventory scanner across all AWS regions.

---

# ✅ Features

- Scan EC2 instances
- Scan S3 buckets
- Scan RDS databases
- Scan Lambda functions
- Parallel region scanning
- JSON output
- Table output
- Cost estimation

---

# ✅ Technologies Used

- boto3
- concurrent.futures
- tabulate
- json

---

# ✅ Example Commands

```bash
python inventory.py --output json
```

---

# ✅ Key Concepts Practiced

- Multi-threading
- AWS multi-region APIs
- Cost estimation
- Resource inventory management

---

# 📂 Example Structure

```text
aws-resource-inventory/
│
├── inventory.py
├── pricing.py
├── output_formatter.py
├── requirements.txt
└── README.md
```

---

# 📦 PROJECT 5 — EC2 LIFECYCLE MANAGER

## 🎯 Objective
Automate EC2 lifecycle operations safely and efficiently.

---

# ✅ Features

- Start EC2 instances
- Stop EC2 instances
- Reboot instances
- Terminate instances
- Dry-run mode
- Tag-based operations
- Scheduling support
- Confirmation prompts

---

# ✅ Technologies Used

- boto3
- argparse
- PyYAML

---

# ✅ Example Commands

```bash
python ec2_lifecycle.py stop \
    --tag Environment=dev \
    --region us-east-1
```

---

# ✅ Safety Features

- `--dry-run`
- Confirmation prompts
- Exception handling

---

# ✅ Key Concepts Practiced

- Infrastructure automation
- Safe cloud operations
- AWS EC2 lifecycle APIs
- Tag filtering

---

# 📂 Example Structure

```text
ec2-lifecycle-manager/
│
├── ec2_lifecycle.py
├── schedules.yaml
├── logger.py
└── README.md
```

---

# 📦 PROJECT 6 — S3 BACKUP & SYNC TOOL

## 🎯 Objective
Build a secure and automated S3 backup solution.

---

# ✅ Features

- Upload backups
- Download backups
- Incremental sync
- MD5 checksum comparison
- Lifecycle policy automation
- Encryption support
- Timestamped backups

---

# ✅ Technologies Used

- boto3
- hashlib
- argparse
- PyYAML

---

# ✅ Example Commands

```bash
python s3_backup.py upload \
    --bucket my-backup-bucket \
    --source ./project
```

---

# ✅ Lifecycle Policies

- 30 days → S3 IA
- 90 days → Glacier
- 365 days → Delete

---

# ✅ Security Features

```python
ServerSideEncryption='AES256'
```

---

# ✅ Key Concepts Practiced

- Backup automation
- Incremental uploads
- S3 lifecycle management
- Encryption & storage optimization

---

# 📂 Example Structure

```text
s3-backup-tool/
│
├── s3_backup.py
├── config.yaml
├── logger.py
├── requirements.txt
└── README.md
```

---

# 📦 PROJECT 7 — MASTER PORTFOLIO REPOSITORY

## 🎯 Objective
Combine all AWS automation projects into a single professional portfolio repository.

---

# ✅ Repository Name

```text
aws-python-tools
```

---

# ✅ Features

- Organized subfolders
- Shared utilities
- Common logging system
- Unified configuration management
- Professional documentation

---

# ✅ Repository Structure

```text
aws-python-tools/
│
├── ec2/
│   ├── ec2_tool.py
│   ├── ec2_lifecycle.py
│
├── s3/
│   ├── s3_backup.py
│
├── utils/
│   ├── logger.py
│   ├── config_loader.py
│
├── config/
│   ├── config.yaml
│
├── requirements.txt
├── README.md
```

---

# ✅ Key Concepts Practiced

- Project architecture
- Portfolio organization
- Code standardization
- Documentation practices

---

# 🧠 WEEK 9 SKILLS GAINED

## Python Skills
- argparse
- logging
- YAML parsing
- threading
- file handling
- JSON formatting

---

## AWS Skills
- EC2 automation
- S3 automation
- RDS inventory
- Lambda inventory
- AWS cost awareness

---

## DevOps Skills
- Infrastructure automation
- CLI tooling
- Configuration management
- Logging & monitoring
- Safe operations

---

# 🔥 MAJOR ACHIEVEMENT

By the end of Week 9, built:
- Multiple production-style AWS tools
- Portfolio-ready GitHub projects
- Reusable automation utilities
- Real cloud engineering workflows

---

# 💭 FINAL REFLECTION

Week 9 transformed Python knowledge into practical cloud engineering skills.

Built confidence in:
- AWS automation
- Production scripting
- Tool design
- Professional project organization

Learned how real cloud engineers:
- Automate repetitive tasks
- Structure projects professionally
- Build reusable tooling
- Manage infrastructure safely

---

**Week 9 Projects:** Complete ✅  
**Days Covered:** 57–63 / 1000 🚀