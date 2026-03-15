# Linux Fundamentals Cheat Sheet (Week 2)

A comprehensive cheat sheet covering Linux fundamentals learned during Week 2 of the **1000 Day AI Cloud Infrastructure Engineer Journey**.

Topics Covered:
- Linux filesystem hierarchy
- Navigation commands
- File & directory operations
- File viewing
- Wildcards
- Permissions
- Text processing
- Pipes & redirection
- Environment variables
- File searching
- Command combinations used in real systems

---

# 1. Linux File System Hierarchy

Linux organizes files using a structured directory tree.

| Directory | Purpose |
|------|------|
| `/` | Root directory (top of the filesystem) |
| `/home` | User home directories |
| `/etc` | System configuration files |
| `/var` | Logs, variable data |
| `/tmp` | Temporary files |
| `/usr` | Installed applications and utilities |
| `/bin` | Essential command binaries |
| `/sbin` | System administration binaries |
| `/opt` | Optional software packages |
| `/mnt` | Mounted drives |

Example:

```
/
├── home
│   └── kevin
├── etc
├── var
│   └── log
```

---

# 2. Navigation Commands

## `pwd`
Print Working Directory.

Shows your current location.

Example:

```bash
pwd
```

Output:

```
/home/kevin/projects
```

---

## `ls`

Lists files in the current directory.

```bash
ls
```

Example output:

```
file.txt
script.sh
folder
```

---

## `ls -la`

Lists **all files including hidden ones** with details.

```bash
ls -la
```

Output example:

```
drwxr-xr-x 2 kevin kevin 4096 Mar 10 project
-rw-r--r-- 1 kevin kevin  200 Mar 10 file.txt
```

Details shown:

- permissions
- owner
- group
- size
- modification date

---

## `cd`

Change directory.

```bash
cd /home
```

---

## `cd ..`

Move one directory up.

```bash
cd ..
```

---

## `cd ~`

Go to your home directory.

```bash
cd ~
```

---

# 3. Absolute vs Relative Paths

Absolute path starts from root.

Example:

```
/home/kevin/documents
```

Relative path starts from current location.

Example:

```
../documents
```

---

# 4. File & Directory Operations

## `mkdir`

Create a directory.

```bash
mkdir project1
```

Creates:

```
project1/
```

---

## `touch`

Create an empty file.

```bash
touch file.txt
```

---

## `cp`

Copy files.

```bash
cp file.txt backup.txt
```

Result:

```
file.txt
backup.txt
```

---

## `mv`

Move or rename files.

Rename example:

```bash
mv file.txt newfile.txt
```

Move example:

```bash
mv file.txt folder/
```

---

## `rm`

Delete a file.

```bash
rm file.txt
```

---

## `rm -r`

Delete directory recursively.

```bash
rm -r project1
```

---

# 5. File Viewing Commands

## `cat`

Display file contents.

```bash
cat file.txt
```

Output:

```
Hello world
```

---

## `less`

Scroll through large files.

```bash
less logfile.txt
```

Controls:

- `q` → quit
- arrow keys → scroll

---

## `head`

Show first 10 lines.

```bash
head logfile.txt
```

---

## `tail`

Show last 10 lines.

```bash
tail logfile.txt
```

---

## `tail -f`

Follow file updates live.

```bash
tail -f server.log
```

Used for **monitoring logs in real time**.

---

# 6. Wildcards

## `*`

Matches any characters.

Example:

```bash
ls *.txt
```

Lists all `.txt` files.

---

Example:

```bash
rm file*
```

Deletes:

```
file1
file2
file_backup
```

---

# 7. File Permissions

Example permission string:

```
rwxr-xr--
```

Meaning:

| Section | Meaning |
|------|------|
| rwx | Owner permissions |
| r-x | Group permissions |
| r-- | Others permissions |

Permission values:

| Permission | Value |
|------|------|
| Read | 4 |
| Write | 2 |
| Execute | 1 |

---

## `chmod`

Change permissions.

Example:

```bash
chmod 755 script.sh
```

Meaning:

```
Owner = rwx
Group = r-x
Others = r-x
```

---

## `chown`

Change file owner.

```bash
chown kevin:staff file.txt
```

---

# 8. Text Processing Commands

## `grep`

Search text inside files.

```bash
grep "error" logfile.txt
```

---

## `grep -i`

Case insensitive search.

```bash
grep -i error logfile.txt
```

Matches:

```
error
ERROR
Error
```

---

## `grep -n`

Show line numbers.

```bash
grep -n error logfile.txt
```

Output:

```
24:error occurred
78:error occurred
```

---

## `wc -l`

Count lines.

```bash
wc -l logfile.txt
```

Example output:

```
500 logfile.txt
```

---

## `sort`

Sort lines alphabetically.

```bash
sort names.txt
```

---

## `uniq`

Remove duplicate lines.

```bash
uniq names.txt
```

---

# 9. Pipes

Pipes send output of one command into another.

Symbol:

```
|
```

Example:

```bash
ls -la | grep ".txt"
```

Flow:

```
ls output → grep filter
```

---

Example:

```bash
ls -la | grep ".txt" | wc -l
```

Meaning:

1. list files
2. filter `.txt`
3. count them

---

# 10. Redirection

## `>`

Overwrite file.

```bash
echo "hello" > file.txt
```

---

## `>>`

Append to file.

```bash
echo "world" >> file.txt
```

File becomes:

```
hello
world
```

---

## `<`

Use file as input.

```bash
cat < file.txt
```

---

## `2>`

Redirect errors.

```bash
ls wrongfolder 2> error.log
```

Error message stored in `error.log`.

---

# 11. Environment Variables

## `$PATH`

Shows directories where commands are stored.

```bash
echo $PATH
```

---

## `$HOME`

Shows user's home directory.

```bash
echo $HOME
```

Example:

```
/home/kevin
```

---

## `export`

Create environment variable.

```bash
export MY_VAR="hello"
```

Access with:

```bash
echo $MY_VAR
```

---

# 12. Searching Files

## `find`

Search files.

```bash
find . -name "*.txt"
```

---

## `-type f`

Search files only.

```bash
find . -type f
```

---

## `-type d`

Search directories only.

```bash
find . -type d
```

---

## `locate`

Fast file search using database.

```bash
locate file.txt
```

---

## `which`

Find location of commands.

```bash
which python
```

Example output:

```
/usr/bin/python
```

---

# 13. Command Combinations (Real DevOps Usage)

## Find errors in logs

```bash
grep -i error server.log
```

---

## Count errors

```bash
grep -i error server.log | wc -l
```

---

## Monitor logs live

```bash
tail -f server.log
```

---

## Find running processes

```bash
ps aux | grep nginx
```

---

## Delete multiple files

```bash
find . -name "*.log" | xargs rm
```

---

# Key Skills Learned This Week

- Linux filesystem structure
- Terminal navigation
- File management
- Permissions and ownership
- Text searching and processing
- Pipes and redirection
- File searching
- Basic log analysis

These fundamentals are **critical for DevOps, Cloud Engineering, and System Administration**.

---

# Progress

```
Week 2 Completed
Day 14 / 1000
```

Linux foundation established.