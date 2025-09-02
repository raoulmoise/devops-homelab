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

/home/labops/docker_volumes/homepage/
└── docker-compose.yml
└── config/

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
    restart: unless-stopped
```
---

## 🔐 Accessing the UI

Visit: HTTP://your-ip>:3000

<img width="1898" height="1036" alt="image" src="https://github.com/user-attachments/assets/868bd063-0686-4d13-87fa-e4f0a632d37a" />



## 🧠 Tips

- You can [configure](https://github.com/raoulmoise/homelab/blob/96aa2341308cd4b757560acecb7d355e4446f792/containers/homepage-dashboard/configuration.md) your Dashboard using the different .yaml files provided by the container
- After some testing with my server and some restart, I have noticed that the container does not restart automatically, so I have added this command:
```bash
sudo docker update --restart unless-stopped homepage
```

---

## 🚧 Status

🟢 Actively maintained as part of my [`homelab`](https://github.com/raoulmoise/homelab) project.

---
