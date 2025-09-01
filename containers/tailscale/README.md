# 🔐 Tailscale (Docker) Setup

This guide documents how I deployed [Tailscale](https://tailscale.com/) inside Docker to enable secure remote access to my homelab.

---

## 📦 What is Tailscale?

"Tailscale is a zero-config VPN that creates a secure, peer-to-peer mesh network between your devices.  
It’s built on WireGuard and handles NAT traversal automatically, allowing you to connect to your machines anywhere without port forwarding."

Tailscale allows you to:
- Access your homelab securely from anywhere
- Bypass CGNAT and firewall limitations (no public IP required)
- Use a private subnet of **100.x.x.x** addresses across devices
- Manage all machines from a central admin console

🔗 Project site: [https://tailscale.com/](https://tailscale.com/)

---

## 💻 Hardware Used

### First Computer – HP EliteDesk 800 G1 (Homelab Host)  
- **CPU:** Intel Core i5-4570  
- **RAM:** 32 GB DDR3  
- **Storage:** 480 GB SSD + 2 × 1 TB HDD (RAID1)  
- **Network:** Ethernet (static IP via Netplan)  
- **Operating System:** Ubuntu Server  

---

## ⏳ Installation

**Folder setup:**
```bash
mkdir -p /home/labops/docker_volumes/tailscale/config
cd /home/labops/docker_volumes/tailscale
docker compose up -d
```
Generate an auth key in the Tailscale admin console (Settings → Keys):

TS_AUTHKEY=tskey-auth-XXXXXXXXXXXXXXXXXXXXXXXXXXXX

TS_HOSTNAME=YOURNAME

## 🐳 Docker Compose File
---
```yaml
version: "3.9"
services:
  tailscale:
    image: tailscale/tailscale:latest
    container_name: tailscale
    hostname: TS_HOSTNAME
    network_mode: host
    cap_add: # Required for tailscale to work
      - NET_ADMIN
      - NET_RAW
    devices: # Required for tailscale to work
      - /dev/net/tun:/dev/net/tun
    environment:
      - TS_AUTHKEY=TS_AUTHKEY 
      - TS_STATE_DIR=/var/lib/tailscale # State data will be stored in this dir
    volumes:
      - /home/labops/docker_volumes/tailscale/config:/var/lib/tailscale
    restart: unless-stopped
```

## 🔐 Accessing Tailscale

- Check your node in the admin console: https://login.tailscale.com/admin/machines
- On the host, verify:
```bash
docker exec tailscale tailscale status
docker exec tailscale tailscale ip -4
```

---

## 🚧 Status

🟢 Actively maintained as part of my [`homelab`](https://github.com/raoulmoise/homelab) project.

---
