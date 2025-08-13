# Ubuntu Server Installation Guide

This document covers a clean installation of **Ubuntu Server** (24.04 LTS) on bare metal.

---

## 🛠️ Pre-Installation Checklist

-  USB drive (at least 4GB)
-  Ubuntu Server ISO: [https://ubuntu.com/download/server](https://ubuntu.com/download/server)
-  Tool to write ISO to USB (Rufus)

---

## 1. 💾 Writing ISO to USB (Optional but Recommended)

1. Download [Rufus](https://rufus.ie/en/)
2. Write the ISO to USB

<img width="461" height="570" alt="image" src="https://github.com/user-attachments/assets/1df480db-9169-452d-83b0-6185b49e811b" />

---

## 2. 💻 Boot into Installer

1. Insert the bootable USB and restart the machine  
2. Select "Try or Install Ubuntu Server"

<img width="635" height="398" alt="image" src="https://github.com/user-attachments/assets/1e4280d4-b138-4665-8950-f514b38ec546" />

## 3. 🗣️ Select the language

Select the language you want to use and the keyboard layout

<img width="676" height="109" alt="image" src="https://github.com/user-attachments/assets/da939383-a8cd-4aee-93df-ffbe55fb22bf" />

---

## 3. 🌐 Network Configuration

Configure the IP Address of the PC;

<img width="585" height="376" alt="image" src="https://github.com/user-attachments/assets/d3d019a0-bb19-4203-9f03-06972fba5042" />

- Choose the correct network interface (usually `enpXs0` or `eth0`)
- For homelab setups: choose **Manual IP**

---

## 4. 🗃️ Storage Setup

- For my homelab, I have used the automatically assigned storage on the main SSD
- I have added the X2 1TB HDD configured as RAID1, mounted separetly
- Always **encrypt** the storage

---

## 5. 👤 User Configuration

- Create a primary user (e.g., `user1`)
- Choose a strong password
- Set hostname (e.g., `pc1`)
  
 <img width="880" height="331" alt="image" src="https://github.com/user-attachments/assets/5ae1aab3-a2e9-4f96-b52e-a99490d99349" />

---

## 6. ⬇️ Package Selection

- Enable **OpenSSH server** (checked by default)
- Skip other snaps unless needed

---

## 7. 🧼 Post-Install Cleanup (optional)

- Eject USB and reboot
- Login with your user credentials
- Run the following commands:
    1. sudo systemctl mask sleep.target suspend.target hibernate.target hybrid-sleep.target
    2. sudo apt update && sudo apt upgrade -y
