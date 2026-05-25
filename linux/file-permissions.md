# 🔐 Linux File Permissions

In Linux, every file and directory has permissions that control who can read, write, or execute it.

---

## 📌 Types of Permissions

There are 3 main permissions:

- **r → read** (view file)
- **w → write** (modify file)
- **x → execute** (run file/program)

---

## 📌 Types of Users

Permissions are given to 3 types of users:

- **Owner** → creator of the file
- **Group** → users in same group
- **Others** → everyone else

---

## 📌 Viewing Permissions

Use this command:

```bash
ls -l
```

### Example output:
```
-rwxr-xr-- 1 user user 1234 file.txt
```

---

## 📌 Understanding Permission Format

Example:
```
-rwxr-xr--
```

Breakdown:

| Part | Meaning |
|------|--------|
| - | file type |
| rwx | owner permissions |
| r-x | group permissions |
| r-- | others permissions |

---

## 📌 Changing Permissions (chmod)

Used to change file permissions.

### Example:

```bash
chmod 777 file.txt
```

### Meaning:
- 7 = read + write + execute
- 777 = full access to everyone

---

## 📌 Common chmod values

| Value | Permission |
|------|------------|
| 7 | rwx (full access) |
| 6 | rw- (read + write) |
| 5 | r-x (read + execute) |
| 4 | r-- (read only) |

---

## 📌 Changing Owner (chown)

```bash
chown user file.txt
```

---

## 🎯 Summary

File permissions are important for:
- security
- server control
- DevOps and system administration