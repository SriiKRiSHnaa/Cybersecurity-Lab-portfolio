# Bandit Level 05

## Objective

Retrieve the password for **Bandit Level 6**. The password is stored in a file that satisfies all of the following conditions:

- Human-readable
- Exactly **1033 bytes**
- Not executable

---

## Difficulty

⭐⭐ Beginner

---

## Learning Objectives

- Learn how to search for files using the `find` command.
- Filter files by type and size.
- Verify file type using the `file` command.
- Check file permissions with `ls -l`.
- Read the correct file using `cat`.

---

## Challenge Description

The `inhere` directory contained multiple subdirectories and many files. Instead of manually checking every file, I used the `find` command to search for files matching the required size.

After locating the candidate file, I verified that it was human-readable and not executable before reading its contents.

---

## Commands Used

### Connect to the Bandit server

```bash
ssh bandit5@bandit.labs.overthewire.org -p 2220
```

### Verify current user

```bash
whoami
```

### Enter the challenge directory

```bash
cd inhere
```

### Search for files that are exactly 1033 bytes

```bash
find . -type f -size 1033c
```

Output:

```text
./maybehere07/.file2
```

### Verify the file type

```bash
file ./maybehere07/.file2
```

### Check file permissions

```bash
ls -l ./maybehere07/.file2
```

### Read the file

```bash
cat ./maybehere07/.file2
```

---

## Command Explanation

### `find`

Searches for files and directories.

### `.`

Starts the search from the current directory.

### `-type f`

Searches only for regular files.

### `-size 1033c`

Searches for files that are exactly **1033 bytes**.

The suffix `c` means bytes.

### `file`

Determines the file type based on its contents.

### `ls -l`

Displays detailed file information, including permissions.

### `cat`

Displays the contents of a file.

---

## Solution

The following command located the file matching the required size:

```bash
find . -type f -size 1033c
```

The result was:

```text
./maybehere07/.file2
```

The file type was verified using:

```bash
file ./maybehere07/.file2
```

Permissions were checked with:

```bash
ls -l ./maybehere07/.file2
```

Finally, the password was retrieved using:

```bash
cat ./maybehere07/.file2
```

---

## Skills Learned

- Searching files recursively
- Using the `find` command
- Filtering by file type
- Filtering by file size
- Checking file permissions
- Verifying file types

---

## Key Takeaways

- `find` is one of the most powerful Linux commands.
- Searching by file properties is much faster than manually inspecting files.
- Always verify file type before opening unknown files.
- File permissions provide useful information about how a file can be accessed.

---

## Real-World Relevance

Security professionals frequently use the `find` command during:

- Penetration testing
- Digital forensics
- Incident response
- System administration

Examples include searching for:

- World-writable files
- SUID binaries
- SSH keys
- Log files
- Configuration files
- Large or recently modified files

---

## References

- OverTheWire Bandit
- `man find`
- `man file`
- `man ls`

---

## Result

✅ Successfully retrieved the password for **Bandit Level 6**.
