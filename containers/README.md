# 🐳 Homelab Containerized Services

This folder documents the containerized applications I’ve deployed in my homelab environment using Docker.

---

## 📦 Services

| Service         | Description                        | Setup Guide                             |
|----------------|------------------------------------|------------------------------------------|
| Homepage        | Dashboard & service launcher       | [homepage-dashboard](https://github.com/raoulmoise/homelab/tree/4f24d2abd498cbd578748ce755e7802b76449391/containers/homepage-dashboard) |
| qBittorrent     | Lightweight torrent client (web UI)| [qbittorrent](https://github.com/raoulmoise/homelab/tree/f02641d934cf39acb2e75ea8027a7dcb0558d01a/containers/qbittorrent)     |
| Plex            | Media server software              | [plex](containers/plex)    |
| Portainer       | Docker container manager GUI       | *(coming soon)* |
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

> This is part of my larger [`homelab`](https://github.com/raoulmoise/homelab) project.
