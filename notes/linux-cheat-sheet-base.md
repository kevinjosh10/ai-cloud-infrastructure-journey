# Linux Command Cheat Sheet 🐧

A quick reference guide for commonly used Linux commands while working with servers, cloud infrastructure, and development environments.

Linux is the foundation of most modern cloud systems including **AWS EC2, Docker containers, and Kubernetes nodes**.  
This cheat sheet will continue to grow throughout the journey as more commands are learned.

---

# 🧭 Basic Navigation Commands

## 📍 Print Current Directory

```
pwd
```

Displays the full path of the current working directory.

Example output:

```
/home/kevin
```

---

## 📂 List Files and Directories

```
ls
```

Shows files and directories in the current location.

---

### Detailed File Listing

```
ls -l
```

Displays additional information:

- file permissions  
- file owner  
- file size  
- last modified time

---

### Show Hidden Files

```
ls -a
```

Displays hidden files (files starting with `.`).

Example:

```
.git
.bashrc
.profile
```

---

# 🔁 Directory Navigation

## Move into a Directory

```
cd <directory-name>
```

Example:

```
cd Documents
```

---

## Move Up One Directory

```
cd ..
```

Moves to the parent directory.

---

## Go to Home Directory

```
cd ~
```

Returns to the current user's home directory.

Example:

```
/home/kevin
```

---

## Go to Root Directory

```
cd /
```

Navigates to the top-level directory of the system.

---

# 📍 Path Types

Understanding paths is essential for navigating Linux systems.

---

## Absolute Path

A full path starting from the root directory `/`.

Example:

```
/home/kevin/documents
```

Absolute paths always begin with `/`.

---

## Relative Path

A path relative to the current working directory.

Example:

```
../documents
```

Meaning:

- `..` → move up one directory  
- then enter `documents`

---

# 📂 Important Linux Directories

Linux organizes system files into specific directories.

---

## `/`

Root directory — the top of the Linux filesystem.

All directories branch from here.

---

## `/home`

Stores personal user directories.

Example:

```
/home/kevin
/home/user
```

---

## `/etc`

Contains system configuration files.

Examples:

```
/etc/passwd
/etc/ssh
/etc/network
```

---

## `/var`

Stores variable system data that changes frequently.

Examples:

```
/var/log
/var/cache
```

---

## `/var/log`

Contains system and application logs.

Examples:

```
syslog
auth.log
kern.log
```

---

## `/usr`

Contains installed software, libraries, and utilities.

Examples:

```
/usr/bin
/usr/lib
/usr/share
```

---

## `/bin`

Essential commands required for system operation.

Examples:

```
ls
cp
mv
cat
```

---

## `/sbin`

Administrative commands used by system administrators.

Examples:

```
reboot
shutdown
fdisk
```

---

## `/tmp`

Temporary files created by applications.

These files may be automatically cleared by the system.

---

## `/opt`

Used for installing third-party software.

Example:

```
/opt/docker
/opt/google
```

---

## `/mnt`

Mount point used to attach external storage devices.

Examples:

- USB drives  
- external disks  
- network storage

---

# ⚡ Useful Tips

✔ Linux commands are **case sensitive**  
✔ Use `Tab` for **auto-completion** in the terminal  
✔ Use **arrow keys** to navigate previous commands  
✔ Combine commands to work faster

---

# 🚀 Purpose of This Cheat Sheet

This document serves as a growing reference while progressing through the **1000-day journey toward becoming an AI Cloud Infrastructure Engineer**.

Future additions will include:

- file management commands  
- process management  
- networking tools  
- package managers  
- permissions and ownership  
- shell scripting basics

---