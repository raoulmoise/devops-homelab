# 🐳 Portainer Setup
  
This guide documents how I deployed Portainer in Docker using a simple volume bind and default configuration.

---

## 📦 What is Portainer?

"Portainer Community Edition is a lightweight service delivery platform for containerized applications that can be used to manage Docker, Swarm, Kubernetes and ACI environments.
 It is designed to be as simple to deploy as it is to use. 
 The application allows you to manage all your orchestrator resources (containers, images, volumes, networks and more) through a ‘smart’ GUI and/or an extensive API."

Portainer allows you to:
- Deploy and manage containers, images, volumes, and networks
- Monitor container health and logs
- Manage access control and multiple environments
- Simplify updates and upgrades for services

🔗 Project site: [https://www.portainer.io/](https://www.portainer.io/)

---

## 🧱 Folder Structure
/home/labops/docker_volumes/portainer/

└── docker-compose.yml

└── data/

---

## ⏳ Installation

Portainer was installed using a custom Docker Compose file, adapted to my homelab environment.  
Persistent data is stored under `/home/labops/docker_volumes/portainer/data`.

---

## 🐳 Docker Compose File

```yaml
version: "3.9"
services:
  portainer:
    image: portainer/portainer-ce:latest
    container_name: portainer
    restart: always
    ports:
      - "9443:9443"   # HTTPS Web UI
      - "8000:8000"   # Optional Edge agent tunnel
    volumes:
      - /var/run/docker.sock:/var/run/docker.sock
      - /home/labops/docker_volumes/portainer/data:/data
```

---

# 🔐 Accessing the UI

Visit: [https://<your-ip>:9443](https://<your-ip>:9443)  

On first login, you will be prompted to create an **admin user**.

---

# 🧠 Tips

### Updating Portainer
```bash
cd /home/labops/docker_volumes/portainer
docker compose pull
docker compose up -d
```

---

## 🚧 Status

🟢 Actively maintained as part of my [`homelab`](https://github.com/raoulmoise/homelab) project.

---
