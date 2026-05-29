# Bash Basics

## Introduction

Bash (Bourne Again Shell) is a command-line interpreter used in Linux and Unix-based systems. It allows users to execute commands, automate tasks, manage files, and write scripts.

---

## Print Text

```bash
echo "Hello World"
```

Output:

```text
Hello World
```

---

## Variables

```bash
name="Dhanush"
echo $name
```

Output:

```text
Dhanush
```

---

## User Input

```bash
read name
echo "Hello $name"
```

---

## Comments

```bash
# This is a single line comment
```

---

## Arithmetic Operations

```bash
num1=10
num2=5

echo $((num1 + num2))
echo $((num1 - num2))
echo $((num1 * num2))
echo $((num1 / num2))
echo $((num1 % num2))
```

---

## Comparison Operators

| Operator | Meaning |
|-----------|----------|
| -eq | Equal |
| -ne | Not Equal |
| -gt | Greater Than |
| -lt | Less Than |
| -ge | Greater Than or Equal |
| -le | Less Than or Equal |

Example:

```bash
if [ 10 -gt 5 ]
then
echo "True"
fi
```

---

## If Statement

```bash
age=18

if [ $age -ge 18 ]
then
echo "Eligible"
fi
```

---

## If Else Statement

```bash
age=15

if [ $age -ge 18 ]
then
echo "Adult"
else
echo "Minor"
fi
```

---

## If Elif Else Statement

```bash
marks=85

if [ $marks -ge 90 ]
then
echo "Grade A"
elif [ $marks -ge 75 ]
then
echo "Grade B"
else
echo "Grade C"
fi
```

---

## Logical Operators

### AND

```bash
if [ 10 -gt 5 ] && [ 20 -gt 10 ]
then
echo "True"
fi
```

### OR

```bash
if [ 10 -gt 20 ] || [ 20 -gt 10 ]
then
echo "True"
fi
```

### NOT

```bash
if [ ! 10 -eq 5 ]
then
echo "True"
fi
```

---

## For Loop

```bash
for i in 1 2 3 4 5
do
echo $i
done
```

---

## While Loop

```bash
count=1

while [ $count -le 5 ]
do
echo $count
count=$((count + 1))
done
```

---

## Until Loop

```bash
count=1

until [ $count -gt 5 ]
do
echo $count
count=$((count + 1))
done
```

---

## Functions

```bash
greet() {
echo "Hello DevOps"
}

greet
```

---

## Arrays

```bash
fruits=("Apple" "Mango" "Orange")

echo ${fruits[0]}
echo ${fruits[1]}
echo ${fruits[2]}
```

Print all elements:

```bash
echo ${fruits[@]}
```

---

## String Length

```bash
name="Dhanush"

echo ${#name}
```

Output:

```text
7
```

---

## String Uppercase

```bash
name="devops"

echo ${name^^}
```

Output:

```text
DEVOPS
```

---

## Command Line Arguments

```bash
echo $1
echo $2
```

Run:

```bash
bash script.sh Linux DevOps
```

Output:

```text
Linux
DevOps
```

---

## Case Statement

```bash
read choice

case $choice in

1)
echo "Option 1"
;;

2)
echo "Option 2"
;;

*)
echo "Invalid Choice"
;;

esac
```

---

## Environment Variables

Current User:

```bash
echo $USER
```

Home Directory:

```bash
echo $HOME
```

Current Shell:

```bash
echo $SHELL
```

---

## File Operations

Current Directory:

```bash
pwd
```

List Files:

```bash
ls
```

Create Directory:

```bash
mkdir test
```

Change Directory:

```bash
cd test
```

Create File:

```bash
touch file.txt
```

Delete File:

```bash
rm file.txt
```

Delete Directory:

```bash
rm -r test
```

---

## Permissions

View Permissions:

```bash
ls -l
```

Make Script Executable:

```bash
chmod +x script.sh
```

---

## Process Management

Show Running Processes:

```bash
ps
```

Detailed Processes:

```bash
ps aux
```

Kill Process:

```bash
kill PID
```

---

## System Information

Current Date:

```bash
date
```

Current User:

```bash
whoami
```

Hostname:

```bash
hostname
```

System Uptime:

```bash
uptime
```

---

## Useful Commands

```bash
history
clear
man ls
which bash
```

---

## Running Bash Scripts

Method 1:

```bash
bash script.sh
```

Method 2:

```bash
./script.sh
```

---

## Advantages of Bash

- Easy to learn
- Automates repetitive tasks
- Useful for DevOps and System Administration
- Works on most Linux distributions
- Helps manage servers efficiently

---

## Conclusion

Bash is one of the most important tools for Linux administrators, DevOps engineers, and cloud professionals. Learning Bash helps automate tasks, manage systems, and improve productivity.