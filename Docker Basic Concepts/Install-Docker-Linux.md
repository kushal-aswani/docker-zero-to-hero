# Installing Docker on Linux

---

## Step 1: Update System Packages

Before installing Docker, ensure your system is up to date to avoid conflicts or missing dependencies.

```bash
sudo apt update && sudo apt upgrade -y
```

---

## Step 2: Install Dependencies

Install the essential dependencies required for Docker to work correctly and securely fetch packages from Docker’s official repository.

```bash
sudo apt install -y ca-certificates curl gnupg
```

---

## Step 3: Add Docker’s GPG Key and Repository

Add Docker’s official GPG key and set up the stable repository for your Linux distribution.

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

Then add the repository:

```bash
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

---

## Step 4: Install Docker

Update the package index and install Docker Engine, CLI, and container runtime.

```bash
sudo apt update
sudo apt install -y docker-ce docker-ce-cli containerd.io
```

---

## Step 5: Add User to the Docker Group

To execute Docker commands without using `sudo`, add your user to the Docker group.

```bash
sudo usermod -aG docker $USER
```

**⚠️ Important:** You must log out and log back in (or restart your terminal session) for the changes to take effect.

---

## Step 6: Enable Docker to Start on Boot

Ensure Docker starts automatically when your system boots.

```bash
sudo systemctl enable docker
```

To start Docker immediately without rebooting:

```bash
sudo systemctl start docker
```

---

## Step 7: Verify Docker Installation

Check if Docker is installed and running properly.

```bash
docker --version
docker run hello-world
```

If the “hello-world” container runs successfully, Docker is correctly installed and ready for use. 🎉
