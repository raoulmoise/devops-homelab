# 🎬 Plex Media Server (Docker - linuxserver/plex)

This setup uses the official `linuxserver/plex` image with Docker Compose.  
It creates a Plex Media Server instance with persistent storage and media mounts.
What is Plex? | Plex is a media server and streaming service that allows users to organize, stream, and share their personal media collections, as well as access free, ad-supported movies, TV shows, and live TV channels. 

---

## 🔧 Prerequisites
- Docker installed
- Docker Compose installed
- A valid Plex account

---

## ⏳ Installation

1. Clone this repo or copy the `docker-compose.yml` below.
2. Adjust the `PUID`, `PGID`, `TZ`, and volume paths to your system.
3. Run:
   ```bash
   docker compose up -d
4. Access Plex at: http://localhost:32400/web

---

## 🐳 Docker Compose File

```yaml

services:
  plex:
    image: lscr.io/linuxserver/plex:latest
    container_name: plex
    environment:
      - PUID=1000        # user ID
      - PGID=1000        # group ID
      - TZ=Europe/Bucharest
    volumes:
      - ./config:/config 
      - /raid/Torrents:/tv  # /path/to/tv
      - /raid/Torrents:/movies # /path/to/movies
    ports:
      - 32400:32400
    restart: unless-stopped

```

## 🧠 Tips

Replace /path/to/tv and /path/to/movies with your media folders.

Check your PUID and PGID with id <username>.

To update Plex:

``` bash

docker compose pull
docker compose up -d

```
