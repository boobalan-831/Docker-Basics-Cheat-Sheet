---

# Docker Basics Cheat Sheet

A concise reference to core Docker commands and workflows.

## 1. Installation

* **Install Docker Desktop (Windows/Mac)**
* **Verify Installation**:



## 2. Key Concepts

* **Image**: Immutable snapshot built from a Dockerfile.
* **Container**: Running instance of an image.
* **Dockerfile**: Text recipe defining how to build an image.
* **Volume**: Persistent storage for containers.
* **Network**: Allows containers to communicate.
* **Docker Compose**: Define and run multi-container apps with a YAML file.

---

## 3. Basic Docker Commands

### 3.1 Image Operations

* **Build an image**:

  ```bash
  docker build -t <image_name> .
  ```
* **List images**:

  ```bash
  docker images
  ```
* **Remove an image**:

  ```bash
  docker rmi <image_name_or_id>
  ```

### 3.2 Container Operations

* **Run a container**:

  ```bash
  docker run -d -p <host_port>:<container_port> --name <container_name> <image_name>
  ```
* **List running containers**:

  ```bash
  docker ps
  ```
* **List all containers**:

  ```bash
  docker ps -a
  ```
* **Stop a container**:

  ```bash
  docker stop <container_id_or_name>
  ```
* **Remove a container**:

  ```bash
  docker rm <container_id_or_name>
  ```
* **View logs**:

  ```bash
  docker logs <container_id_or_name>
  ```
* **Execute shell inside**:

  ```bash
  docker exec -it <container_name> bash
  ```

### 3.3 Volume Management

* **Run with volume**:

  ```bash
  docker run -v /host/path:/container/path <image_name>
  ```
* **List volumes**:

  ```bash
  docker volume ls
  ```
* **Remove volume**:

  ```bash
  docker volume rm <volume_name>
  ```

### 3.4 Networking

* **List networks**:

  ```bash
  docker network ls
  ```
* **Inspect network**:

  ```bash
  docker network inspect <network_name>
  ```

---

## 4. Docker Compose Commands

* **Start services**:

  ```bash
  docker compose up
  ```
* **Start in background**:

  ```bash
  docker compose up -d
  ```
* **Rebuild services**:

  ```bash
  docker compose build --no-cache
  ```
* **Stop and remove containers, networks**:

  ```bash
  docker compose down
  ```

---

## 5. Docker Hub (Registry)

### 5.1 Authenticate

```bash
docker login
```

### 5.2 Pull an image

```bash
docker pull <username>/<image>:<tag>
```

### 5.3 Tag an image

```bash
docker tag <local_image> <username>/<repo>:<tag>
```

### 5.4 Push an image

```bash
docker push <username>/<repo>:<tag>
```

### 5.5 Save & Load (Offline Sharing)

* **Save image to tar**:

  ```bash
  docker save <image_name> > image.tar
  ```
* **Load image from tar**:

  ```bash
  docker load < image.tar
  ```

---

## 6. Handy Tips

* Use descriptive image and container names.
* Leverage Docker caching by ordering `COPY` and `RUN` intelligently.
* Clean up unused resources:

  ```bash
  docker system prune -a
  ```
* Store secrets via environment variables or Docker secrets (not in Dockerfile).

---

*End of Cheat Sheet.*
