# 🐧 Install Ubuntu Server 24.04 on Proxmox 9.x VM

This guide documents the installation of **Ubuntu Server 24.04 LTS** inside **Proxmox VE 9.x**, creating a lightweight VM dedicated to running **Portainer**.

---

## ⚙️ VM Specifications

- **Node:** `proxmoxmain`  
- **VM Name:** `Portainer`  
- **Storage:** `zfs1`  
- **Disk Size:** 20 GB (SSD-backed)  
- **CPU:** 1 core  
- **RAM:** 2 GB  
- **Network:** `vmbr0` bridge (VirtIO)  

---

## 📥 Step 1 – Upload Ubuntu ISO

1. Download **Ubuntu Server 24.04 ISO**:  
   👉 [Ubuntu Server Downloads](https://ubuntu.com/download/server)

2. Proxmox Web UI → `proxmoxmain` → **zfs1 › ISO Images › Upload** → select ISO.

---

## 🖥️ Step 2 – Create VM

From Proxmox Web UI:

- **General**
  - Node: `proxmoxmain`
  - VM ID: auto (e.g., `101`)
  - Name: `Portainer`

- **OS**
  - ISO Image: `ubuntu-24.04-live-server-amd64.iso`
  - Guest OS: `Linux` → `6.x - 2.6 Kernel`

- **System**
  - BIOS: OVMF (UEFI) or SeaBIOS  
  - Machine: `q35`  
  - QEMU Agent: **Enable**

- **Disks**
  - Bus: SCSI  
  - Storage: `zfs1`  
  - Disk size: `20G`  
  - Discard: Yes (TRIM)  
  - IO Thread: Yes  

- **CPU**
  - 1 socket, 1 core  
  - Type: `host`

- **Memory**
  - 2048 MB (ballooning enabled)

- **Network**
  - Bridge: `vmbr0`  
  - Model: VirtIO (paravirtualized)

Finish → Start VM.

---

## 🛠️ Step 3 – Install Ubuntu Server

Console into the VM and follow the installer:

- Keyboard/Language: your choice  
- Network: static 
- Disk: guided install on 20 GB  
- User: create your admin user  
- Enable OpenSSH server  

Reboot when finished.

<img width="713" height="529" alt="edd6b833-11c4-4e9f-af44-0c3b9d51e02a" src="https://github.com/user-attachments/assets/f83dfe1b-612e-4ee3-9554-e60329456172" />


---

## 🔧 Step 4 – Post-Install

SSH into the VM or use the console:

```bash
# Update base system
sudo apt update && sudo apt full-upgrade -y

# Install QEMU guest agent
sudo apt install -y qemu-guest-agent
sudo systemctl enable --now qemu-guest-agent
```

---

## 🚧 Status

🟢 Actively maintained as part of my [`homelab`](https://github.com/raoulmoise/homelab) project.

---

