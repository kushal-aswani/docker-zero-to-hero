## 🐳 Anatomy of a Dockerfile

Docker can build images automatically by reading instructions from a **Dockerfile**.  
A Dockerfile is simply a **text document** that contains all the commands you would normally run on the command line to assemble an image.  

---

### 📜 Common Dockerfile Instructions

| Instruction  | Description |
|--------------|-------------|
| **FROM**     | 🏗️ Create a new build stage from a base image |
| **WORKDIR**  | 📂 Change the working directory |
| **RUN**      | ⚙️ Execute build commands |
| **EXPOSE**   | 🌐 Describe the ports your application will be listening on |
| **ENV**      | 🌱 Set environment variables |
| **ENTRYPOINT** | 🚀 Specify the default executable |
| **CMD**      | 💬 Specify default commands/arguments |
| **ARG**      | 🛠️ Define build-time variables |
| **ADD**      | 📦 Add local/remote files and directories (supports URLs & tar extraction) |
| **COPY**     | 📄 Copy files and directories (preferred over ADD for most use cases) |

---

### 🧩 Example: Simple Dockerfile

```dockerfile
FROM ubuntu:latest

WORKDIR /app

COPY . /app

RUN apt-get update && apt-get install -y python3 python3-pip

ENV NAME World

CMD ["python3", "app.py"]
```

### 🔎 Explanation (Line by Line)

- **`FROM ubuntu:latest`** → Uses the official Ubuntu base image (latest tag) from Docker Hub.  
- **`WORKDIR /app`** → Sets the working directory to `/app`. Any subsequent commands will run inside this folder.  
- **`COPY . /app`** → Copies all files from the current host directory into `/app` inside the image.  
- **`RUN apt-get update && apt-get install -y python3 python3-pip`** → Installs dependencies (Python runtime + pip).  
- **`ENV NAME World`** → Defines an environment variable `NAME` with the default value `World`.  
- **`CMD ["python3", "app.py"]`** → Specifies the default command to run when a container starts (in this case, runs the Python app).  


