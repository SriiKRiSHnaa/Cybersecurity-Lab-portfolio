# Bandit Level 07

## Objective

Retrieve the password for **Bandit Level 8**. The password is stored in the file `data.txt` next to the word `millionth`.

---

## Difficulty

⭐⭐ Beginner

---

## Learning Objectives

- Learn how to search for text inside files.
- Understand the basic usage of the `grep` command.
- Distinguish between searching for files and searching within files.

---

## Challenge Description

The challenge provided the filename (`data.txt`) and a keyword (`millionth`).

Instead of manually reading the entire file, the `grep` command was used to search for the specific word.

---

## Commands Used

### Connect to the Bandit server

```bash
ssh bandit7@bandit.labs.overthewire.org -p 2220
```

### Verify current user

```bash
whoami
```

### Search for the keyword

```bash
grep millionth data.txt
```

---

## Command Explanation

### `grep`

Searches for text matching a pattern inside one or more files.

### `millionth`

The search pattern.

### `data.txt`

The file being searched.

---

## Solution

The password was located by searching for the word `millionth` inside `data.txt`:

```bash
grep millionth data.txt
```

The matching line contained the password for Bandit Level 8.

---

## Skills Learned

- Searching text inside files
- Basic usage of `grep`
- Understanding command syntax

---

## Key Takeaways

- `grep` searches **inside** files, not for files.
- A simple `grep` command follows the format:

```text
grep PATTERN FILE
```

- Reading the challenge carefully helps identify the search pattern and the file.

---

## Real-World Relevance

`grep` is one of the most frequently used commands in cybersecurity.

It is commonly used to:

- Search log files
- Find error messages
- Locate IP addresses
- Search configuration files
- Detect indicators of compromise

---

## References

- OverTheWire Bandit
- `man grep`

---

## Result

✅ Successfully retrieved the password for **Bandit Level 8**.
