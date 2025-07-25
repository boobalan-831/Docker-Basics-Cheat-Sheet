🔰 Basics
Edit
# 🐋 Run a container
docker run hello-world

# 📦 List images
docker images

# 🚀 Run interactively with terminal
docker run -it ubuntu /bin/bash

# ⛔️ Stop a running container
docker stop <container_id>

# 🧼 Remove a container
docker rm <container_id>

# 🔄 List running containers
docker ps

# 📦 Pull an image
docker pull nginx

# 📤 Push image to Docker Hub
docker push <your_repo>/<image>:tag
⚙️ Dockerfile Essentials
dockerfile

# ✍️ Start from base image
FROM node:18

# 🗂️ Set working directory
WORKDIR /app

# 📁 Copy files
COPY . .

# 🛠️ Install dependencies
RUN npm install

# 🚪 Expose port
EXPOSE 3000

# 🏁 Start command
CMD ["npm", "start"]
🧪 Intermediate Usage

# 👁️ Inspect container details
docker inspect <container>

# 📂 Mount volume
docker run -v /host:/container nginx

# 🖧 Create network
docker network create mynet

# 🔌 Connect container to network
docker network connect mynet <container>

# 🔁 Restart policy
docker run --restart=always nginx

# 🧾 View logs
docker logs -f <container>
🧰 Docker Compose
docker-compose.yml

yaml

version: "3"
services:
  web:
    image: nginx
    ports:
      - "8080:80"
  db:
    image: mysql
    environment:
      MYSQL_ROOT_PASSWORD: password

# 🚀 Start all services
docker-compose up -d

# ⛔️ Stop and remove
docker-compose down

# 🔎 View service logs
docker-compose logs -f
🧠 Advanced
# 📊 Resource usage
docker stats

# 🔎 Changes in container FS
docker diff <container>

# 🧹 Clean everything (⚠️ dangerous!)
docker system prune -a

# 🎯 Limit CPU and Memory
docker run --cpus="1.5" --memory="1g" ubuntu

# 🧪 Exec into running container
docker exec -it <container> bash

# 🔐 Scan image for vulnerabilities
docker scan <image>
📚 Best Practices
✅ Use official base images (FROM node:alpine)

🧹 Clean up temp files in RUN to reduce image size

🛡️ Don’t run as root inside containers

💡 Use .dockerignore to avoid bloated builds

📂 Mount named volumes, not bind mounts in prod

📎 Official Resources
🌐 Docker Docs

📘 Docker CLI Reference

🧠 Scribd Cheat Sheet

✅ Output Format
You can export this Markdown to PDF using:

VS Code + Markdown PDF extension

Typora

HackMD / Dillinger.io

Pandoc CLI

