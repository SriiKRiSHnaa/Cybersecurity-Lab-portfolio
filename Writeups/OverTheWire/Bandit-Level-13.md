# Bandit Level 13

## Objective

Retrieve the password for **Bandit Level 14**.

Unlike previous levels, the password cannot be read directly. Instead, a private SSH key is provided that must be used to authenticate as the `bandit14` user.

---

## Difficulty

⭐⭐⭐ Intermediate

---

## Learning Objectives

- Understand SSH key-based authentication.
- Learn the difference between password authentication and public key authentication.
- Use the `ssh -i` option.
- Secure private keys using proper file permissions.

---

## Challenge Description

The home directory contained a private SSH key named `sshkey.private`.

This key had to be used to authenticate as the `bandit14` user instead of using a password.

Direct SSH from within the Bandit server is blocked, so the key was copied to the local Kali machine using `scp`.

---

## Commands Used

### Copy the private key to Kali Linux

```bash
scp -P 2220 bandit13@bandit.labs.overthewire.org:~/sshkey.private .
```

### Restrict key permissions

```bash
chmod 600 sshkey.private
```

### Login using the private key

```bash
ssh -i sshkey.private -p 2220 bandit14@bandit.labs.overthewire.org
```

### Verify the logged-in user

```bash
whoami
```

### Retrieve the password

```bash
cat /etc/bandit_pass/bandit14
```

---

## Command Explanation

### `scp`

Securely copies files over SSH.

### `chmod 600`

Restricts access to the private key so only the owner can read and write it.

### `ssh -i`

Specifies the private key (identity file) used for authentication.

### `-p 2220`

Connects to the Bandit SSH server on port 2220.

---

## Solution

1. Copy the private key to the local machine.
2. Restrict its permissions.
3. Authenticate as `bandit14` using the key.
4. Read the password from:

```text
/etc/bandit_pass/bandit14
```

---

## Skills Learned

- SSH key authentication
- Secure file permissions
- Secure file transfer with SCP
- SSH identity files

---

## Key Takeaways

- SSH keys are more secure than passwords.
- Private keys should never be shared.
- Private keys should have restrictive permissions (`600`).
- Many production Linux servers disable password authentication entirely and rely on SSH keys.

---

## Real-World Relevance

SSH key authentication is widely used in:

- Linux server administration
- AWS EC2
- Azure Virtual Machines
- Google Cloud Platform
- GitHub SSH authentication
- Penetration testing
- CTF competitions

Understanding SSH keys is an essential skill for cybersecurity professionals.

---

## References

- OverTheWire Bandit
- `man ssh`
- `man scp`

---

## Result

✅ Successfully authenticated using an SSH private key and retrieved the password for **Bandit Level 14**.
