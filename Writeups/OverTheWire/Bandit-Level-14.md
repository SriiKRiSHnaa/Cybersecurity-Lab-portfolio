# Bandit Level 14

## Objective

Retrieve the password for **Bandit Level 15** by submitting the current level's password to a service listening on `localhost` port `30000`.

---

## Difficulty

⭐⭐⭐ Intermediate

---

## Learning Objectives

- Understand TCP client-server communication.
- Learn to use Netcat (`nc`).
- Submit data to a network service.
- Use pipes and input redirection with networking tools.

---

## Challenge Description

The Bandit server was running a TCP service on `localhost` port `30000`.

The service expected the current level's password as input. If the correct password was submitted, it returned the password for Bandit Level 15.

---

## Commands Used

### Connect to the service

```bash
nc localhost 30000
```

### Submit the current password

```
<Bandit14 Password>
```

---

## Alternative One-Line Solution

```bash
cat /etc/bandit_pass/bandit14 | nc localhost 30000
```

or

```bash
nc localhost 30000 < /etc/bandit_pass/bandit14
```

---

## Command Explanation

### `nc`

Netcat, a utility for creating TCP and UDP connections.

### `localhost`

The local machine.

### `30000`

The TCP port where the challenge service is listening.

---

## Solution

1. Connect to the service using Netcat.
2. Submit the current level password.
3. Receive the password for Bandit Level 15.

---

## Skills Learned

- TCP networking
- Client-server communication
- Netcat (`nc`)
- Pipes
- Input redirection

---

## Key Takeaways

- Network services listen on ports.
- Clients connect to those ports.
- Netcat can manually communicate with TCP services.
- Pipes allow command output to become another command's input.

---

## Real-World Relevance

Netcat is commonly used for:

- Banner grabbing
- Service testing
- Penetration testing
- Debugging network services
- CTF competitions

Understanding TCP communication is fundamental for cybersecurity professionals.

---

## References

- OverTheWire Bandit
- `man nc`

---

## Result

✅ Successfully retrieved the password for **Bandit Level 15**.
