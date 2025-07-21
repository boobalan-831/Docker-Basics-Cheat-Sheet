# Docker Cheat Sheet

**By Boobalan D.**  
_A concise reference to core Docker commands and workflows._

---

## 📦 1. Installation & Setup

| Command                             | Description                                              |
|-------------------------------------|----------------------------------------------------------|
| `docker --version`                  | Show Docker Engine version.                              |
| `docker compose version`            | Show Docker Compose version.                             |
| `docker login`                      | Log in to Docker Hub (for push/pull operations).         |
| `docker logout`                     | Log out from Docker Hub.                                 |

---

## 🧠 2. Core Concepts

- **Image**: Read‑only template built from a Dockerfile.  
- **Container**: Running instance of an image.  
- **Dockerfile**: Text “recipe” that defines how to build an image.  
- **Volume**: Persistent data storage shared between host & container.  
- **Network**: Virtual LAN for container‑to‑container communication.  
- **Compose**: Tool to define/run multi‑container apps via a YAML file.

---

## 🛠️ 3. Basic Docker CLI Commands

### 3.1 Image Management

| Command                                      | Description                                  |
|----------------------------------------------|----------------------------------------------|
| `docker build -t <name>:<tag> <path>`        | Build an image from a Dockerfile.            |
| `docker images`                              | List all local images.                       |
| `docker pull <image>:<tag>`                  | Download image from Docker Hub.              |
| `docker tag <src> <username>/<repo>:<tag>`   | Add a new tag to a local image.              |
| `docker push <username>/<repo>:<tag>`        | Upload image to Docker Hub.                  |
| `docker rmi <image_or_id>`                   | Remove one or more local images.             |

### 3.2 Container Management

| Command                                                   | Description                               |
|-----------------------------------------------------------|-------------------------------------------|
| `docker run -d -p <host>:<container> --name <name> <img>`  | Run container in detached mode.           |
| `docker ps`                                               | List running containers.                  |
| `docker ps -a`                                            | List all containers (running & stopped).  |
| `docker stop <container>`                                 | Stop a running container.                 |
| `docker rm <container>`                                   | Remove one or more stopped containers.    |
| `docker logs <container>`                                 | View container logs.                      |
| `docker exec -it <container> bash`                        | Start a shell inside a running container. |

### 3.3 Data & Networking

| Command                                                   | Description                                         |
|-----------------------------------------------------------|-----------------------------------------------------|
| `docker volume create <name>`                             | Create a named volume.                              |
| `docker volume ls`                                        | List all volumes.                                   |
| `docker run -v <host>:/<container> <image>`               | Mount host directory or volume into container.      |
| `docker network ls`                                       | List networks.                                      |
| `docker network create <name>`                            | Create a user-defined network.                     |
| `docker network connect <network> <container>`            | Connect container to a network.                    |

---

## 📑 4. Docker Compose Commands

| Command                                        | Description                                          |
|------------------------------------------------|------------------------------------------------------|
| `docker compose up`                            | Build, (re)create, start, and attach to containers.  |
| `docker compose up -d`                         | Same as above, but in detached mode.                 |
| `docker compose build --no-cache`              | Build services without cache.                        |
| `docker compose ps`                            | List containers for a Compose project.               |
| `docker compose logs`                          | View output from services.                           |
| `docker compose down`                          | Stop and remove containers, networks, volumes.       |

---

## 🌐 5. Docker Hub & Image Sharing

| Command                                   | Description                                       |
|-------------------------------------------|---------------------------------------------------|
| `docker login`                            | Authenticate to Docker Hub.                       |
| `docker pull <user>/<repo>:<tag>`         | Pull an image from your Docker Hub repository.    |
| `docker push <user>/<repo>:<tag>`         | Push a local image to your Docker Hub repository. |
| `docker save <image> > image.tar`         | Export an image to a tar archive.                 |
| `docker load < image.tar`                 | Import an image from a tar archive.               |

---

## 💡 6. Handy Tips

- Order Dockerfile instructions to maximize layer caching (`COPY requirements.txt` before `COPY . .`).  
- Use **descriptive names** and **tags** (e.g. `myapp:1.0`).  
- Clean up unused resources:  
  ```bash
  docker system prune -a
