# Week 002 Recap — Linux Fundamentals I

## Overview

Week 2 focused on learning the **Linux command line and filesystem fundamentals**.  
Since most cloud infrastructure runs on Linux, mastering the terminal is a critical skill for cloud and DevOps engineers.

The goal of this week was to:

- Understand the Linux filesystem structure
- Learn essential terminal commands
- Manage files and directories
- Understand Linux permissions
- Perform text processing using command-line tools
- Combine commands using pipes
- Search files efficiently
- Practice Linux through hands-on exercises

This week built the **core operating system skills required for working with cloud servers**.

---

# Key Topics Learned

## 1. Linux File System Hierarchy

Learned how Linux organizes files using a hierarchical directory structure.

Important directories studied:

| Directory | Purpose |
|------|------|
| `/` | Root directory |
| `/home` | User home directories |
| `/etc` | System configuration files |
| `/var` | Logs and variable data |
| `/tmp` | Temporary files |
| `/usr` | Installed applications |
| `/bin` | Essential command binaries |
| `/sbin` | System administration commands |
| `/opt` | Optional software packages |
| `/mnt` | Mounted storage devices |

Understanding this structure helps engineers **locate system files, logs, and configuration settings**.

---

## 2. Terminal Navigation

Practiced basic navigation commands used in Linux.

Commands learned:

```
pwd
ls
ls -la
cd
cd ..
cd ~
```

Key concepts:

- navigating directories
- viewing files
- understanding hidden files
- exploring system folders

Also learned the difference between:

Absolute paths

```
/home/kevin/documents
```

Relative paths

```
../documents
```

---

## 3. File & Directory Management

Learned how to create, copy, move, and delete files.

Commands practiced:

```
mkdir
touch
cp
mv
rm
rm -r
```

Example workflow:

```
mkdir project
touch notes.txt
cp notes.txt backup.txt
mv notes.txt documents/
rm backup.txt
```

These commands are essential for **managing files on Linux servers**.

---

## 4. File Viewing Tools

Learned commands used to read and inspect files.

Commands:

```
cat
less
head
tail
tail -f
```

Key use cases:

- viewing file contents
- scrolling through large files
- monitoring logs in real time

Example:

```
tail -f server.log
```

This command is widely used by engineers to **monitor server activity and logs**.

---

## 5. Wildcards

Learned how to match multiple files using wildcard characters.

Example:

```
ls *.txt
```

Lists all text files.

Example:

```
rm file*
```

Deletes files starting with "file".

Wildcards make it easier to **operate on many files simultaneously**.

---

## 6. Linux File Permissions

Studied how Linux controls access to files.

Example permission string:

```
rwxr-xr--
```

Meaning:

| Section | Access |
|------|------|
| Owner | rwx |
| Group | r-x |
| Others | r-- |

Numeric permission system:

| Permission | Value |
|------|------|
| Read | 4 |
| Write | 2 |
| Execute | 1 |

Commands learned:

```
chmod
chown
```

Examples:

```
chmod 755 script.sh
chown kevin:staff file.txt
```

These commands control **who can read, modify, or execute files**.

---

## 7. Text Processing Commands

Learned powerful tools used for searching and analyzing text.

Commands studied:

```
grep
wc
sort
uniq
```

Examples:

Search for errors in logs

```
grep "error" logfile.txt
```

Count lines

```
wc -l logfile.txt
```

Sort text

```
sort names.txt
```

Remove duplicates

```
uniq names.txt
```

These tools are widely used for **log analysis and data inspection**.

---

## 8. Pipes and Command Chaining

Learned how to combine commands using pipes.

Symbol:

```
|
```

Example:

```
ls -la | grep ".txt"
```

Example pipeline:

```
ls -la | grep ".txt" | wc -l
```

This pipeline:

1. lists files
2. filters `.txt`
3. counts them

Pipes allow engineers to **build powerful command workflows**.

---

## 9. Input and Output Redirection

Learned how to redirect command output.

Commands:

```
>
>>
<
2>
```

Examples:

Overwrite file

```
echo "hello" > file.txt
```

Append to file

```
echo "world" >> file.txt
```

Redirect errors

```
ls wrongfolder 2> errors.log
```

Redirection is frequently used in **automation scripts and logging systems**.

---

## 10. Environment Variables

Studied environment variables used by the shell.

Examples:

```
echo $PATH
echo $HOME
```

Creating variables:

```
export MY_VAR="hello"
```

Environment variables store **configuration values used by programs and scripts**.

---

## 11. File Searching Tools

Learned commands used to locate files in the system.

Commands:

```
find
locate
which
```

Examples:

Find Python files

```
find /home -name "*.py"
```

Locate files quickly

```
locate file.txt
```

Find command location

```
which python
```

These commands help engineers **quickly locate files or programs on large systems**.

---

## 12. Command Automation with `xargs`

Learned how to pass output of one command as arguments to another.

Example:

```
find . -name "*.log" | xargs rm
```

This command finds and deletes all log files.

`xargs` is commonly used in **batch operations and automation scripts**.

---

## 13. Linux Practice via Bandit

Started the **OverTheWire Bandit wargame**.

Completed:

```
Level 0 → Level 5
```

These exercises reinforce:

- file navigation
- hidden files
- password retrieval
- command-line usage

Bandit helps transform theory into **practical Linux problem-solving skills**.

---

# Key Skills Developed

By the end of Week 2, the following skills were established:

- navigating Linux filesystems
- managing files and directories
- understanding permissions
- analyzing text files
- building command pipelines
- redirecting command output
- searching files efficiently
- monitoring logs

These skills are essential for:

- Cloud Engineering
- DevOps
- Infrastructure Engineering
- System Administration

---

# Outcome of Week 2

Successfully built a strong foundation in Linux terminal usage.

Completed:

- Linux filesystem exploration
- command-line file management
- permission management
- text processing tools
- pipes and redirection
- file search tools
- Linux practice challenges

This week marks the beginning of **serious command-line proficiency**.

---

# Progress

```
Week 2 Completed
Day 14 / 1000
```

Core Linux fundamentals established.

Next focus:

```
Week 3 → Linux Fundamentals II
```

Where deeper topics like **process management, networking commands, package management, and shell scripting** will be explored.

---