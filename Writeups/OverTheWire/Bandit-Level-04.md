# Bandit Level 04

## Objective

Retrieve the password for **Bandit Level 5**. The password is stored in the only human-readable file inside the `inhere` directory.

---

## Difficulty

⭐ Beginner

---

## Learning Objectives

- Learn how to identify file types using the `file` command.
- Understand what "human-readable" means.
- Practice inspecting multiple files efficiently.
- Read the contents of the correct file using `cat`.

---

## Challenge Description

After logging into the `bandit4` account, the home directory contained a directory named `inhere` with multiple files.

Instead of opening every file manually, I used the `file` command to determine the type of each file and identify the only human-readable file.

---

## Commands Used

### Connect to the Bandit server

```bash
ssh bandit4@bandit.labs.overthewire.org -p 2220
```

### Verify current user

```bash
whoami
```

### Enter the challenge directory

```bash
cd inhere
```

### Identify file types

```bash
file ./*
```

Example output:

```text
./-file00: data
./-file01: data
./-file02: OpenPGP Secret Key
./-file03: data
./-file04: data
./-file05: data
./-file06: Non-ISO extended-ASCII text
./-file07: ASCII text
./-file08: data
./-file09: data
```

### Read the human-readable file

```bash
cat ./-file07
```

---

## Command Explanation

### `file`

Determines the type of a file by examining its contents rather than relying on the filename or extension.

Examples:

- ASCII text
- PNG image
- PDF document
- ELF executable
- ZIP archive

---

### `cat`

Displays the contents of a file.

---

## Solution

Using the `file` command revealed that `-file07` was the only file identified as **ASCII text**, making it the only human-readable file.

The password was retrieved with:

```bash
cat ./-file07
```

---

## Skills Learned

- Using the `file` command
- Identifying human-readable files
- Inspecting multiple files efficiently
- Reading file contents using `cat`

---

## Key Takeaways

- File extensions are not always reliable.
- The `file` command identifies files by their contents.
- Human-readable files are typically plain text files.
- The `file` command is extremely useful during malware analysis, digital forensics, and penetration testing.

---

## Real-World Relevance

Cybersecurity professionals frequently use the `file` command when analyzing unknown files.

For example, a file named:

```text
invoice.pdf
```

might actually be:

```text
PE32 executable
```

This can indicate that the file is malicious or intentionally disguised.

---

## References

- OverTheWire Bandit
- `man file`
- `man cat`

---

## Result

✅ Successfully retrieved the password for **Bandit Level 5**.
