# 🐧 Install Ubuntu Server 24.x on Proxmox 9.x VM

This guide documents the installation of **Ubuntu Server 24.04 LTS** inside **Proxmox VE 9.x**, creating a lightweight VM dedicated to running **Portainer**.

---

## ⚙️ VM Specifications

- **Node:** `proxmoxmain`  
- **VM Name:** `Portainer`  
- **Storage:** `zfs1`  
- **Disk Size:** 60 GB (SSD-backed)  
- **CPU:** 2 core  
- **RAM:** 4 GB  
- **Network:** `vmbr0` bridge (VirtIO)  

---

## 📥 Step 1 – Upload Ubuntu ISO

1. Download **Ubuntu Server 24.x ISO**:  
   👉 [Ubuntu Server Downloads](https://ubuntu.com/download/server)

2. Proxmox Web UI → `proxmoxmain` → **zfs1 › ISO Images › Upload** → select ISO.

---

## 🖥️ Step 2 – Create VM

From Proxmox Web UI:

- **General**
  - Node: `proxmoxmain`
  - VM ID: auto (e.g., `100`)
  - Name: `Portainer`

- **OS**
  - ISO Image: `ubuntu-24.x-live-server-amd64.iso`
  - Guest OS: `Linux` → `6.x - 2.6 Kernel`

- **Disks**
  - Bus: SCSI  
  - Storage: `zfs1`  
  - Disk size: `60G`  
  - Discard: Yes (TRIM)  
  - IO Thread: Yes  

- **CPU**
  - 1 socket, 2 cores  
  - Type: `host`

- **Memory**
  - 4096 MB

- **Network**
  - Bridge: `vmbr0`  
  - Model: VirtIO

Finish → Start VM.

---

## 🛠️ Step 3 – Install Ubuntu Server

Console into the VM and follow the installer:

- Keyboard/Language: your choice  
- Network: static 
- Disk: guided install on 60 GB + LUKS crypt  
- User: create your admin user  
- Enable OpenSSH server  

Reboot when finished.

<img width="668" height="237" alt="image" src="https://github.com/user-attachments/assets/16a68e3d-7c45-4409-b49f-90452c27e8b6" />


---

## 🔧 Step 4 – Post-Install

[post-install](https://github.com/raoulmoise/homelab/blob/main/proxmox-setup/vm-layout/ubuntu-server-setup/post-install.md)

---

## 🚧 Status

🟢 Actively maintained as part of my [`homelab`](https://github.com/raoulmoise/homelab) project.

---

