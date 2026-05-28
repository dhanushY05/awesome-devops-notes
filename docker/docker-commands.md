# Docker Commands 🐳

This document contains commonly used Docker commands for managing:

* images
* containers
* volumes
* networks
* logs
* Docker system operations

---

# Check Docker Version

```bash
docker --version
```

Displays installed Docker version.

---

# Docker Help

```bash
docker --help
```

Shows all available Docker commands.

---

# Docker Images

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

Displays all downloaded images.

---

## Remove an Image

```bash
docker rmi nginx
```

Deletes a Docker image.

---

## Remove Multiple Images

```bash
docker rmi image_id1 image_id2
```

---

## Remove All Images

```bash
docker rmi $(docker images -q)
```

---

# Docker Containers

## Run a Container

```bash
docker run nginx
```

Creates and starts a container.

---

## Run Container in Detached Mode

```bash
docker run -d nginx
```

Runs container in background.

---

## Run Container with Custom Name

```bash
docker run --name mynginx nginx
```

---

## Run Container with Port Mapping

```bash
docker run -p 8080:80 nginx
```

Maps:

* host port → 8080
* container port → 80

---

## Run Interactive Container

```bash
docker run -it ubuntu bash
```

Starts interactive terminal.

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

Stops running container.

---

## Start a Container

```bash
docker start container_id
```

Starts stopped container.

---

## Restart a Container

```bash
docker restart container_id
```

---

## Pause a Container

```bash
docker pause container_id
```

Temporarily pauses container.

---

## Unpause a Container

```bash
docker unpause container_id
```

---

## Kill a Container

```bash
docker kill container_id
```

Forcefully stops container.

---

## Remove a Container

```bash
docker rm container_id
```

Deletes container.

---

## Remove All Stopped Containers

```bash
docker container prune
```

---

# Execute Commands Inside Container

## Open Bash Shell

```bash
docker exec -it container_id bash
```

---

## Open sh Shell

```bash
docker exec -it container_id sh
```

---

# Docker Logs

## View Logs

```bash
docker logs container_id
```

---

## Follow Logs

```bash
docker logs -f container_id
```

Displays live logs.

---

## Show Last 50 Log Lines

```bash
docker logs --tail 50 container_id
```

---

# Docker Inspect

## Inspect Container

```bash
docker inspect container_id
```

Shows detailed information.

---

# Docker Stats

## Monitor Resource Usage

```bash
docker stats
```

Displays:

* CPU usage
* memory usage
* network usage

---

# Docker Volumes

## Create Volume

```bash
docker volume create myvolume
```

---

## List Volumes

```bash
docker volume ls
```

---

## Inspect Volume

```bash
docker volume inspect myvolume
```

---

## Remove Volume

```bash
docker volume rm myvolume
```

---

## Mount Volume

```bash
docker run -v myvolume:/data ubuntu
```

---

# Bind Mounts

## Mount Current Directory

```bash
docker run -v $(pwd):/app node
```

---

# Docker Networks

## List Networks

```bash
docker network ls
```

---

## Create Network

```bash
docker network create mynetwork
```

---

## Inspect Network

```bash
docker network inspect mynetwork
```

---

## Remove Network

```bash
docker network rm mynetwork
```

---

## Run Container in Network

```bash
docker run --network=mynetwork nginx
```

---

# Docker Build Commands

## Build Docker Image

```bash
docker build -t myapp .
```

---

## Build Image with Version Tag

```bash
docker build -t myapp:v1 .
```

---

# Docker Compose Commands

## Start Services

```bash
docker-compose up
```

---

## Start in Detached Mode

```bash
docker-compose up -d
```

---

## Stop Services

```bash
docker-compose down
```

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

---

# Docker System Commands

## Check Docker Disk Usage

```bash
docker system df
```

---

## Remove Unused Resources

```bash
docker system prune
```

---

## Remove Everything Unused

```bash
docker system prune -a
```

---

# Docker Hub Commands

## Login to Docker Hub

```bash
docker login
```

---

## Push Image

```bash
docker push username/image
```

---

## Pull Image

```bash
docker pull username/image
```

---

# Docker Copy Commands

## Copy File from Host to Container

```bash
docker cp file.txt container_id:/app
```

---

## Copy File from Container to Host

```bash
docker cp container_id:/app/file.txt .
```

---

# Environment Variables

## Pass Environment Variable

```bash
docker run -e APP_ENV=production nginx
```

---

# Restart Policies

## Always Restart Container

```bash
docker run --restart always nginx
```

Restart Policies:

* no
* always
* unless-stopped
* on-failure

---

# Docker Cleanup Commands

## Remove Stopped Containers

```bash
docker container prune
```

---

## Remove Unused Images

```bash
docker image prune
```

---

## Remove Unused Volumes

```bash
docker volume prune
```

---

## Remove Unused Networks

```bash
docker network prune
```

---

# Common Docker Command Examples

## Run Nginx Web Server

```bash
docker run -d -p 8080:80 nginx
```

---

## Run Ubuntu Container

```bash
docker run -it ubuntu bash
```

---

## Run Node.js Container

```bash
docker run -it node
```

---

# Useful Docker Shortcuts

| Command           | Purpose            |
| ----------------- | ------------------ |
| docker ps         | Running containers |
| docker images     | List images        |
| docker logs       | View logs          |
| docker exec       | Open terminal      |
| docker build      | Build image        |
| docker-compose up | Start services     |

---

# Summary

Docker commands help manage:

* containers
* images
* volumes
* networks
* logs
* deployments

Learning Docker commands is essential for DevOps, Cloud, and Backend Development.
