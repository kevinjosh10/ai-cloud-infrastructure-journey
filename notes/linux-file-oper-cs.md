# Linux File & Directory Operations — Cheat Sheet 🐧

Quick reference for essential Linux commands used to manage files and directories.

---

# 📁 Directory Operations

## Create Directory

```bash
mkdir folder_name
```

Example:

```bash
mkdir projects
```

---

## Create Multiple Directories

```bash
mkdir folder1 folder2 folder3
```

---

## Create Nested Directories

```bash
mkdir -p parent/child/grandchild
```

Example:

```bash
mkdir -p cloud/aws/projects
```

---

# 🗑️ Delete Operations

## Delete File

```bash
rm filename
```

Example:

```bash
rm notes.txt
```

---

## Delete Directory

```bash
rm -r foldername
```

Example:

```bash
rm -r old_project
```

---

## Force Delete (Use Carefully)

```bash
rm -rf foldername
```

Options:

```
-r   recursive
-f   force delete
```

---

# 📦 Copy Operations

## Copy File

```bash
cp source destination
```

Example:

```bash
cp file.txt backup.txt
```

---

## Copy File to Directory

```bash
cp file.txt folder/
```

Example:

```bash
cp notes.txt documents/
```

---

## Copy Directory

```bash
cp -r source_directory destination_directory
```

Example:

```bash
cp -r project project_backup
```

---

# 🚚 Move & Rename

## Move File

```bash
mv file.txt folder/
```

Example:

```bash
mv notes.txt documents/
```

---

## Rename File

```bash
mv oldname.txt newname.txt
```

Example:

```bash
mv report.txt final_report.txt
```

---

# 📄 File Creation

## Create Empty File

```bash
touch filename
```

Example:

```bash
touch notes.txt
```

---

## Create Multiple Files

```bash
touch file1.txt file2.txt file3.txt
```

---

# 📖 View File Contents

## Display File Content

```bash
cat filename
```

Example:

```bash
cat notes.txt
```

---

# 📜 Read Large Files

## Scroll Through File

```bash
less filename
```

Example:

```bash
less server.log
```

Navigation inside `less`:

```
↑ ↓   scroll
space next page
q     quit
```

---

# ⭐ Wildcards

Wildcards allow operations on multiple files.

---

## List Files by Extension

```bash
ls *.txt
```

Lists all `.txt` files.

---

## Delete Multiple Files

```bash
rm file*
```

Deletes files starting with **file**.

Example matches:

```
file1.txt
file2.txt
file_backup.txt
```

---

# 🧪 Quick Practice Commands

```bash
mkdir linux-practice
cd linux-practice

mkdir folder1 folder2 folder3

touch file1.txt file2.txt file3.txt file4.txt file5.txt

cp file1.txt folder1/
cp file2.txt folder2/

mv file3.txt folder3/

mv file4.txt renamed.txt

ls *.txt

rm file5.txt

rm -r folder3
```

---

# ☁️ Real Cloud Engineering Example

Typical server workflow:

```bash
mkdir my-app
cd my-app

touch config.yaml
cp config.yaml config_backup.yaml

less server.log

rm *.tmp
```

Used frequently when working with:

- AWS EC2 servers
- application deployments
- configuration files
- server logs
- backup management

---

# 🧠 Key Commands Summary

| Command | Purpose |
|------|------|
| `mkdir` | Create directories |
| `rm` | Delete files |
| `rm -r` | Delete directories |
| `rm -rf` | Force delete |
| `cp` | Copy files or folders |
| `mv` | Move or rename |
| `touch` | Create files |
| `cat` | Show file content |
| `less` | Scroll large files |
| `*` | Wildcard |

---

🚀 Part of the **AI + Cloud Infrastructure Engineering Journey**