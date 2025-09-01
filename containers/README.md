# 🐳 Homelab Containerized Services

This folder documents the containerized applications I’ve deployed in my homelab environment using Docker.

---

## 📦 Services

| Service         | Description                        | Setup Guide                             |
|----------------|------------------------------------|------------------------------------------|
| Homepage        | Dashboard & service launcher       | [homepage-dashboard](https://github.com/raoulmoise/homelab/tree/main/containers/homepage-dashboard) |
| qBittorrent     | Lightweight torrent client (web UI)| [qbittorrent](https://github.com/raoulmoise/homelab/tree/main/containers/qbittorrent)     |
| Plex            | Media server software              | [plex](https://github.com/raoulmoise/homelab/tree/main/containers/plex)    |
| Portainer       | Docker container manager GUI       | [portainer](https://github.com/raoulmoise/homelab/tree/main/containers/portainer) |
| Tailscale       | VPN                                | [tailscale](https://github.com/raoulmoise/homelab/tree/main/containers/tailscale)
| Grafana         | Metrics dashboard (planned)        | *(Coming soon)* |
| Prometheus      | Metrics collector (planned)        | *(Coming soon)* |

---

## 🧱 Deployment Notes

- All containers are run using **Docker Compose**
- Configuration files and volumes are stored under `/home/labops/docker_volumes`

---

## 🧠 Why This Exists

- Helps me track my lab service deployments
- Reusable for reinstallations or new nodes
- Part of my DevOps learning documentation

---

## 🚧 Status

<img width="816" height="141" alt="image" src="https://github.com/user-attachments/assets/6e4b192a-4d2b-4e2c-9609-70fa1e6d02df" />


🟢 Actively maintained as part of my [`homelab`](https://github.com/raoulmoise/homelab) project.

---
