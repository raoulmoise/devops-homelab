# 🖥️ Proxmox Setup

This folder contains installation notes, configurations, and VM layouts for my **Proxmox VE homelab**.  
The goal is to simulate production-like infrastructure by separating workloads into dedicated VMs.

---

## 📂 Files
- **install.md** → Step-by-step installation of Proxmox VE  
- **post-install.md** → Initial configuration (storage, network, users)  
- **vm-layout.md** → List of VMs, roles, and resource allocation  

---

## 🧩 Why Proxmox?
- Centralized VM management via web UI  
- Easy snapshot and backup handling  
- Flexible storage options (SSD for VMs, HDD RAID for data)  
- Great for testing **automation with Ansible**  

---

## 🚀 Current VM Plan
- **VM1:** Ubuntu Server – Docker (Homepage, Portainer) 
- **VM2:** Monitoring – Prometheus & Grafana  
- **VM3:** Security – SNMP, Suricata, Firewall tools  
- **VM4+:** Future experiments  

---
