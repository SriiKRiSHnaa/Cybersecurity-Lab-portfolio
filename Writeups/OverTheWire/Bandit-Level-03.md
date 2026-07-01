# Bandit Level 03

## Objective

Retrieve the password for **Bandit Level 4**. The password is stored in a hidden file inside the `inhere` directory.

---

## Difficulty

⭐ Beginner

---

## Learning Objectives

- Understand hidden files in Linux.
- Learn how to display hidden files using `ls -a`.
- Navigate directories using `cd`.
- Read hidden files using the `cat` command.

---

## Challenge Description

After logging into the `bandit3` account, the home directory contained a folder named `inhere`.

Listing its contents with the normal `ls` command showed no files.

After using the `-a` option with `ls`, a hidden file became visible.

---

## Commands Used

### Display current directory

```bash
pwd
```

### List files

```bash
ls
```

### Enter the directory

```bash
cd inhere
```

### Display all files (including hidden files)

```bash
ls -a
```

Output:

```text
.  ..  ...Hiding-From-You
```

### Read the hidden file

```bash
cat ...Hiding-From-You
```

---

## Command Explanation

### `pwd`

Displays the current working directory.

---

### `ls`

Lists visible files and directories.

---

### `cd`

Changes the current working directory.

---

### `ls -a`

Displays **all** files, including hidden files.

Files beginning with a dot (`.`) are hidden by default in Linux.

---

### `cat`

Displays the contents of a file.

---

## Solution

The hidden file became visible after running:

```bash
ls -a
```

The password was retrieved by reading the hidden file:

```bash
cat ...Hiding-From-You
```

---

## Skills Learned

- Navigating directories
- Working with hidden files
- Using `ls -a`
- Reading hidden files
- Understanding Linux file visibility

---

## Key Takeaways

- Files beginning with `.` are hidden by default.
- `ls` does not display hidden files.
- `ls -a` displays every file in a directory.
- Hidden files are commonly used for configuration and application settings.

Examples:

```text
.bashrc
.git
.ssh
.profile
.config
```

Cybersecurity professionals frequently inspect hidden files because they often contain configuration data, credentials, SSH keys, or application settings.

---

## References

- OverTheWire Bandit
- `man ls`
- `man cat`

---

## Result

✅ Successfully retrieved the password for **Bandit Level 4**.
