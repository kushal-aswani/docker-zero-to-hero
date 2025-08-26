### Docker Networks

* Docker networks are primarily used to establish communication between Docker containers and the outside world via the host machine.

* Docker networks are used to provide complete isolation for docker containers

### Docker Network Drivers

#### Bridge Driver

![](https://miro.medium.com/v2/resize:fit:720/format:webp/0*VDNvPBLuTnXc9cZF.png)

* It is a private default network created on a host

* When containers are created through this network, they will receive an internal IP address through which they can communicate with each other

#### Host Driver

![](https://miro.medium.com/v2/resize:fit:720/format:webp/0*JwZ2n9HIbDncu2-2.png)

* This driver will help you in creating a public network for your docker container.

* The container will use the host machine's IP address and port to run services within a container.

#### Overlay Driver

![](https://miro.medium.com/v2/resize:fit:640/format:webp/0*1xmsjESIUD4wGe32.png)

* Overlay driver allows containers across the host to communicate with each other without worrying about the setup

* It is useful for multi-host network communication such as Docker Swarm and Kubernetes

#### Macvlan Driver

![](https://miro.medium.com/v2/resize:fit:720/format:webp/0*LRqQVdswEDKMp5p8.png)

* Macvlan driver allows you to assign a **MAC** address to a container, making it appear as a physical device on your network.

* It is suitable when a user wants to directly connect the container to the physical network rather than the Docker host.

#### None Driver

![](https://miro.medium.com/v2/resize:fit:600/format:webp/0*TTU1P5TmtIVUYQVG.png)

* In this kind of network, containers are not attached to any network which means containers will not be able to communicate with the host machine or with each other.

* This network is used when you want to completely disable networking on a container

### Basic Docker Network Commands

#### List down the networks associated with the Docker

`docker network ls`

#### Creating a network

`docker network create <network-name>`

#### Disconnecting a container from the network

`docker network disconnect <network-name> <container-name-or-id>`

#### Display detailed information about a network

`docker network inspect <network-name`

#### Remove all unused networks

`docker network prune`