# Docker Basics 🚀

## What is Docker?

Docker is an open-source containerization platform used to build, package, and run applications inside lightweight environments called containers.

Docker helps developers and DevOps engineers:

* run applications consistently
* avoid dependency conflicts
* simplify deployments
* isolate applications
* improve scalability

---

# Why Docker?

Before Docker:

* applications worked differently on different systems
* setup was difficult
* dependencies caused conflicts

Docker solves these problems by packaging:

* application code
* libraries
* dependencies
* configurations

inside containers.

---

# What is a Container?

A container is a lightweight, isolated environment that contains everything needed to run an application.

Containers are:

* portable
* fast
* lightweight
* consistent

---

# Docker vs Virtual Machine

| Virtual Machine       | Docker Container |
| --------------------- | ---------------- |
| Heavy                 | Lightweight      |
| Full Operating System | Shares Host OS   |
| Slow Startup          | Fast Startup     |
| Uses More RAM         | Uses Less RAM    |

---

# Docker Architecture

Docker architecture consists of:

## Docker Client

The interface used to interact with Docker.

Example:

```bash
docker run nginx
```

---

## Docker Daemon

Runs in the background and manages:

* containers
* images
* networks
* volumes

---

## Docker Images

Blueprints used to create containers.

Example:

* Ubuntu image
* Nginx image
* Node.js image

---

## Docker Containers

Running instances of Docker images.

---

## Docker Registry

Stores Docker images.

Examples:

* Docker Hub
* AWS ECR
* GitHub Container Registry

---

# Installing Docker (Ubuntu)

Update packages:

```bash
sudo apt update
```

Install Docker:

```bash
sudo apt install docker.io -y
```

Start Docker:

```bash
sudo systemctl start docker
```

Enable Docker:

```bash
sudo systemctl enable docker
```

Check Docker version:

```bash
docker --version
```

---

# Important Docker Commands

## Pull an Image

```bash
docker pull nginx
```

Downloads the nginx image from Docker Hub.

---

## List Images

```bash
docker images
```

Shows downloaded Docker images.

---

## Run a Container

```bash
docker run nginx
```

Creates and starts a container.

---

## Run in Detached Mode

```bash
docker run -d nginx
```

Runs the container in background mode.

---

## List Running Containers

```bash
docker ps
```

Shows active containers.

---

## List All Containers

```bash
docker ps -a
```

Shows all containers including stopped ones.

---

## Stop a Container

```bash
docker stop container_id
```

Stops a running container.

---

## Start a Container

```bash
docker start container_id
```

Starts a stopped container.

---

## Remove a Container

```bash
docker rm container_id
```

Deletes a container.

---

# Docker Run Flags

| Flag   | Meaning               |
| ------ | --------------------- |
| -d     | Detached Mode         |
| -it    | Interactive Terminal  |
| -p     | Port Mapping          |
| --name | Custom Container Name |
| -v     | Volume Mount          |

Example:

```bash
docker run -d -p 8080:80 --name mynginx nginx
```

---

# Port Mapping

Port mapping connects host machine ports to container ports.

Syntax:

```bash
host_port:container_port
```

Example:

```bash
docker run -p 3000:80 nginx
```

---

# Interactive Containers

Open terminal inside container:

```bash
docker run -it ubuntu bash
```

Exit terminal:

```bash
exit
```

---

# Docker Logs

View container logs:

```bash
docker logs container_id
```

Live logs:

```bash
docker logs -f container_id
```

---

# Execute Commands Inside Container

```bash
docker exec -it container_id bash
```

---

# Docker Images vs Containers

| Images                    | Containers           |
| ------------------------- | -------------------- |
| Blueprint                 | Running Instance     |
| Read-only                 | Active Process       |
| Used to Create Containers | Executes Application |

---

# Docker Lifecycle

1. Pull Image
2. Create Container
3. Run Container
4. Stop Container
5. Remove Container

---

# Benefits of Docker

* Faster deployments
* Consistent environments
* Lightweight applications
* Better scalability
* Easy portability
* Simplified DevOps workflows

---

# Real-world Use Cases

Docker is commonly used for:

* microservices
* CI/CD pipelines
* cloud deployments
* development environments
* testing applications

---

# Docker Best Practices

* use official images
* minimize image size
* avoid running containers as root
* use .dockerignore
* clean unused containers

---

# Common Docker Errors

## Port Already Allocated

Cause:

* another application already uses the port

Fix:

```bash
sudo lsof -i :80
```

---

## Permission Denied

Fix:

```bash
sudo usermod -aG docker $USER
```

Then restart the terminal.

---

# Summary

Docker is one of the most important tools in modern DevOps.

It helps developers and DevOps engineers:

* build applications faster
* deploy consistently
* isolate services
* simplify infrastructure management

Docker is widely used with:

* Kubernetes
* Jenkins
* AWS
* GitHub Actions
* Terraform
