# 🏠 Homepage Dashboard Setup
  
This guide documents how I deployed it in Docker using a simple volume bind and default configuration.

---

## 📦 What is Homepage?

"A modern, fully static, fast, secure, fully proxied, highly customizable application dashboard with integrations for over 100 services and translations into multiple languages. 
Easily configured via YAML files or through Docker label discovery."

Dashboard allows you to:
- Quickly access local apps (Portainer, qBittorrent, Grafana, etc.)
- Monitor container health, system info, and external services
- Customize layout, icons, sections, and widgets

🔗 Project site: [https://gethomepage.dev/](https://gethomepage.dev/)

---

## 🧱 Folder Structure

<img width="510" height="37" alt="image" src="https://github.com/user-attachments/assets/86886ea9-903b-4c8f-9c3a-14e4478464a7" />

## ⏳ Installation

The Homepage Dashboard was installed using the Docker Compose file provided by [homepage](https://gethomepage.dev/installation/docker/) and modified to suit my homelab environment.

---

## 🐳 Docker Compose File

---
```yaml
services:
  homepage:
    image: ghcr.io/gethomepage/homepage:latest
    container_name: homepage
    ports:
      - 3000:3000
    volumes:
      - ./config:/app/config # Make sure your local config directory exists
     # - /var/run/docker.sock:/var/run/docker.sock # (optional) For docker integrations, see alternative methods
    environment:
      HOMEPAGE_ALLOWED_HOSTS: <YOUR-IP-ADDRESS> # required, may need port. See gethomepage.dev/installation/#homepage_allowed_hosts
      PUID: 1000
      PGID: 1000
```
---

## 🔐 Accessing the UI

Visit: HTTP://your-ip>:3000

<img width="1779" height="975" alt="image" src="https://github.com/user-attachments/assets/8bafcf6e-faca-472c-ad20-a549d20da586" />


## 🧠 Tips

- You can configure your Dashboard using the different .yaml files provided by the container

> This is part of my larger [`homelab`](https://github.com/raoulmoise/homelab)

