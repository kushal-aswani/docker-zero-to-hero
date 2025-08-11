### Installing Docker on Linux
---

#### Step 1: Update System Packages

Start by updating your system's package list to ensure everything is up-to-date.

`sudo apt update && sudo apt upgrade -y`

#### Step 2: Install Dependencies

Install the required dependencies to allow your system to fetch packages from Docker's official repository.

`bash sudo apt install -y ca-certificates curl gnupg`

#### Step 3: Add Docker's GPG Key and Repository

Run the below commands to add Docker's official GPG key and the Docker repository to your system.

`curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg`
`echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null`

#### Step 4: Install Docker

Now, install docker using the apt package manager.

`sudo apt update`
`sudo apt install -y docker-ce docker-ce-cli containerd.io`

#### Step 5: Add User to Docker Group

To run Docker commands without sudo, you need to add your user to the Docker group.

`sudo usermod -aG docker $USER`

**Important:** After running this command, log out and log back in to apply the changes.

#### Step 6: Start Docker on Boot

Use the below command to start docker on boot.

`sudo systemctl enable docker`