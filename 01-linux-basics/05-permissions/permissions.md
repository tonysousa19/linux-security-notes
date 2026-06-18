# Permissions

Linux uses permissions to control who can read, modify, or execute files and directories.

Every file and directory has:

- Owner
- Group
- Permissions for owner, group, and others

---

## Viewing Permissions

Use `ls -l` to view file permissions.

```bash
ls -l
```

Example output:

```text
-rwxr-xr-- 1 tony developers 1200 script.sh
```

Structure:

```text
-rwxr-xr--
│││││││││
│││││││└── Others
│││││└──── Group
│││└────── Owner
│└──────── File type
```

---

## File Types

The first character shows the type:

```text
-  regular file
d  directory
l  symbolic link
```

Example:

```text
drwxr-xr-x
```

The `d` means it is a directory.

---

## Permission Types

Linux has three main permissions:

| Permission | Meaning |
|---|---|
| `r` | Read |
| `w` | Write |
| `x` | Execute |

---

## Permission Groups

Permissions are divided into three categories:

```text
Owner   Group   Others

rwx     r-x     r--
```

Example:

```text
-rwxr-xr--
```

Means:

Owner:

```text
rwx
```

Can read, write, and execute.

Group:

```text
r-x
```

Can read and execute.

Others:

```text
r--
```

Can only read.

---

## Numeric Permissions

Permissions can also be represented by numbers.

Values:

```text
r = 4
w = 2
x = 1
```

Add values together:

```text
rwx = 4 + 2 + 1 = 7

rw- = 4 + 2 = 6

r-x = 4 + 1 = 5
```

---

## chmod

`chmod` changes file permissions.

Usage:

```bash
chmod permissions file
```

Example:

```bash
chmod 755 script.sh
```

Meaning:

```text
Owner: 7 = rwx
Group: 5 = r-x
Others: 5 = r-x
```

---

## Symbolic chmod

Permissions can also be changed using letters.

Add execute permission:

```bash
chmod +x script.sh
```

Remove write permission:

```bash
chmod -w file.txt
```

Add read permission for group:

```bash
chmod g+r file.txt
```

---

## Changing Ownership

`chown` changes the owner of a file.

Usage:

```bash
chown user file
```

Example:

```bash
sudo chown alice file.txt
```

Change owner and group:

```bash
sudo chown alice:developers file.txt
```

---

## Changing Groups

`chgrp` changes the group of a file.

Usage:

```bash
chgrp group file
```

Example:

```bash
sudo chgrp developers project.txt
```

---

## Directory Permissions

Directories use permissions differently.

Read:

```text
r
```

Allows listing files.

Write:

```text
w
```

Allows creating or deleting files.

Execute:

```text
x
```

Allows entering the directory.

Example:

```bash
chmod 755 folder
```

---

## Special Permissions

Linux also has special permissions:

### SUID

Allows a file to run with the owner's privileges.

Example:

```text
-rwsr-xr-x
```

The `s` replaces `x`.

---

### SGID

Allows files inside a directory to inherit the group.

Example:

```text
drwxrwsr-x
```

---

### Sticky Bit

Commonly used in shared directories.

Only the file owner can delete their files.

Example:

```text
drwxrwxrwt
```

Used in:

```bash
/tmp
```

---

## Permissions in Cybersecurity

Permissions are important for:

- Preventing unauthorized access
- Protecting sensitive files
- Controlling privileges
- System hardening

Security analysts check:

- Files with excessive permissions
- Suspicious ownership changes
- Executable files

Examples:

Find files with permissions:

```bash
ls -la
```

Check sensitive files:

```bash
ls -l /etc/passwd
```

---

## Summary

| Command | Purpose |
|---|---|
| `ls -l` | View permissions |
| `chmod` | Change permissions |
| `chown` | Change owner |
| `chgrp` | Change group |
| `umask` | Default permissions |
