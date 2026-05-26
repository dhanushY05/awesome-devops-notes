# 🌿 Git Branching

Branching allows developers to work on new features without affecting the main project.

---

## 📌 What is a Branch?

A branch is a separate version of the project used for development.

Main branch:
```txt
main
```

---

## 📌 View Branches

```bash
git branch
```

Shows all branches.

---

## 📌 Create New Branch

```bash
git branch feature-login
```

Creates a branch called:
```txt
feature-login
```

---

## 📌 Switch Branch

```bash
git checkout feature-login
```

Moves to another branch.

---

## 📌 Create and Switch Together

```bash
git checkout -b feature-login
```

Creates and switches to branch.

---

## 📌 Merge Branch

```bash
git merge feature-login
```

Merges branch into current branch.

---

## 📌 Delete Branch

```bash
git branch -d feature-login
```

Deletes branch after merge.

---

## 📌 Why Branching is Important?

Branching helps:
- avoid breaking main code
- develop features safely
- work in teams

---

## 🎯 Example Workflow

```txt
main → feature-login → merge → main
```

---

## 🎯 Summary

Git branching is used for:
- feature development
- bug fixing
- team collaboration
- safe code management