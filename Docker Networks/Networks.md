# Docker Networks

Docker networks allow communication between Docker containers and the outside world via the host machine. They also provide isolation and segmentation for containers to ensure secure communication.

---

## Docker Network Drivers

### 1. Bridge Driver

![Bridge Driver](https://miro.medium.com/v2/resize:fit:720/format:webp/0*VDNvPBLuTnXc9cZF.png)

- The **Bridge** network is the default private network created on a host.  
- Containers connected to this network get internal IPs and can communicate with each other.

---

### 2. Host Driver

![Host Driver](https://miro.medium.com/v2/resize:fit:720/format:webp/0*JwZ2n9HIbDncu2-2.png)

- The **Host** driver allows containers to share the host’s network stack.  
- Containers use the host’s IP address and ports to run services.

---

### 3. Overlay Driver

![Overlay Driver](https://miro.medium.com/v2/resize:fit:640/format:webp/0*1xmsjESIUD4wGe32.png)

- The **Overlay** driver enables communication between containers across multiple Docker hosts.  
- Commonly used in **Docker Swarm** or **Kubernetes** setups for multi-host networking.

---

### 4. Macvlan Driver

![Macvlan Driver](https://miro.medium.com/v2/resize:fit:720/format:webp/0*LRqQVdswEDKMp5p8.png)

- The **Macvlan** driver assigns a unique **MAC address** to a container, making it appear as a physical device on the network.  
- Ideal for scenarios requiring containers to directly communicate with the physical network.

---

### 5. None Driver

![None Driver](https://miro.medium.com/v2/resize:fit:600/format:webp/0*TTU1P5TmtIVUYQVG.png)

- The **None** driver disables networking entirely.  
- Containers on this network cannot communicate with the host or other containers.  
- Useful when isolation is critical.

---

## Basic Docker Network Commands

| Command | Description |
|----------|--------------|
| `docker network ls` | Lists all available Docker networks |
| `docker network create <network-name>` | Creates a new Docker network |
| `docker network disconnect <network-name> <container-name-or-id>` | Disconnects a container from a network |
| `docker network inspect <network-name>` | Displays detailed information about a specific network |
| `docker network prune` | Removes all unused networks |

---

### ✅ Summary

Docker networks are essential for managing communication and isolation between containers. Understanding the network drivers helps in designing efficient and secure containerized environments.
