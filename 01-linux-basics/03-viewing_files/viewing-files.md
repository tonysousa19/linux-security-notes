# Viewing Files

Linux provides several commands to read and inspect file contents directly from the terminal.

These commands are useful for checking configuration files, logs, scripts, and system information.

---

## cat

`cat` displays the entire content of a file.

Usage:

```bash
cat file.txt
```

Example:

```bash
cat notes.txt
```

Output:

```text
Linux basics
Users
Permissions
Processes
```

Useful for small files.

---

## less

`less` allows you to read files page by page.

Usage:

```bash
less file.txt
```

Navigation:

- `Space` → next page
- `b` → previous page
- `q` → quit

Useful for large files.

Example:

```bash
less /var/log/syslog
```

---

## more

`more` is a simple file viewer that displays content page by page.

Usage:

```bash
more file.txt
```

It has fewer navigation features than `less`.

---

## head

`head` displays the beginning of a file.

Usage:

```bash
head file.txt
```

By default, it shows the first 10 lines.

Show a specific number of lines:

```bash
head -n 20 file.txt
```

Shows the first 20 lines.

---

## tail

`tail` displays the end of a file.

Usage:

```bash
tail file.txt
```

By default, it shows the last 10 lines.

Show a specific number of lines:

```bash
tail -n 20 file.txt
```

Shows the last 20 lines.

---

## tail -f

`tail -f` monitors a file and displays new content when it is added.

Usage:

```bash
tail -f file.log
```

Example:

```bash
tail -f /var/log/syslog
```

Useful for:

- Monitoring logs
- Troubleshooting
- Security analysis

---

## Viewing Files in Cybersecurity

Security analysts use these commands to inspect:

- System logs
- Configuration files
- User information
- Scripts

Examples:

View system users:

```bash
cat /etc/passwd
```

Analyze authentication logs:

```bash
less /var/log/auth.log
```

Monitor new log entries:

```bash
tail -f /var/log/syslog
```

---

## Summary

| Command | Purpose |
|---|---|
| `cat` | Display entire file |
| `less` | Read large files |
| `more` | Simple file viewer |
| `head` | Show beginning of file |
| `tail` | Show end of file |
| `tail -f` | Monitor changes in real time |
