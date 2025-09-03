# 🐧 Ubuntu Server Setup

This folder documents how I install and configure **Ubuntu Server 24.X LTS** VM, where I have configured Portainer and Homepage. 
The goal is to keep a reproducible process for deploying VMs and services on top of Ubuntu.  

---

## 📦 Contents

- [`install.md`](./install.md) → Clean installation steps for Ubuntu Server  
- [`post-install.md`](./post-install.md) → Base configuration (updates, packages, Docker, etc.)  
- Service-specific guides:
  - [homepage-dashboard](https://github.com/raoulmoise/homelab/tree/main/containers/homepage-dashboard)
  - [portainer](https://github.com/raoulmoise/homelab/tree/main/containers/portainer)
  

---

## ⚙️ VM Specifications (default template)

When deployed in **Proxmox**, I use this baseline for Ubuntu Server VMs:

- **Disk**: 20–30 GB (ZFS or LVM backend)  
- **CPU**: 1–2 cores  
- **RAM**: 2 GB minimum (4 GB recommended for Docker-heavy workloads)  
- **Network**: `virtio` with static IP  
- **Extras**: QEMU Guest Agent installed for integration with Proxmox  

---

## 🚧 Status

🟢 Actively maintained as part of my [`homelab`](https://github.com/raoulmoise/homelab) project.
