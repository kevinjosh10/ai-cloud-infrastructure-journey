# Linux File Permissions Cheat Sheet 🔐

A quick reference guide for understanding and managing **Linux file permissions**, commonly used by system administrators, DevOps engineers, and cloud engineers.

---

# 📂 Viewing File Permissions

Command:

```bash
ls -la
```

Example output:

```
-rwxr-xr-- 1 kevin staff 120 Mar 11 script.sh
```

Breakdown:

| Section | Meaning |
|------|------|
| `-` | File type |
| `rwx` | Owner permissions |
| `r-x` | Group permissions |
| `r--` | Others permissions |
| `kevin` | Owner |
| `staff` | Group |
| `120` | File size |
| `Mar 11` | Last modified date |
| `script.sh` | File name |

---

# 🔑 Permission Types

| Symbol | Meaning | Value |
|------|------|------|
| `r` | Read | 4 |
| `w` | Write | 2 |
| `x` | Execute | 1 |
| `-` | No permission | 0 |

Example permission:

```
rwxr-xr--
```

Split into:

```
Owner   Group   Others
rwx     r-x     r--
```

---

# 🔢 Numeric Permission System

Permissions can also be represented with numbers.

| Permission | Calculation | Number |
|-----------|------------|--------|
| `rwx` | 4 + 2 + 1 | 7 |
| `rw-` | 4 + 2 | 6 |
| `r-x` | 4 + 1 | 5 |
| `r--` | 4 | 4 |

Example:

```
rwxr-xr-x
```

Numeric equivalent:

```
755
```

---

# ⚙️ chmod – Change File Permissions

Syntax:

```bash
chmod permission filename
```

Example:

```bash
chmod 755 script.sh
```

Meaning:

| User | Permission |
|------|-----------|
| Owner | rwx |
| Group | r-x |
| Others | r-x |

---

# 📊 Common Permission Values

| Permission | Meaning |
|------|------|
| `777` | Full access for everyone (not secure) |
| `755` | Owner full access, others read + execute |
| `644` | Owner read/write, others read |
| `600` | Private file (owner only) |
| `400` | Read-only for owner |

Examples:

```bash
chmod 644 file.txt
chmod 755 script.sh
chmod 600 private.key
```

---

# 👤 chown – Change File Owner

Syntax:

```bash
chown user:group filename
```

Example:

```bash
chown kevin:staff file.txt
```

Verify:

```bash
ls -la
```

Example output:

```
-rw-r--r-- 1 kevin staff file.txt
```

---

# 🧾 Creating an Executable Script

### Step 1 – Create script

```bash
nano script.sh
```

Add:

```bash
#!/bin/bash
echo "Hello Linux"
```

---

### Step 2 – Make executable

```bash
chmod 755 script.sh
```

---

### Step 3 – Run script

```bash
./script.sh
```

Output:

```
Hello Linux
```

---

# ⭐ Special Permissions

## setuid

Allows a program to run with the **owner's privileges**.

Example:

```
-rwsr-xr-x
```

`s` indicates **setuid**.

Common example:

```
/usr/bin/passwd
```

---

## setgid

When applied to directories, new files inherit the **directory’s group**.

Example:

```
drwxr-sr-x
```

Useful for **shared project directories**.

---

# 🧪 Quick Practice Commands

Create practice directory:

```bash
mkdir permissions-practice
cd permissions-practice
```

Create file:

```bash
touch test.txt
```

Check permissions:

```bash
ls -la
```

Change permissions:

```bash
chmod 644 test.txt
```

Create executable script:

```bash
nano script.sh
chmod 755 script.sh
./script.sh
```

---

# ☁️ Cloud Engineering Relevance

Linux permissions are critical for:

- SSH key security
- Server configuration
- Docker containers
- Deployment scripts
- DevOps pipelines
- Infrastructure automation

Example:

```bash
chmod 400 key.pem
```

SSH will refuse connections if the key is too open.

---

# 🚀 Quick Memory Guide

```
r = 4
w = 2
x = 1
```

Common combos:

```
755 → rwxr-xr-x
644 → rw-r--r--
600 → rw-------
```

Commands:

```
ls -la   → view permissions
chmod    → change permissions
chown    → change owner
```

---

✅ **Tip:** Proper permission management is essential for **Linux security, cloud infrastructure, and DevOps workflows.**