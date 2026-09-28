# Docker Cheatsheet 🐳

A quick reference guide for essential Docker and Docker Compose operations.

---

## 1. Container Lifecycle

| Command | Description |
| :--- | :--- |
| `docker run -d --name <name> -p <host_port>:<container_port> <image>` | Run a container in detached mode with port mapping |
| `docker ps` | List running containers |
| `docker ps -a` | List all containers (including stopped ones) |
| `docker start <container>` | Start a stopped container |
| `docker stop <container>` | Gracefully stop a running container |
| `docker restart <container>` | Restart a container |
| `docker rm <container>` | Remove a stopped container |
| `docker rm -f <container>` | Force remove a running container |

---

## 2. Image Management

| Command | Description |
| :--- | :--- |
| `docker images` | List locally stored images |
| `docker build -t <image_name>:<tag> .` | Build an image from a Dockerfile in the current directory |
| `docker pull <image>` | Download an image from Docker Hub |
| `docker rmi <image>` | Remove a local image |
| `docker tag <source_image> <target_image>:<tag>` | Tag an image for a registry |
| `docker push <username>/<image>:<tag>` | Push an image to Docker Hub or remote registry |

---

## 3. Inspection & Debugging

| Command | Description |
| :--- | :--- |
| `docker logs -f <container>` | Fetch and follow live logs of a container |
| `docker exec -it <container> /bin/bash` | Open an interactive Bash shell inside a container |
| `docker exec -it <container> sh` | Open an interactive Shell (for Alpine images) |
| `docker inspect <container_or_image>` | Display detailed JSON metadata of a container/image |
| `docker stats` | Display live streaming statistics of container resource usage |

---

## 4. Volumes & Networks

| Command | Description |
| :--- | :--- |
| `docker volume ls` | List all Docker volumes |
| `docker volume create <volume_name>` | Create a named volume |
| `docker network ls` | List all Docker networks |
| `docker network create <network_name>` | Create a custom network |
| `docker network connect <network> <container>` | Connect a container to a network |

---

## 5. System Cleanup

| Command | Description |
| :--- | :--- |
| `docker system prune` | Remove unused data (stopped containers, unused networks, dangling images) |
| `docker system prune -a --volumes` | Deep clean: Remove ALL unused images, volumes, and networks |

---

## 6. Docker Compose

| Command | Description |
| :--- | :--- |
| `docker compose up -d` | Build, (re)create, and start containers in detached mode |
| `docker compose down` | Stop and remove containers, networks created by `up` |
| `docker compose down -v` | Stop containers and remove named volumes as well |
| `docker compose ps` | List containers managed by the current compose file |
| `docker compose logs -f` | Follow logs for all services |
| `docker compose exec <service_name> sh` | Run an interactive shell in a service container |
