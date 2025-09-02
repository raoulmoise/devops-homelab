# ⚙️ Proxmox VE Installation Guide

This document explains how I installed and configured **Proxmox VE** on my homelab server.  
The goal is to manage multiple virtual machines (VMs) for Docker services, monitoring, and security tools.

---

## 🖥️ Hardware Used
- **Model:** HP EliteDesk 800 G1  
- **CPU:** Intel Core i5-4570  
- **RAM:** 32 GB DDR3  
- **Storage:** 480 GB SSD + 2 × 1 TB HDD (RAID1)  
- **Network:** Ethernet (static IP planned for host)  

---

## 📥 Step 1 – Download Proxmox VE ISO
- [Official Proxmox Downloads](https://www.proxmox.com/en/downloads)  
- Used **Proxmox VE 9.x ISO Installer**

---

## 💿 Step 2 – Create Bootable Media
- Used **Rufus** (Windows) / `dd` (Linux) to flash ISO to a USB stick.
<img width="464" height="531" alt="image" src="https://github.com/user-attachments/assets/9cd947eb-c7de-43c5-9975-21ffa657da46" />
- Booted HP EliteDesk from USB.

---

## ⚡ Step 3 – Install Proxmox
- Selected target disk: `480 GB SSD`
- Configured RAID1 separately for data storage.
- Set root password and email for admin notifications.
- Assigned a static IP to the management interface.

---

## 🌐 Step 4 – First Login
- Accessed web UI from another machine: https://proxmox.example.com:8006

---

## 📦 Step 5 – Initial Configuration
- Updated repositories:
```bash
apt update && apt full-upgrade -y
```
- Configured local storage (SSD for VMs, HDD RAID for backups/ISO/images).
-  Created first VM: Ubuntu Server 24.04 LTS.

---

## 📚 References

- [Proxmox VE Documentation](https://pve.proxmox.com/pve-docs/?utm_source=chatgpt.com)
- [Proxmox Wiki](https://pve.proxmox.com/wiki/Main_Page?utm_source=chatgpt.com)

---

## 🚧 Status

🟢 Actively maintained as part of my [`proxmox-setup`](https://github.com/raoulmoise/proxmox-setup) project.

---

