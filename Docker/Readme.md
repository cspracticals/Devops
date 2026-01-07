# 🐳 Docker Basics – Beginner Reference Guide

This repository contains **beginner-friendly notes on Docker**, created as a quick reference for students and developers who are getting started with containerization.

These notes are inspired by and summarized from a detailed blog by **TechWithKunal** (link provided below).

---

## 📌 What is Docker?

Docker is a **containerization platform** that allows developers to package an application along with all its dependencies into a **container**, ensuring the application runs the same way across different environments.

> “Build once, run anywhere.”

---

## 🚀 Why Use Docker?

Docker helps you to:

- Avoid environment-related issues  
- Run applications consistently across systems  
- Deploy applications faster  
- Use system resources efficiently  
- Simplify DevOps workflows  
- Easily scale applications  

---

## 🧠 Docker vs Virtual Machines

| Docker Containers | Virtual Machines |
|------------------|------------------|
| Lightweight | Heavy |
| Share host OS kernel | Require full guest OS |
| Fast startup | Slow startup |
| Low resource usage | High resource usage |

---

## 🏗️ Docker Architecture

Docker follows a **Client–Server architecture**:

### 1️⃣ Docker Client
- Used to run Docker commands (`docker run`, `docker build`)
- Communicates with Docker Daemon

### 2️⃣ Docker Daemon
- Runs in the background
- Manages images, containers, volumes, and networks

### 3️⃣ Docker Registry
- Stores Docker images
- Default public registry: **Docker Hub**

---

## 📦 Docker Image

- A **Docker image** is a read-only template
- Used to create containers
- Contains application code, libraries, and dependencies
- Images are immutable

### Common Image Commands
```bash
docker images
docker pull ubuntu
docker rmi ubuntu
```
## 🚀 Docker Container

- A **container** is a running instance of an image  
- Containers are **isolated environments**  
- A container **stops when its main process stops**

### Common Container Commands
```bash
docker run -it ubuntu
docker ps
docker ps -a
docker stop <container_id>
docker rm <container_id>
```
### Dockerfile

# A Dockerfile is a text file that contains instructions to build a Docker image.

Example Dockerfile
```
FROM ubuntu
RUN apt-get update
CMD ["echo", "Hello Docker"]
```
docker build -t myimage .

## Cleanup Commands
```
docker container prune
docker image prune
docker system prune -a --volumes
```

### 📚 Reference Blog (Read More)

This README is based on the following blog:

# 🔗 Getting Started with Docker – TechWithKunal
# https://www.techwithkunal.com/blog/getting-started-with-docker

