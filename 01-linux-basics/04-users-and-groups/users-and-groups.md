# Users and Groups

Linux is a multi-user operating system.

Users and groups are used to control access to files, directories, and system resources.

---

## Users

A user is an account that can interact with the system.

Each user has:

- Username
- User ID (UID)
- Group ID (GID)
- Home directory
- Shell

Example:

```bash
id
```

Output example:

```text
uid=1000(user) gid=1000(user) groups=1000(user)
```

---

## Root User

The root user is the administrator account.

It has full access to the system.

The root user has:

```text
UID: 0
```

Example:

```bash
whoami
```

Output:

```text
root
```

---

## User Information

Linux stores user information in:

```bash
/etc/passwd
```

View users:

```bash
cat /etc/passwd
```

Example entry:

```text
tony:x:1000:1000:Tony:/home/tony:/bin/bash
```

Structure:

```text
username:password:UID:GID:info:home:shell
```

---

## Groups

Groups are collections of users.

They simplify permission management.

Instead of giving permissions to each user individually, you can assign permissions to a group.

Example:

```text
developers
|
├── user1
├── user2
└── user3
```

---

## Group Information

Linux stores groups in:

```bash
/etc/group
```

View groups:

```bash
cat /etc/group
```

Example:

```text
developers:x:1001:user1,user2
```

Structure:

```text
group:password:GID:members
```

---

## Creating Users

Create a user:

```bash
sudo useradd username
```

Create a user with a home directory:

```bash
sudo useradd -m username
```

Example:

```bash
sudo useradd -m alice
```

---

## Setting Passwords

Set or change a user's password:

```bash
sudo passwd username
```

Example:

```bash
sudo passwd alice
```

---

## Creating Groups

Create a group:

```bash
sudo groupadd groupname
```

Example:

```bash
sudo groupadd developers
```

---

## Adding Users to Groups

Add a user to a group:

```bash
sudo usermod -aG group user
```

Example:

```bash
sudo usermod -aG developers alice
```

---

## Switching Users

Change user:

```bash
su username
```

Example:

```bash
su alice
```

Return to previous user:

```bash
exit
```

---

## Checking User Information

Show current user:

```bash
whoami
```

Show user and groups:

```bash
id
```

Show groups:

```bash
groups
```

---

## Deleting Users

Remove a user:

```bash
sudo userdel username
```

Remove user and home directory:

```bash
sudo userdel -r username
```

---

## Users and Groups in Cybersecurity

User and group management is important for:

- Access control
- Privilege management
- Auditing
- System security

Security analysts often check:

- Which users exist
- Which groups users belong to
- Who has administrative privileges

Examples:

Find users:

```bash
cat /etc/passwd
```

Check privileges:

```bash
groups username
```

Check current permissions:

```bash
id
```

---

## Summary

| Command | Purpose |
|---|---|
| `whoami` | Show current user |
| `id` | Show user and groups |
| `groups` | Show group membership |
| `useradd` | Create user |
| `passwd` | Set password |
| `groupadd` | Create group |
| `usermod` | Modify user |
| `userdel` | Delete user |
| `su` | Switch user |
