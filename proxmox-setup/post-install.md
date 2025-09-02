# ⚙️ Proxmox Post-Install Setup

After installing **Proxmox VE 8 (Trixie)**, these steps were performed to configure the host for daily use and VM deployment.

---

## 🔄 System Update & Repository Fix

Proxmox defaults to enterprise repositories (subscription required).  
I switched to **no-subscription repos** for both Proxmox and Ceph.

---


## 🔄 System Update & Repository Fix
- Add non-subscription repositories and update them:
```bash
nano /etc/apt/sources.list.d/proxmox.sources
nano /etc/apt/sources.list.d/ceph.sources
apt update && apt full-upgrade -y
```
### proxmox.sources file
```bash
Types: deb
URIs: http://download.proxmox.com/debian/pve
Suites: trixie
Components: pve-no-subscription
Signed-By: /usr/share/keyrings/proxmox-archive-keyring.gpg
```

### ceph.sources file
```bash
Types: deb
URIs: http://download.proxmox.com/debian/ceph-squid
Suites: trixie
Components: no-subscription
Signed-By: /usr/share/keyrings/proxmox-archive-keyring.gpg
```
<img width="545" height="80" alt="image" src="https://github.com/user-attachments/assets/86699b52-1b26-439f-935e-6469948e09de" />

---

## 🌐 Networking

- Static IP was set during installation.
- Default Proxmox bridge vmbr0 is used for VM traffic (no manual reconfiguration needed).

---

## 💾 Storage Configuration

- SSD (480 GB) → Local VM storage (disks + ISOs).
- HDDs (2 × 1TB) → Configured as ZFS mirror pool (tank) using the GUI.
- Used for backups and larger VM storage.

---

## Security

- Enabled Proxmox firewall at the Datacenter level.
- Allowed only required access (Web UI, SSH).
- Updates are performed regularly.

---


## 🚧 Status

🟢 Actively maintained as part of my [`proxmox-setup`](https://github.com/raoulmoise/proxmox-setup) project.

---
