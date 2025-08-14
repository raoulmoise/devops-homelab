# 📥 qBittorrent Docker Setup

qBittorrent is a lightweight, full-featured BitTorrent client with a clean web interface.  
This guide documents how I deployed it in Docker with persistent storage and optional port exposure.

---

## 🔧 Features

- Web UI for managing downloads
- Torrent queueing, filtering, speed limits
- Optional password authentication
- Custom data storage path
- Ideal for homelab with attached storage

---

## 🧱 Folder Structure

<img width="528" height="39" alt="image" src="https://github.com/user-attachments/assets/f71f55bd-bba4-4e66-809a-175b448550e5" />

---

## ⏳ Installation

qBittorrent was installed using the Docker Compose file provided by [linuxserver](https://hub.docker.com/r/linuxserver/qbittorrent) and modified to suit my homelab environment.

---

## 🐳 Docker Compose File

---

```yaml
version: "3.8"
services:
  qbittorrent:
    image: lscr.io/linuxserver/qbittorrent:latest
    container_name: qbittorrent
    environment:
      - PUID=1000
      - PGID=1000
      - TZ=Europe/Bucharest
      - WEBUI_PORT=8080
      - TORRENTING_PORT=6881
    volumes:
      - ./config:/config
      - /raid/Torrents:/downloads
    ports:
      - 8080:8080
      - 6881:6881
      - 6881:6881/udp
    restart: unless-stopped
```
---

⚙️ The volumes for downloading the files were put on the RAID1 setup I have on my PC.

After the docker-compose.yaml file was created, we have to run the following command: **docker compose up -d**

## 🔐 Accessing the UI

Visit: HTTP://<your-ip>:8080
Default login:
  - Username: admin
  - Password: a temporary password was generated

We can check the password using the following command: **sudo docker logs *container-id***

<img width="933" height="699" alt="image" src="https://github.com/user-attachments/assets/2acae4e8-1ee8-433c-ad69-556c58fa84d0" />

## 🧠 Tips

- Use the Homepage dashboard to link and monitor this service

> This is part of my larger [`homelab`](https://github.com/raoulmoise/homelab)


