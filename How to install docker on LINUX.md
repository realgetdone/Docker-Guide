# How to install docker on LINUX

1. Step 1: **Uninstall old versions (if any)**

```bash
sudo apt-get remove docker docker-engine docker.io containerd runc
```

1.  **Update the apt package index and install dependencies**

```bash
sudo apt-get update
sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
```

1.  **Add Docker’s official GPG key**

```bash
sudo mkdir -p /etc/apt/keyrings

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | \
    sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```

1. Step 4: **Set up the Docker repository**

```bash
echo \
  "deb [arch=$(dpkg --print-architecture) \
  signed-by=/etc/apt/keyrings/docker.gpg] \
  https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

1. Update package index again

```bash
sudo apt-get update
```

1. Step 6: **Install Docker Engine**

```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

1. Verify the installation

```bash
sudo docker run hello-world
```

1. Docker Version Check

```bash
docker --version
```