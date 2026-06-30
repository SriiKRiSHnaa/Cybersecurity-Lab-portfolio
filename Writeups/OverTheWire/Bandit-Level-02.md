# Bandit Level 02

## Objective

Retrieve the password for **Bandit Level 3**. The password is stored in a file whose name contains spaces and begins and ends with special characters.

---

## Difficulty

⭐ Beginner

---

## Learning Objectives

- Understand how Linux handles filenames containing spaces.
- Learn how to work with filenames that begin with special characters.
- Use relative paths to explicitly reference files.
- Practice reading files using the `cat` command.

---

## Challenge Description

After logging into the `bandit2` account, I listed the files in the home directory.

```bash
ls -l
```

Output:

```text
--spaces in this filename--
```

The filename contains spaces and also begins with `--`.

This makes it impossible to reference by typing the filename normally because the shell treats spaces as argument separators, and many commands interpret names beginning with `-` or `--` as command options.

---

## Commands Used

### List files

```bash
ls -l
```

### Display filenames with escaped special characters

```bash
ls -lb
```

Output:

```text
--spaces\ in\ this\ filename--
```

The `-b` option displays escape characters, making it easier to understand filenames containing spaces.

### Read the file

```bash
cat ./--spaces\ in\ this\ filename--
```

---

## Command Explanation

### `ls`

Lists files in the current directory.

---

### `ls -l`

Displays files in long format, including permissions, owner, size, and modification date.

---

### `ls -lb`

Displays filenames while escaping special characters such as spaces.

Example:

```text
--spaces\ in\ this\ filename--
```

The backslashes (`\`) indicate escaped spaces.

---

### `cat`

Displays the contents of a file.

---

### `./`

Represents the current directory.

Using `./` ensures that Linux interprets the filename as a file located in the current directory rather than treating it as a command-line option.

---

## Solution

The file was accessed using:

```bash
cat ./--spaces\ in\ this\ filename--
```

The command displayed the password required to log in to **Bandit Level 3**.

---

## Skills Learned

- Working with filenames containing spaces
- Escaping spaces using backslashes (`\`)
- Understanding relative paths (`./`)
- Reading files using the `cat` command
- Inspecting filenames with `ls -lb`

---

## Key Takeaways

- Linux filenames may contain spaces and special characters.
- Spaces separate command-line arguments unless escaped or quoted.
- Filenames beginning with `-` or `--` can be mistaken for command options.
- Using `./` explicitly tells Linux that the target is a file in the current directory.
- Inspect the actual system rather than relying entirely on online tutorials, as filenames and challenges may change over time.

---

## References

- OverTheWire Bandit
- Linux `cat` Manual (`man cat`)
- Linux `ls` Manual (`man ls`)

---

## Result

✅ Successfully retrieved the password for **Bandit Level 3**.

