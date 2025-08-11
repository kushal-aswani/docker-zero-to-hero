# Introduction to Docker

### What is Docker?

Docker is an open platform for developing, shipping, and running applications.  
It enables you to package an application and its dependencies into a standardized unit called a **container**. These containers are lightweight, portable, and ensure consistency across different environments.

### Docker Architecture

Docker uses a **client-server** architecture, where the Docker **client** communicates with the Docker **daemon** (`dockerd`). The daemon handles the heavy lifting of building, running, and managing Docker containers.

The client and daemon can run on the same host or be connected remotely. They communicate over a REST API, using UNIX sockets or a network interface.

<p align="center">
    <img src="https://docs.docker.com/get-started/images/docker-architecture.webp" alt="Docker Architecture" />
</p>


### Key Components of Docker

#### 🐳 Docker Daemon (`dockerd`)

The Docker **daemon** listens for Docker API requests and manages Docker objects like **images**, **containers**, **networks**, and **volumes**. It can also communicate with other daemons to manage multi-host containerized applications via **Docker Swarm** or **services**.

#### 💻 Docker Client (`docker`)

The Docker **client** is the primary interface for most users. When you run commands like `docker run`, the client sends the request to the Docker daemon, which executes it.  
The client can communicate with multiple daemons.

#### 📦 Docker Registries

A **Docker registry** stores Docker images.  
Docker Hub is a popular public registry that Docker uses by default, but you can also configure and use private registries.

Common commands:
- `docker pull`: Retrieves an image from a registry.
- `docker push`: Uploads an image to a registry.

### Docker Objects

Docker works with several core objects. Here are the most important ones:

#### 📸 Images

A **Docker image** is a read-only template used to create containers.  
It contains the application code, runtime, libraries, environment variables, and configuration files needed to run the app.

Images are often built on top of base images (e.g., `ubuntu`, `node`, `python`) with additional layers added during customization.

#### 📦 Containers

A **container** is a runnable instance of an image.  
You can create, start, stop, move, or delete containers using the Docker CLI or API.

Key characteristics:
- Containers are isolated from the host and from each other.
- You can configure containers with specific storage, network, and environment settings.
- When a container is deleted, any changes not stored in **volumes** or **bind mounts** are lost.
