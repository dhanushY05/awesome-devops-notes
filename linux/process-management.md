# ⚙️ Linux Process Management

In Linux, a process is a running program. Process management is used to monitor, control, and stop running processes.

---

## 📌 What is a Process?

A process is:
- A program in execution
- Identified by a unique ID called **PID (Process ID)**

---

## 📌 Viewing Running Processes

### 1. Using ps command

```bash
ps
```

Shows processes running in current terminal.

---

### 2. Detailed process list

```bash
ps aux
```

### Meaning:
- a → all users processes
- u → user-friendly format
- x → processes without terminal

---

## 📌 Real-time Process Monitoring

### top command

```bash
top
```

Shows live running processes with:
- CPU usage
- Memory usage
- PID

---

## 📌 Killing a Process

### Step 1: Find PID

```bash
ps aux
```

### Step 2: Kill process

```bash
kill PID
```

Example:

```bash
kill 1234
```

---

## 📌 Force Kill Process

If process does not stop:

```bash
kill -9 PID
```

---

## 📌 Better Tool than top

### htop (advanced view)

```bash
htop
```

👉 More user-friendly interface

---

## 📌 Background & Foreground Processes

### Run process in background

```bash
command &
```

Example:

```bash
ping google.com &
```

---

### Bring process to foreground

```bash
fg
```

---

## 📌 Check Running Jobs

```bash
jobs
```

---

## 🎯 Summary

Process management is used for:
- monitoring system performance
- stopping unwanted processes
- managing server resources

It is very important in:
- DevOpsx
- Linux administration
- Cloud servers