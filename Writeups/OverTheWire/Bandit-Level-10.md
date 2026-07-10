# Bandit Level 10

## Objective

Retrieve the password for **Bandit Level 11**. The password is stored in the file `data.txt`, which contains Base64 encoded data.

---

## Difficulty

⭐ Beginner

---

## Learning Objectives

- Understand the difference between encoding and encryption.
- Learn how to decode Base64 encoded data.
- Use the `base64` command-line utility.

---

## Challenge Description

The challenge file `data.txt` contained Base64 encoded text.

Since Base64 is an encoding format rather than encryption, the data could be decoded directly using the Linux `base64` utility.

---

## Commands Used

### Connect to the Bandit server

```bash
ssh bandit10@bandit.labs.overthewire.org -p 2220
```

### Verify current user

```bash
whoami
```

### Decode the Base64 data

```bash
base64 -d data.txt
```

---

## Command Explanation

### `base64`

Encodes or decodes data using the Base64 encoding scheme.

### `-d`

Tells the `base64` command to decode the input instead of encoding it.

### `data.txt`

The file containing the Base64 encoded text.

---

## Solution

The password was retrieved by decoding the contents of `data.txt`:

```bash
base64 -d data.txt
```

The decoded output contained the password for Bandit Level 11.

---

## Skills Learned

- Identifying Base64 encoded data
- Decoding Base64 using Linux
- Understanding encoding vs. encryption

---

## Key Takeaways

- Base64 is **encoding**, not encryption.
- Encoded data can be reversed without a secret key.
- The `base64` utility is commonly used in Linux for encoding and decoding data.

---

## Real-World Relevance

Base64 is frequently encountered in:

- JWT (JSON Web Tokens)
- HTTP Basic Authentication
- Email attachments (MIME)
- APIs
- Malware analysis
- Capture The Flag (CTF) challenges

Recognizing Base64 encoded data is a useful skill for security professionals.

---

## References

- OverTheWire Bandit
- `man base64`

---

## Result

✅ Successfully retrieved the password for **Bandit Level 11**.
