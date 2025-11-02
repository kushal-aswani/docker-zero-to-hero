# Introduction to Docker

## What is Docker?

Docker is an **open platform** for developing, shipping, and running applications.  
It allows developers to package an application with all its dependencies into a standardized unit called a **container**. Containers are lightweight, portable, and ensure consistent behavior across environments—from development to production.


## Docker Architecture

Docker follows a **client–server architecture**, consisting of the **Docker Client**, **Docker Daemon**, and **Docker Registry**.

- The **Docker Client** communicates with the **Docker Daemon** (`dockerd`), which performs tasks such as building, running, and managing containers.
- They communicate using a REST API, via UNIX sockets or a network interface.
- The client and daemon can reside on the same machine or operate remotely.

<p align="center">
  <img src="https://docs.docker.com/get-started/images/docker-architecture.webp" alt="Docker Architecture" />
</p>


## Key Components of Docker

### 🐳 Docker Daemon (`dockerd`)

The **Docker Daemon** is the background process that manages Docker objects such as images, containers, networks, and volumes.  
It listens for Docker API requests and executes them. It can also communicate with other daemons to manage distributed applications using **Docker Swarm** or other orchestration tools.

### 💻 Docker Client (`docker`)

The **Docker Client** is the main interface for users.  
When commands like `docker run` or `docker build` are executed, the client sends these instructions to the daemon, which processes them.  
A single client can communicate with multiple Docker daemons.

### 📦 Docker Registries

A **Docker Registry** is a repository that stores Docker images.  
Docker Hub is the default public registry, but you can also use **private registries** for secure image storage.

Common commands:
- `docker pull`: Retrieve an image from a registry.
- `docker push`: Upload an image to a registry.

---


## Docker Objects

Docker primarily operates using the following core objects:

### 📸 Images

A **Docker Image** is a read-only template used to create containers.  
It includes everything needed to run an application—code, runtime, system tools, libraries, and settings.

Images are typically built on top of base images (e.g., `ubuntu`, `node`, `python`) and customized through a `Dockerfile`.

### 📦 Containers

A **Container** is a lightweight, runnable instance of an image.  
You can create, start, stop, move, or remove containers using the Docker CLI or API.

Key properties:
- Containers are **isolated** from one another and the host system.
- They can have dedicated **networking, storage**, and **environment variables**.
- When deleted, unsaved data (not in volumes or bind mounts) is lost.

---

**In summary**, Docker simplifies application deployment by ensuring consistency across environments, reducing dependency conflicts, and improving scalability through containerized workloads.
