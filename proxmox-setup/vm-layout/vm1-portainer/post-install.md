# 🔧 Ubuntu Server Post-Install

After installing **Ubuntu Server 24.04 LTS**, these are the post-installation steps I applied in my homelab environment.

---

## 📦 System Updates
```bash
# Update base system
sudo apt update && sudo apt full-upgrade -y
```
---

## 🖥️ QEMU Guest Agent (Proxmox VM)
```bash
# Install QEMU guest agent
sudo apt install -y qemu-guest-agent
sudo systemctl enable --now qemu-guest-agent
```
---

## 🐳 Docker & Docker Compose
```bash
# Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update

# Install Docker
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

# Verify if Docker works
sudo docker run hello-world
```
---

## 📂 Containers Installed

| Container         | Description                        | Setup Guide                             |
|----------------|------------------------------------|------------------------------------------|
| Homepage        | Dashboard & service launcher       | [homepage-dashboard](https://github.com/raoulmoise/homelab/tree/main/containers/homepage-dashboard) |
| Portainer       | Docker container manager GUI       | [portainer](https://github.com/raoulmoise/homelab/tree/main/containers/portainer) |

---

## 🚧 Status

🟢 Actively maintained as part of my [`homelab`](https://github.com/raoulmoise/homelab) project.

---
