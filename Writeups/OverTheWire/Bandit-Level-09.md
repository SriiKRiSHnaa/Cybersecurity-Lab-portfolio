# Bandit Level 09

## Objective

Retrieve the password for **Bandit Level 10**. The password is stored in the file `data.txt` in one of the human-readable strings, preceded by several `=` characters.

---

## Difficulty

⭐⭐ Beginner

---

## Learning Objectives

- Learn how to extract readable text from binary files.
- Understand the purpose of the `strings` command.
- Combine `strings` with `grep` using pipes.
- Search extracted text for specific patterns.

---

## Challenge Description

The file `data.txt` contained binary data mixed with human-readable text.

Instead of displaying the binary file directly, the `strings` command was used to extract printable text.

The extracted text was then searched using `grep` to locate the password.

---

## Commands Used

### Connect to the Bandit server

```bash
ssh bandit9@bandit.labs.overthewire.org -p 2220
```

### Verify current user

```bash
whoami
```

### Extract readable strings and search for `=`

```bash
strings data.txt | grep "="
```

---

## Command Explanation

### `strings`

Extracts printable (human-readable) strings from binary files.

---

### `grep "="`

Searches for lines containing the `=` character.

---

### `|` (Pipe)

Passes the output of `strings` directly to `grep`.

---

## Solution

The binary file was processed with:

```bash
strings data.txt
```

The extracted strings were then filtered:

```bash
strings data.txt | grep "="
```

The matching line containing the password was identified and used to log in to Bandit Level 10.

---

## Skills Learned

- Extracting text from binary files
- Searching binary output
- Combining commands with pipes
- Pattern searching

---

## Key Takeaways

- Binary files often contain readable strings.
- The `strings` command is useful during malware analysis and reverse engineering.
- Pipelines allow multiple commands to work together efficiently.
- Broad searches can be refined after observing the results.

---

## Real-World Relevance

Security professionals frequently use `strings` when analyzing:

- Malware
- Executables
- Memory dumps
- Firmware
- Unknown binary files

It often reveals:

- URLs
- File paths
- API keys
- Debug messages
- Embedded credentials

---

## References

- OverTheWire Bandit
- `man strings`
- `man grep`

---

## Result

✅ Successfully retrieved the password for **Bandit Level 10**.
