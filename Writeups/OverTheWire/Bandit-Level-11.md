# Bandit Level 11

## Objective

Retrieve the password for **Bandit Level 12**. The password is stored in the file `data.txt`, where all alphabetic characters have been rotated by 13 positions (ROT13).

---

## Difficulty

⭐⭐ Beginner

---

## Learning Objectives

- Understand the ROT13 substitution cipher.
- Learn how to translate characters using the `tr` command.
- Use input redirection with Linux commands.

---

## Challenge Description

The file `data.txt` contained text encoded using the ROT13 cipher.

ROT13 replaces each letter with the letter 13 positions ahead in the alphabet. Since the English alphabet contains 26 letters, applying ROT13 twice restores the original text.

---

## Commands Used

### Connect to the Bandit server

```bash
ssh bandit11@bandit.labs.overthewire.org -p 2220
```

### Verify current user

```bash
whoami
```

### Decode the ROT13 text

```bash
tr 'A-Za-z' 'N-ZA-Mn-za-m' < data.txt
```

---

## Command Explanation

### `tr`

Translates characters from one set to another.

### `A-Za-z`

The source character set containing uppercase and lowercase English letters.

### `N-ZA-Mn-za-m`

The destination character set representing the ROT13 transformation.

### `<`

Input redirection.

The shell sends the contents of `data.txt` to the `tr` command through standard input.

---

## Solution

The encoded text was decoded using:

```bash
tr 'A-Za-z' 'N-ZA-Mn-za-m' < data.txt
```

The decoded output contained the password for Bandit Level 12.

---

## Skills Learned

- Character translation
- ROT13 cipher
- Input redirection
- Standard input (stdin)

---

## Key Takeaways

- ROT13 is a substitution cipher, not secure encryption.
- Applying ROT13 twice returns the original text.
- `tr` is useful for character-by-character transformations.
- Input redirection allows commands to read data from files via standard input.

---

## Real-World Relevance

Although ROT13 is not used for security, the `tr` command is widely used in:

- Shell scripting
- Data cleaning
- Text normalization
- Log processing
- CTF challenges

Understanding simple ciphers also provides a foundation for learning more advanced cryptographic concepts.

---

## References

- OverTheWire Bandit
- `man tr`

---

## Result

✅ Successfully retrieved the password for **Bandit Level 12**.
