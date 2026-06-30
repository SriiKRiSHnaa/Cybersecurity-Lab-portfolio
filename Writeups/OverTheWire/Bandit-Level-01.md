# Bandit Level 01

## Objective

Retrieve the password stored in a file named `-`.

---

## Commands Used

```bash
ls
cat ./-
```

---

## Explanation

The file was named `-`, which is normally interpreted by many Linux commands as a special argument.

Using `./-` explicitly tells Linux to use the file named `-` in the current directory.

---

## Skills Learned

- Working with special filenames
- Understanding relative paths
- Understanding command-line arguments

---

## Key Takeaway

Always consider how commands interpret arguments. When a filename conflicts with a command option, use an explicit path.

---

## Result

Successfully obtained the password for Bandit Level 2.
