# Process Management

A process is a running instance of a program.

Linux manages processes to control system resources such as CPU, memory, and execution time.

Process management is important for:

- Monitoring system activity
- Troubleshooting
- Performance analysis
- Security investigation

---

## Understanding Processes

Every process has information such as:

- Process ID (PID)
- User who started it
- CPU usage
- Memory usage
- Current state

The PID identifies each running process.

---

## Viewing Processes

Use `ps` to view running processes.

```bash
ps
```

Example output:

```text
PID   TTY      TIME     CMD
1234  pts/0    00:00    bash
1450  pts/0    00:00    firefox
```

---

## ps aux

`ps aux` shows all running processes.

```bash
ps aux
```

Example:

```text
USER   PID   %CPU  %MEM   COMMAND
root   1     0.0   0.1    systemd
tony   500   2.5   5.0    firefox
```

Important columns:

| Column | Meaning |
|---|---|
| USER | Process owner |
| PID | Process ID |
| %CPU | CPU usage |
| %MEM | Memory usage |
| COMMAND | Running program |

---

## Real-Time Monitoring

### top

`top` displays processes in real time.

```bash
top
```

Shows:

- CPU usage
- Memory usage
- Running processes
- System load

Exit:

```text
q
```

---

## htop

`htop` is an interactive version of `top`.

Install:

```bash
sudo apt install htop
```

Run:

```bash
htop
```

Features:

- Easier visualization
- Process search
- Direct process control

---

## Finding Processes

Search for a process:

```bash
ps aux | grep process
```

Example:

```bash
ps aux | grep firefox
```

Shows processes related to Firefox.

---

## Ending Processes

### kill

`kill` sends a signal to a process.

Usage:

```bash
kill PID
```

Example:

```bash
kill 1450
```

---

## kill -9

Forcefully terminates a process.

```bash
kill -9 PID
```

Example:

```bash
kill -9 1450
```

Use when a process does not stop normally.

---

## Process Signals

Linux uses signals to communicate with processes.

Common signals:

| Signal | Number | Purpose |
|---|---|---|
| SIGTERM | 15 | Graceful termination |
| SIGKILL | 9 | Force termination |
| SIGSTOP | 19 | Pause process |

Example:

```bash
kill -15 1234
```

---

## Background Processes

A command can run in the background using `&`.

Example:

```bash
firefox &
```

The terminal remains available.

---

## Jobs

View background jobs:

```bash
jobs
```

Example:

```text
[1] Running firefox &
```

---

## Moving Processes

Send a process to background:

```text
Ctrl + Z
```

Resume in background:

```bash
bg
```

Bring back to foreground:

```bash
fg
```

---

## Process Priority

Linux assigns priorities to processes.

Priority affects CPU scheduling.

---

## nice

Start a process with a priority.

Example:

```bash
nice -n 10 command
```

Higher value = lower priority.

---

## renice

Change priority of an existing process.

Example:

```bash
renice 5 -p PID
```

---

## Process Management in Cybersecurity

Security analysts use process management to:

- Detect suspicious programs
- Investigate malware activity
- Monitor resource usage
- Identify unauthorized processes

Examples:

Check running processes:

```bash
ps aux
```

Monitor activity:

```bash
top
```

Find suspicious process:

```bash
ps aux | grep unknown
```

Terminate malicious process:

```bash
kill -9 PID
```

---

## Summary

| Command | Purpose |
|---|---|
| `ps` | View processes |
| `ps aux` | View all processes |
| `top` | Real-time monitoring |
| `htop` | Interactive monitoring |
| `kill` | Stop process |
| `kill -9` | Force stop |
| `jobs` | View background jobs |
| `bg` | Send process to background |
| `fg` | Bring process to foreground |
| `nice` | Set priority |
| `renice` | Change priority |
