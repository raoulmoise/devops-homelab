# 🐧 VM1 on Proxmox

This folder documents how I install and configure **Ubuntu Server 24.X LTS** VM, with Portainer and Homepage. 
The goal is to keep a reproducible process for deploying VMs and services on top of Ubuntu.  

---

## 📦 Contents

- [`install.md`](./install.md) → Clean installation steps for Ubuntu Server  
- [`post-install.md`](./post-install.md) → Base configuration (updates, packages, Docker, etc.)  
- Service-specific guides:
  - [homepage-dashboard](https://github.com/raoulmoise/homelab/tree/main/containers/homepage-dashboard)
  - [portainer](https://github.com/raoulmoise/homelab/tree/main/containers/portainer)
  

---

## ⚙️ VM Specifications

- **Disk**: 60GB LVM 
- **CPU**: 2 cores  
- **RAM**: 4 GB
- **Network**: `virtio` with static IP   

---

## 🚧 Status

🟢 Actively maintained as part of my [`homelab`](https://github.com/raoulmoise/homelab) project.
