### What is Docker?
---

* Docker is an open platform for developing, shipping and running applications.

* Docker provides the ability to package and run an application in a loosely isolated environment called a container.

### Docker Architecture
---

* Docker uses client-server architecture. The docker client talks to the Docker daemon which does the heavy lifting of building, running and distributing your docker containers.

* The docker client and daemon can run on the same system or you can connect a docker client to a remote docker daemon.

* The docker client and daemon communicate using a REST API, over UNIX sockets or a network interface.

<p align="center">
    <img src="https://docs.docker.com/get-started/images/docker-architecture.webp" />
</p>

#### Docker Daemon
---
Docker daemon (dockerd) listens for API requests and manage Docker objects such as images, containers, networks and volumes. A daemon can also communicate with other daemons to manage Docker services.

#### Docker Client
---
Docker client (docker) is the primary way that many Docker users interact with Docker. When you use commands such as "docker run", the client sends these commands to dockerd, which carries them out. The "docker" command uses the Docker API. The docker client can communicate with more than one daemon.

#### Docker Registries
---
A docker registry that will store docker images. Docker hub is a public registry that anyone can use and Docker looks for images on Docker hub by default. You can even run your own private registry. When you use the "docker pull" or "docker run" commands. Docker pulls the required images from your configured registry. When you use the "docker push" command, docker pushes your image to your configured registry.

#### Docker Objects
---

##### Images

An images is a read-only template with instructions for creating a Docker container. Often, an image is based on another image, with additional customization. For example, you may build an image which is based on the "ubuntu" image, but installs the Apache web server and your application, as well as the configuration details needed to make your application run.

##### Containers
A container is a runnable instance of an image. You can create, stop, move or delete a container using the Docker API or CLI. You can connect a container to one or more networks, attach storage to it, or even create a new image based on its current state.

By default, a container is relatively well isolated from other containers and its host machine. You can control how isolated a container's network, storage or other underlying subsystems are from other containers or from the host machine.

A container is defined by its image as well as any configuration options you provide to it when you create or start it. When a container is removed, any changes to it's state that aren't stored in persistent storage disappear.