# Shell Scripting

## Introduction

Shell scripting is the process of writing a series of Linux commands in a file and executing them automatically. Shell scripts help automate repetitive tasks, manage servers, perform backups, monitor systems, and simplify DevOps workflows.

---

## What is a Shell Script?

A shell script is a text file containing Bash commands.

Example:

```bash
#!/bin/bash

echo "Hello World"
```

Save as:

```bash
script.sh
```

Run:

```bash
bash script.sh
```

Output:

```text
Hello World
```

---

## Shebang

The first line of a script is called a shebang.

```bash
#!/bin/bash
```

It tells Linux to execute the script using Bash.

---

## Variables in Shell Scripts

```bash
#!/bin/bash

name="Dhanush"

echo "Welcome $name"
```

Output:

```text
Welcome Dhanush
```

---

## User Input

```bash
#!/bin/bash

echo "Enter your name:"
read name

echo "Hello $name"
```

---

## Command Line Arguments

```bash
#!/bin/bash

echo "First Argument: $1"
echo "Second Argument: $2"
```

Run:

```bash
bash script.sh Linux DevOps
```

Output:

```text
First Argument: Linux
Second Argument: DevOps
```

---

## Arithmetic Operations

```bash
#!/bin/bash

a=20
b=10

echo $((a+b))
echo $((a-b))
echo $((a*b))
echo $((a/b))
```

---

## If Statement

```bash
#!/bin/bash

age=20

if [ $age -ge 18 ]
then
echo "Eligible"
fi
```

---

## If Else Statement

```bash
#!/bin/bash

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
#!/bin/bash

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

## For Loop

```bash
#!/bin/bash

for i in 1 2 3 4 5
do
echo $i
done
```

Output:

```text
1
2
3
4
5
```

---

## While Loop

```bash
#!/bin/bash

count=1

while [ $count -le 5 ]
do
echo $count
count=$((count + 1))
done
```

---

## Functions

```bash
#!/bin/bash

greet() {
echo "Welcome to DevOps"
}

greet
```

---

## Arrays

```bash
#!/bin/bash

fruits=("Apple" "Mango" "Orange")

echo ${fruits[0]}
echo ${fruits[1]}
echo ${fruits[2]}
```

---

## Case Statement

```bash
#!/bin/bash

echo "Enter Choice:"
read choice

case $choice in

1)
echo "Install Docker"
;;

2)
echo "Install Nginx"
;;

*)
echo "Invalid Option"
;;

esac
```

---

## Reading Files

Suppose file.txt contains:

```text
Linux
Docker
Kubernetes
```

Script:

```bash
#!/bin/bash

while read line
do
echo $line
done < file.txt
```

---

## Writing to Files

```bash
#!/bin/bash

echo "Hello DevOps" > output.txt
```

Append data:

```bash
echo "Docker" >> output.txt
```

---

## File Existence Check

```bash
#!/bin/bash

if [ -f test.txt ]
then
echo "File Exists"
else
echo "File Not Found"
fi
```

---

## Directory Existence Check

```bash
#!/bin/bash

if [ -d project ]
then
echo "Directory Exists"
else
echo "Directory Not Found"
fi
```

---

## Error Handling

```bash
#!/bin/bash

mkdir test

if [ $? -eq 0 ]
then
echo "Success"
else
echo "Failed"
fi
```

`$?` stores the exit status of the previous command.

---

## Logging

```bash
#!/bin/bash

echo "Backup Started" >> backup.log
date >> backup.log
```

Logs help track script execution.

---

## Backup Script Example

```bash
#!/bin/bash

backup_dir="/backup"

mkdir -p $backup_dir

cp -r /home/user/project $backup_dir

echo "Backup Completed"
```

---

## Compress Files

```bash
#!/bin/bash

tar -czvf backup.tar.gz project/
```

Creates a compressed archive.

---

## Disk Usage Monitoring

```bash
#!/bin/bash

df -h
```

Displays disk usage.

---

## Memory Usage Monitoring

```bash
#!/bin/bash

free -h
```

Displays RAM usage.

---

## CPU Monitoring

```bash
#!/bin/bash

top
```

or

```bash
htop
```

Displays CPU and process information.

---

## Process Monitoring

```bash
#!/bin/bash

ps aux
```

Shows running processes.

---

## Service Management

Check service status:

```bash
systemctl status nginx
```

Start service:

```bash
systemctl start nginx
```

Stop service:

```bash
systemctl stop nginx
```

Restart service:

```bash
systemctl restart nginx
```

---

## Automated Nginx Installation Script

```bash
#!/bin/bash

sudo apt update

sudo apt install nginx -y

sudo systemctl start nginx

sudo systemctl enable nginx

echo "Nginx Installed Successfully"
```

---

## Scheduled Tasks Using Cron

View Cron Jobs:

```bash
crontab -l
```

Edit Cron Jobs:

```bash
crontab -e
```

Example:

```bash
0 2 * * * /home/user/backup.sh
```

Runs daily at 2:00 AM.

---

## System Information Script

```bash
#!/bin/bash

echo "User: $(whoami)"
echo "Hostname: $(hostname)"
echo "Date: $(date)"
echo "Uptime:"
uptime
```

---

## DevOps Use Cases of Shell Scripting

Shell scripting is widely used in DevOps for:

- Server Automation
- Application Deployment
- Backup Management
- Log Monitoring
- User Management
- Service Monitoring
- Infrastructure Automation
- Cron Job Scheduling
- Docker Automation
- Kubernetes Administration
- CI/CD Pipelines

---

## Advantages of Shell Scripting

- Easy to learn
- Reduces manual work
- Automates repetitive tasks
- Improves productivity
- Saves time
- Essential for DevOps Engineers

---

## Best Practices

- Use meaningful variable names
- Add comments in scripts
- Validate user input
- Handle errors properly
- Store logs for debugging
- Use functions for reusable code
- Avoid hardcoding passwords
- Test scripts before production deployment

---

## Conclusion

Shell scripting is a powerful automation tool used by Linux administrators, Cloud Engineers, and DevOps professionals. It helps automate tasks, manage infrastructure, monitor systems, and improve operational efficiency.