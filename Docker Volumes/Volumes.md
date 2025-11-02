# Docker Volumes

### Introduction

Docker containers are easiest to use with **stateless applications** because their filesystems are ephemeral in nature.  
Changes made inside a container are **lost** when the container stops, crashes, or is replaced.

However, you can dockerize **stateful applications** such as databases or file servers by attaching **volumes** to your containers.  
Volumes provide **persistent storage** that is independent of individual containers, allowing data to survive container restarts and deletions.

---

### Why Use Docker Volumes?

- 🗂 **Persistence:** Keeps data even when the container is removed.  
- 🔄 **Sharing Data:** Share data between multiple containers.  
- 🧩 **Isolation:** Data is stored outside the container’s writable layer, improving I/O performance and integrity.  
- 🔒 **Backup & Restore:** Volumes can easily be backed up or migrated.

---

### Types of Docker Storage

Docker supports multiple methods for persisting data:

| Type | Managed by Docker | Accessible from Host | Use Case |
|------|-------------------|----------------------|-----------|
| **Bind Mounts** | ❌ No | ✅ Yes | Development, local file access |
| **Named Volumes** | ✅ Yes | ⚠️ Limited (via Docker CLI) | Production, container-to-container sharing |
| **tmpfs Mounts** | ❌ No | ❌ No | Ephemeral in-memory data (not written to disk) |

---

## 🪶 Bind Mounts

Bind mounts allow you to **mount a file or directory from the host system** directly into a container.  
This provides **real-time synchronization** between the container and the host.

#### Example

```bash
docker run -d \
  -v /home/user/app:/usr/src/app \
  -p 3000:3000 \
  node:18-alpine
```

➡️ Here, changes in `/home/user/app` on the host reflect instantly in `/usr/src/app` inside the container.

> ⚠️ **Note:** Bind mounts are ideal for **development**, but not recommended for **production**, as host file system dependencies can break portability.

---

## 📦 Named Volumes

Named volumes are managed entirely by Docker.  
They are **independent of the host’s filesystem structure**, providing better portability and safety.

#### Example

```bash
docker volume create app-data

docker run -d \
  --mount type=volume,src=app-data,dst=/var/lib/mysql \
  mysql:8.0
```

➡️ This mounts the Docker-managed volume `app-data` at `/var/lib/mysql` inside the container.

> ✅ **Recommended:** Named volumes are the preferred approach for **databases, application storage, and production workloads**.

---

### 🔍 Inspecting and Managing Volumes

#### List all volumes

```bash
docker volume ls
```

#### Inspect a specific volume

```bash
docker volume inspect app-data
```

#### Remove unused volumes

```bash
docker volume prune
```

#### Delete a specific volume

```bash
docker volume rm <volume-name>
```

---

### Summary

- Use **Bind Mounts** for development (host-container sync).  
- Use **Named Volumes** for production (Docker-managed, portable, persistent).  
- Combine volumes with **backups** and **docker-compose** for robust data management.
