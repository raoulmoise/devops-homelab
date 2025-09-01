# 🔐 Tailscale Setup

This guide documents how I installed and configured [Tailscale](https://tailscale.com/) on my homelab server to enable secure remote access to my network and services.

---

## 📦 What is Tailscale?

"Tailscale is a zero-config VPN that creates a secure, peer-to-peer mesh network between your devices.  
It’s built on WireGuard and handles NAT traversal automatically, allowing you to connect to your machines anywhere without port forwarding."

Tailscale allows you to:
- Access your homelab from anywhere securely
- Bypass ISP CGNAT or firewall limitations (no public IP required)
- Use a private subnet of **100.x.x.x** addresses for all your devices
- Share specific machines or services with other users
- Manage devices from a central admin dashboard

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

Tailscale was installed using the official Linux instructions:

1. Add Tailscale repository and install:
   ```bash
   curl -fsSL https://tailscale.com/install.sh | sh
   ```
<img width="587" height="36" alt="image" src="https://github.com/user-attachments/assets/583b5df0-b613-4ec6-8481-cc9ac3e403ce" />

2. Start the Tailscale service:
  ```bash
   sudo tailscale up
  ```
<img width="349" height="26" alt="image" src="https://github.com/user-attachments/assets/eb13a9e3-d79e-4166-bbca-c2db7a44ce96" />

3. Authenticate by following the login link in your browser.

<img width="450" height="31" alt="image" src="https://github.com/user-attachments/assets/11aafb19-d0cd-45e5-90bb-096ab1d13957" />

---

## 🔐 Accessing the VPN

Once authenticated, the machine will appear in your Tailscale admin console:
https://login.tailscale.com/admin/machines

---

##🧠 Tips

- Use tailscale ip -4 to check your device’s private VPN address.
- Use tailscale status to see connected peers.
- For SSH access, enable Tailscale SSH
  ```bash
  sudo systemctl enable tailscaled
  ```

---

## 🚧 Status

🟢 Actively maintained as part of my [`homelab`](https://github.com/raoulmoise/homelab) project.

---
