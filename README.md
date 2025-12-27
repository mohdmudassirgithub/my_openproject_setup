# my_openproject_setup
This is the openproject setup in fedora linux

# Old docker remove 
sudo dnf remove -y docker* containerd* podman*

# Add repo
sudo dnf config-manager addrepo \
  --from-repofile=https://download.docker.com/linux/fedora/docker-ce.repo
dnf repolist | grep docker

# Install Docker Desktop
sudo dnf install -y \
docker-ce \
docker-ce-cli \
containerd.io \
docker-buildx-plugin \
docker-compose-plugin

# Docker enable
sudo systemctl enable docker --now
systemctl status docker

# Test Docker
docker version
docker run hello-world

# Useradd docker group
sudo usermod -aG docker fedora



systemctl --user start docker-desktop

# Docker compose version
Docker Compose version v2.39.4

docker --version
Docker version 28.4.0, build d8eb465

# Docker version
Client:
 Version:           28.4.0
 API version:       1.51
 Go version:        go1.24.7
<...>
