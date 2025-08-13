# Ubuntu Server Setup Guide (Homelab Edition)

This guide documents how I installed and configured Ubuntu Server (24.04) on one of my homelab machines. It includes full install steps, post-install configuration, and essential tooling for running containers and DevOps workflows.

---

## 💻 Hardware Used

- Device: HP EliteDesk 800 G1
- CPU: Intel i5-4570
- RAM: 32 GB DDR3
- Storage: 480GB SSD + 2x 1TB HDD RAID1
- Network: Ethernet (static IP via Netplan)

---

## 📚 What’s Covered

| File | Description |
|------|-------------|
| `install.md` | Step-by-step installation process |
| `post-install.md` | Basic configuration, hardening, and tooling |
| `scripts/` | Optional automation scripts (e.g., Docker install) |

---

## 📦 Software Installed

- OpenSSH server

---

## 🔐 Optional Hardening Steps

- Disable root SSH login

---

## 🚧 Status

🟢 Actively maintained as part of my [`homelab`](https://github.com/raoulmoise/homelab) project.
