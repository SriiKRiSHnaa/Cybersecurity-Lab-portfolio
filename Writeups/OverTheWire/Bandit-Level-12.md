# Bandit Level 12

## Objective

Retrieve the password for **Bandit Level 13**.

The password is stored in a file that has been converted into a hexadecimal dump and repeatedly compressed using multiple archive and compression formats.

---

## Difficulty

⭐⭐⭐⭐ Intermediate

---

## Learning Objectives

- Convert hexadecimal dumps back into binary files.
- Identify file types using the `file` command.
- Extract multiple compression formats.
- Work with tar archives.
- Apply a forensic investigation workflow.

---

## Challenge Description

The provided file `data.txt` contained a hexadecimal dump rather than the original file.

After converting the hexdump back into binary, the resulting file had multiple layers of compression and archiving.

Each layer had to be identified before selecting the appropriate extraction tool.

---

## Commands Used

### Create a working directory

```bash
mkdir /tmp/bandit12
cd /tmp/bandit12
```

### Copy the challenge file

```bash
cp /home/bandit12/data.txt .
```

### Convert the hexdump back into binary

```bash
xxd -r data.txt > data.bin
```

### Identify the file type

```bash
file data.bin
```

### Decompress gzip data

```bash
mv data.bin data.gz
gzip -d data.gz
```

### Identify the next file

```bash
file data
```

### Decompress bzip2 data

```bash
bzip2 -d data
```

### Extract tar archives

```bash
tar -tf archive
tar -xf archive
```

### Repeat

The process of:

- Running `file`
- Identifying the format
- Choosing the correct extraction tool

was repeated several times until the final file became plain ASCII text.

### Read the password

```bash
cat data8
```

---

## Investigation Workflow

```
Hexdump
    │
    ▼
xxd -r
    │
    ▼
gzip
    │
    ▼
bzip2
    │
    ▼
tar
    │
    ▼
tar
    │
    ▼
bzip2
    │
    ▼
tar
    │
    ▼
gzip
    │
    ▼
ASCII text
    │
    ▼
Password
```

---

## Skills Learned

- Hexadecimal data recovery
- Binary reconstruction
- File identification
- gzip
- bzip2
- tar archives
- Temporary working directories
- Digital forensic workflow

---

## Key Takeaways

- Never guess a file type.
- Always identify unknown files using the `file` command.
- Different compression formats require different extraction tools.
- Complex investigations become manageable by solving one layer at a time.

---

## Real-World Relevance

This workflow closely resembles real-world tasks such as:

- Malware analysis
- Firmware extraction
- Digital forensics
- Incident response
- CTF challenges

Security professionals often encounter files with multiple layers of encoding, compression, or archiving.

The systematic use of the `file` command greatly simplifies these investigations.

---

## References

- OverTheWire Bandit
- `man xxd`
- `man gzip`
- `man bzip2`
- `man tar`
- `man file`

---

## Result

✅ Successfully retrieved the password for **Bandit Level 13**.
