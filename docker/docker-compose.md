# Docker Compose 🐳

## What is Docker Compose?

Docker Compose is a tool used to define and manage multi-container Docker applications using a YAML configuration file.

Instead of running multiple `docker run` commands manually, Docker Compose allows you to manage everything from a single file called:

```bash
docker-compose.yml
```

---

# Why Docker Compose?

Docker Compose helps:

* manage multiple containers
* simplify deployments
* automate container setup
* improve development workflows

---

# Example Without Docker Compose

Running applications manually:

```bash
docker run -d --name mongodb mongo
```

```bash
docker run -d -p 3000:3000 node-app
```

Managing multiple services manually becomes difficult.

---

# Example With Docker Compose

Everything is managed inside one YAML file.

```yaml
version: '3'

services:
  app:
    image: node

  database:
    image: mongo
```

Start all services together:

```bash
docker-compose up
```

---

# Docker Compose Architecture

Docker Compose works using:

* services
* networks
* volumes
* containers

---

# Installing Docker Compose

## Ubuntu

```bash
sudo apt update
```

```bash
sudo apt install docker-compose -y
```

Check version:

```bash
docker-compose --version
```

---

# Docker Compose File

Docker Compose configuration is written in:

```bash
docker-compose.yml
```

---

# Basic Docker Compose Example

```yaml
version: '3'

services:
  web:
    image: nginx
    ports:
      - "80:80"
```

---

# Understanding the Compose File

## version

Defines Compose file version.

```yaml
version: '3'
```

---

## services

Defines application containers.

```yaml
services:
```

---

## image

Specifies Docker image.

```yaml
image: nginx
```

---

## ports

Maps ports between host and container.

```yaml
ports:
  - "80:80"
```

Syntax:

```bash
host_port:container_port
```

---

# Multi-Container Example

```yaml
version: '3'

services:
  frontend:
    image: nginx
    ports:
      - "80:80"

  backend:
    image: node

  database:
    image: mongo
```

This creates:

* frontend container
* backend container
* database container

---

# Running Docker Compose

## Start Services

```bash
docker-compose up
```

---

## Start in Detached Mode

```bash
docker-compose up -d
```

Runs containers in background.

---

## Stop Services

```bash
docker-compose down
```

Stops and removes containers.

---

## Restart Services

```bash
docker-compose restart
```

---

## View Running Services

```bash
docker-compose ps
```

---

## View Logs

```bash
docker-compose logs
```

Live logs:

```bash
docker-compose logs -f
```

---

# Building Images with Compose

Compose can build custom Docker images.

Example:

```yaml
version: '3'

services:
  app:
    build: .
    ports:
      - "3000:3000"
```

---

# Build and Start Containers

```bash
docker-compose up --build
```

---

# Volumes in Docker Compose

Volumes provide persistent storage.

Example:

```yaml
version: '3'

services:
  database:
    image: mysql
    volumes:
      - mysql-data:/var/lib/mysql

volumes:
  mysql-data:
```

---

# Networks in Docker Compose

Compose automatically creates networks.

Containers communicate using service names.

Example:

```yaml
backend:
```

can communicate with:

```yaml
database:
```

using:

```bash
database:27017
```

---

# Environment Variables

Example:

```yaml
version: '3'

services:
  app:
    image: node
    environment:
      - NODE_ENV=production
      - PORT=3000
```

---

# Using .env File

Create `.env` file:

```bash
DB_USER=admin
DB_PASSWORD=password
```

Use inside Compose:

```yaml
environment:
  - DB_USER=${DB_USER}
```

---

# Depends On

Controls startup order.

Example:

```yaml
services:
  backend:
    depends_on:
      - database
```

---

# Restart Policies

Example:

```yaml
restart: always
```

Policies:

* no
* always
* on-failure
* unless-stopped

---

# Docker Compose Commands

| Command                | Purpose             |
| ---------------------- | ------------------- |
| docker-compose up      | Start services      |
| docker-compose up -d   | Start in background |
| docker-compose down    | Stop services       |
| docker-compose ps      | Show containers     |
| docker-compose logs    | View logs           |
| docker-compose restart | Restart services    |

---

# Real-world Example

## MERN Stack

```yaml
version: '3'

services:
  frontend:
    image: react-app

  backend:
    image: node-api

  database:
    image: mongo
```

---

# Advantages of Docker Compose

* simplifies container management
* easy multi-container setup
* faster development
* easier deployments
* automatic networking

---

# Docker Compose vs Dockerfile

| Dockerfile                 | Docker Compose               |
| -------------------------- | ---------------------------- |
| Builds image               | Manages multiple containers  |
| Defines image instructions | Defines application services |
| Single container focus     | Multi-container focus        |

---

# Common Docker Compose Errors

## Port Already Allocated

Cause:

* port already in use

Fix:

```bash
sudo lsof -i :80
```

---

## Service Not Found

Cause:

* wrong service name

Fix:

* check docker-compose.yml indentation
* verify service names

---

# Docker Compose Best Practices

* use meaningful service names
* use environment variables
* use volumes for databases
* avoid hardcoding secrets
* organize Compose files properly

---

# Docker Compose Use Cases

Docker Compose is widely used for:

* local development
* microservices
* full-stack applications
* testing environments
* CI/CD workflows

---

# Interview Questions

## What is Docker Compose?

Docker Compose is a tool for defining and managing multi-container Docker applications.

---

## What file does Docker Compose use?

```bash
docker-compose.yml
```

---

## Difference between Docker and Docker Compose?

Docker:

* manages individual containers

Docker Compose:

* manages multiple containers together

---

# Summary

Docker Compose simplifies:

* multi-container management
* networking
* storage
* deployments

It is one of the most important tools for DevOps and backend development workflows.
