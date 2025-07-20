# How to Install Docker on Linux (Ubuntu/Debian)

### Step 1: Uninstall Old Versions (if any)

```bash
sudo apt-get remove docker docker-engine docker.io containerd runc
```

### Step 2: Update the apt Package Index and Install Dependencies

```bash
sudo apt-get update

sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
```

### Step 3: Add Docker’s Official GPG Key

```bash
sudo mkdir -p /etc/apt/keyrings

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | \
    sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```

### Step 4: Set Up the Docker Repository

```bash
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] \
  https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

### Step 5: Update the Package Index Again

```bash
sudo apt-get update
```

### Step 6: Install Docker Engine and Components

```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io \
    docker-buildx-plugin docker-compose-plugin
```

### Step 7: Verify Docker Installation

```bash
sudo docker run hello-world
```

### Step 8: Check Docker Version

```bash
docker --version
```
