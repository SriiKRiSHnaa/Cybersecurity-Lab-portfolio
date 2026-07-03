# Bandit Level 06

## Objective

Retrieve the password for **Bandit Level 7**. The password is stored somewhere on the server in a file with the following properties:

- Owned by user `bandit7`
- Owned by group `bandit6`
- Exactly **33 bytes** in size

---

## Difficulty

⭐⭐ Beginner

---

## Learning Objectives

- Search the entire filesystem using the `find` command.
- Filter files by owner, group, and size.
- Understand Linux file ownership.
- Learn about permission errors when searching system directories.

---

## Challenge Description

Unlike previous levels, the password file was not located in the home directory.

The challenge required searching the entire filesystem for a file matching three specific properties: owner, group, and file size.

---

## Commands Used

### Connect to the Bandit server

```bash
ssh bandit6@bandit.labs.overthewire.org -p 2220
```

### Verify current user

```bash
whoami
```

### Search the filesystem

```bash
find . -user bandit7 -group bandit6 -size 33c
```

Output:

```text
./var/lib/dpkg/info/bandit7.password
```

### Read the password

```bash
cat ./var/lib/dpkg/info/bandit7.password
```

---

## Command Explanation

### `find`

Searches recursively for files and directories.

### `.`

Starts searching from the current directory.

In this challenge, the current directory was the root (`/`).

### `-user bandit7`

Filters files owned by the user `bandit7`.

### `-group bandit6`

Filters files belonging to the group `bandit6`.

### `-size 33c`

Filters files that are exactly **33 bytes** in size.

The suffix `c` specifies bytes.

### `cat`

Displays the contents of a file.

---

## Solution

The following command searched the filesystem using all three challenge requirements:

```bash
find . -user bandit7 -group bandit6 -size 33c
```

The matching file was:

```text
./var/lib/dpkg/info/bandit7.password
```

The password was retrieved with:

```bash
cat ./var/lib/dpkg/info/bandit7.password
```

---

## Skills Learned

- Searching the filesystem
- Filtering by owner
- Filtering by group
- Filtering by file size
- Understanding Linux ownership
- Handling permission errors

---

## Key Takeaways

- The `find` command can combine multiple search conditions.
- Linux file ownership consists of both a user and a group.
- Permission errors are expected when searching the entire filesystem as a non-root user.
- Combining multiple filters greatly reduces search time.

---

## Real-World Relevance

System administrators and security professionals frequently use `find` to locate:

- Sensitive configuration files
- SSH keys
- World-writable files
- SUID binaries
- Files owned by specific users
- Incident artifacts

Searching by metadata is often much faster than searching by filename alone.

---

## References

- OverTheWire Bandit
- `man find`
- `man cat`

---

## Result

✅ Successfully retrieved the password for **Bandit Level 7**.
