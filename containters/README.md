# 🐳 Homelab Containerized Services

This folder documents the containerized applications I’ve deployed in my homelab environment using Docker.

Each service includes:
- Purpose and functionality
- Docker Compose or run command
- Volumes, networking, and ports used
- Screenshots or UI previews (if applicable)
- Reverse proxy/access notes (if used)

---

## 📦 Services

| Service         | Description                        | Setup Guide                             |
|----------------|------------------------------------|------------------------------------------|
| Homepage        | Dashboard & service launcher       | [homepage-dashboard.md](./homepage-dashboard.md) |
| qBittorrent     | Lightweight torrent client (web UI)| [qbittorrent.md](./qbittorrent.md)       |
| Portainer       | Docker container manager GUI       | [portainer.md](./portainer.md) *(coming soon)* |
| Grafana         | Metrics dashboard (planned)        | *(Coming soon)*                          |
| Prometheus      | Metrics collector (planned)        | *(Coming soon)*                          |

---

## 🧱 Deployment Notes

- All containers are run using **Docker Compose**
- Configuration files and volumes are stored under `//home/labops/docker_volumes`

---

## 🧠 Why This Exists

- Helps me track my lab service deployments
- Reusable for reinstallations or new nodes
- Part of my DevOps learning documentation

> This is part of my larger [`homelab`](https://github.com/raoulmoise/homelab) project.
