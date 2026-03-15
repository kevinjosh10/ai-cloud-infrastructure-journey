# WEEK 2: LINUX FUNDAMENTALS I

## Focus
Master the Linux file system, essential commands, file permissions, and shell basics.

Linux is the backbone of modern cloud infrastructure.  
This week builds the core terminal skills required for DevOps, Cloud Engineering, and Infrastructure roles.

---

# Resources

• Linux Journey — https://linuxjourney.com  
• The Linux Command Line Book — https://linuxcommand.org  
• OverTheWire Bandit — https://overthewire.org/wargames/bandit  

---

# Day 8: Linux File System Hierarchy

### Topics Covered

36. Study the Linux directory structure:

```
/
├── home
├── etc
├── var
├── tmp
├── usr
├── bin
├── sbin
├── opt
└── mnt
```

Understand the purpose of each directory.

| Directory | Purpose |
|------|------|
| `/` | Root directory |
| `/home` | User home directories |
| `/etc` | System configuration files |
| `/var` | Logs and variable data |
| `/tmp` | Temporary files |
| `/usr` | Installed applications |
| `/bin` | Essential command binaries |
| `/sbin` | System administration binaries |
| `/opt` | Optional software packages |
| `/mnt` | Mounted storage devices |

37. Open a terminal (WSL on Windows, or Terminal on Mac/Linux) and practice navigation commands:

```
cd
ls
pwd
```

38. Understand **absolute vs relative paths**

Example:

Absolute path

```
/home/kevin/documents
```

Relative path

```
../documents
```

39. Practice navigation:

Navigate to system directories:

```
cd /etc
ls

cd /var/log
ls
```

40. Create your **first Linux cheat sheet** documenting every command learned.

---

# Day 9: File & Directory Operations

### Commands Learned

41. Directory and file deletion

```
mkdir foldername
rm file.txt
rm -r directory
```

42. Copying and moving files

```
cp source destination
mv source destination
```

Example

```
cp file.txt backup.txt
mv file.txt documents/
```

43. File creation and viewing

```
touch filename
cat filename
less filename
```

Example

```
touch notes.txt
cat notes.txt
less notes.txt
```

44. Practice exercise

Create a directory structure:

```
project/
├── folder1
├── folder2
└── folder3
```

Create 5 files and practice copying and moving them.

45. Learn **wildcards**

```
ls *.txt
rm file*
```

Examples

```
ls *.txt
rm file*
```

---

# Day 10: File Permissions

### Understanding Permission Notation

Example permission string

```
rwxr-xr--
```

Meaning:

| Symbol | Meaning |
|------|------|
| r | read |
| w | write |
| x | execute |

Numeric values:

| Permission | Value |
|------|------|
| r | 4 |
| w | 2 |
| x | 1 |

46. Understand how permissions work for:

- owner
- group
- others

---

### `chmod`

Change file permissions.

Example:

```
chmod 755 script.sh
```

Meaning

```
Owner  → rwx
Group  → r-x
Others → r-x
```

---

### `chown`

Change file owner and group.

Example:

```
chown kevin:staff file.txt
```

---

### Practice

49. Create a script file:

```
touch script.sh
chmod 755 script.sh
ls -la
```

Verify the executable permission.

50. Learn about advanced permission concepts:

- setuid
- setgid

(Read in Linux Journey permissions section.)

---

# Day 11: Text Processing Commands

51. `grep` — search text patterns

Example

```
grep "error" logfile.txt
```

---

52. Advanced grep options

```
grep -r
grep -i
grep -n
```

Examples

```
grep -r error logs/
grep -i error logfile.txt
grep -n error logfile.txt
```

---

53. File preview commands

```
head logfile.txt
tail logfile.txt
tail -f logfile.txt
```

Used heavily for **log monitoring**.

---

54. Counting and sorting text

```
wc -l logfile.txt
sort names.txt
uniq names.txt
```

---

55. Practice

Download a sample log file and run:

```
grep ERROR logfile.txt
grep ERROR logfile.txt | wc -l
```

---

# Day 12: Pipes, Redirection & Shell Basics

### Pipes

56. Combine commands using pipes:

```
command1 | command2
```

Example:

```
ls -la | grep ".txt"
```

---

57. Practice pipeline

```
ls -la | grep ".txt" | wc -l
```

Counts `.txt` files in a directory.

---

### Redirection

58. Learn output redirection

Overwrite file

```
>
```

Append

```
>>
```

Input

```
<
```

Redirect errors

```
2>
```

Examples

```
echo hello > file.txt
echo world >> file.txt
cat < file.txt
ls wrongdir 2> errors.log
```

---

### Environment Variables

59. View variables

```
echo $PATH
echo $HOME
```

Create a variable

```
export MY_VAR="hello"
```

---

### Shell Startup Files

60. Understand shell configuration files

```
.bashrc
.bash_profile
.profile
```

These control terminal startup behavior.

---

# Day 13: Searching & Finding Files

61. Learn `find`

Example

```
find /home -name "*.py"
```

Searches for Python files.

---

62. Use conditions

```
-type f
-type d
-mtime -7
```

Examples

```
find . -type f
find . -type d
find . -mtime -7
```

---

63. Learn fast search tools

```
locate filename
which command
```

Examples

```
locate file.txt
which python
```

---

64. Learn `xargs`

Example

```
find . -name "*.log" | xargs rm
```

Deletes all `.log` files found.

---

65. Start the **OverTheWire Bandit** game.

Goal:

Complete **Level 0 → Level 5**.

This reinforces Linux fundamentals through challenges.

---

# Day 14: Week 2 Review & Cheat Sheet

66. Review all commands learned:

- navigation
- file operations
- permissions
- text processing
- pipes
- searching

---

67. Complete your **Linux cheat sheet**

It should now contain **30+ commands with examples**.

---

68. Complete **Bandit Levels 0–5**

Practice:

- file navigation
- hidden files
- passwords
- command usage

---

69. Update your **Anki flashcards**

Create **20 new cards** covering:

- Linux commands
- permissions
- pipelines
- search commands

---

70. Commit your Linux cheat sheet to GitHub

Example commit:

```
git add .
git commit -m "Week 2 Linux fundamentals cheat sheet"
git push
```

Include a **README explaining what you learned.**

---

# Week 2 Outcome

By the end of this week you should be comfortable with:

- Linux filesystem structure
- Terminal navigation
- File operations
- Permissions management
- Text processing tools
- Pipes and redirection
- File searching techniques
- Basic log analysis

These skills form the **foundation for DevOps, Cloud Engineering, and Infrastructure roles.**

---

# Progress

```
Week 2 Completed
Day 14 / 1000
```

Linux fundamentals established.