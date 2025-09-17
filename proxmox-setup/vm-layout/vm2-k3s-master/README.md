# 🐧 VM2 on Proxmox

This folder documents how I install and configure **Ubuntu Server 24.X LTS** VM with K3S. 
The goal is to keep a reproducible process for deploying VMs and services on top of Ubuntu.  

---

## 📦 Contents

- [`install.md`](https://github.com/raoulmoise/homelab/blob/main/proxmox-setup/vm-layout/vm2-k3s-master/install.md) → Clean installation steps for Ubuntu Server  
- [`post-install.md`](./post-install.md) → Base configuration (updates, packages, Docker, etc.)  
  
---

## ⚙️ VM Specifications

- **Disk**: 40 GB LVM 
- **CPU**: 1 core  
- **RAM**: 4 GB 
- **Network**: `virtio` with static IP   

---

## 🚧 Status

🟢 Actively maintained as part of my [`homelab`](https://github.com/raoulmoise/homelab) project.

