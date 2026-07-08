# Bandit Level 08

## Objective

Retrieve the password for **Bandit Level 9**. The password is stored in the file `data.txt` and is the **only line that occurs exactly once**.

---

## Difficulty

⭐⭐ Beginner

---

## Learning Objectives

- Learn how to sort text using the `sort` command.
- Understand how the `uniq` command works.
- Learn how to combine commands using pipes (`|`).
- Identify unique lines in a text file.

---

## Challenge Description

The file `data.txt` contained many repeated lines.

The challenge required identifying the only line that appeared exactly once.

Since `uniq` only detects adjacent duplicate lines, the file had to be sorted before using `uniq`.

---

## Commands Used

### Connect to the Bandit server

```bash
ssh bandit8@bandit.labs.overthewire.org -p 2220
```

### Verify current user

```bash
whoami
```

### Find the unique line

```bash
sort data.txt | uniq -u
```

---

## Command Explanation

### `sort`

Sorts the lines in a file alphabetically.

Sorting places identical lines next to each other.

---

### `uniq`

Filters duplicate adjacent lines.

### `-u`

Displays only lines that appear exactly once.

---

### `|` (Pipe)

Passes the output of one command as the input to another command.

---

## Solution

The file was sorted first:

```bash
sort data.txt
```

The sorted output was then passed to `uniq`:

```bash
sort data.txt | uniq -u
```

This displayed the only line that appeared exactly once, which was the password for Bandit Level 9.

---

## Skills Learned

- Sorting text
- Finding unique lines
- Using pipes
- Combining Linux commands

---

## Key Takeaways

- `uniq` only compares adjacent lines.
- Sorting before using `uniq` is often necessary.
- Pipes make it easy to combine multiple commands.
- Linux commands are designed to work together.

---

## Real-World Relevance

System administrators and security professionals commonly use pipelines such as:

```bash
cat logfile | grep "ERROR"
```

```bash
ps aux | grep apache
```

```bash
sort users.txt | uniq
```

Pipelines are fundamental to log analysis, automation, scripting, and incident response.

---

## References

- OverTheWire Bandit
- `man sort`
- `man uniq`

---

## Result

✅ Successfully retrieved the password for **Bandit Level 9**.
