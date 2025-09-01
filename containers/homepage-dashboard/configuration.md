# 🏠 Homepage Configuration Files
  
This guide documents how I configured the different YAML files needed for the customization of the dashboard.

---

## Homepage structure

There are multiple configuration files that **Homepage** Docker is using:
- **services.yaml** defines the apps and links shown on the dashboard
- **bookmark.yaml** list of non-service links (docs, tools)
- **settings.yaml** controls look and global options
- **widgets.yaml** adds live panels (CPU, RAM, weather)
-  **docker.yaml** connects to your Docker socket or API

For my dashboard, I have used the following files listed below.

---

## 📦 Services.yaml

```yaml
---
# For configuration options and examples, please see:
# https://gethomepage.dev/configs/services/

- Tools:
    - Portainer:
        icon: https://cdn.jsdelivr.net/gh/homarr-labs/dashboard-icons/png/portainer-dark.png
        href: https://192.168.1.240:9443/#!/home
        description: Portainer
    - ChatGPT:
        icon: https://cdn.jsdelivr.net/gh/homarr-labs/dashboard-icons/png/chatgpt.png
        href: https://chatgpt.com/
        description: ChatGPT
- Media:
    - qBittorent:
        icon: https://cdn.jsdelivr.net/gh/homarr-labs/dashboard-icons/png/qbittorrent.png
        href: http://192.168.1.240:8080
        description: qBittorent
    - Plex:
        icon: https://cdn.jsdelivr.net/gh/homarr-labs/dashboard-icons/png/plex-light.png
        href: http://192.168.1.240:32400/web/
        description: Plex
- Social:
    - LinkedIn:
        icon: https://cdn.jsdelivr.net/gh/homarr-labs/dashboard-icons/png/linkedin.png
        href: https://www.linkedin.com/feed/
        description: LinkedIn
    - GitHub:
        icon: https://cdn.jsdelivr.net/gh/homarr-labs/dashboard-icons/png/github-light.png
        href: https://github.com/raoulmoise
        description: GitHub
    - Gmail:
        icon: https://cdn.jsdelivr.net/gh/homarr-labs/dashboard-icons/png/gmail.png
        href: https://mail.google.com/mail/u/0/?pli=1#inbox
        description: Gmail
    - YouTube:
        icon: https://cdn.jsdelivr.net/gh/homarr-labs/dashboard-icons/png/youtube.png
        href: https://www.youtube.com/
        description: YouTube
    - WhatsApp:
        icon: https://cdn.jsdelivr.net/gh/homarr-labs/dashboard-icons/png/whatsapp.png
        href: https://web.whatsapp.com/
        description: WhatsApp
    - DNSC:
        icon: https://cdn.jsdelivr.net/gh/homarr-labs/dashboard-icons/png/nextdns.png
        href: https://www.dnsc.ro/
        description: DNSC
    - TheHackerNews:
        icon: https://cdn.jsdelivr.net/gh/homarr-labs/dashboard-icons/png/nextcloud-news.png
        href: https://thehackernews.com/
        description: TheHackerNews
    - Reddit:
        icon: https://cdn.jsdelivr.net/gh/homarr-labs/dashboard-icons/png/reddit.png
        href: https://www.reddit.com/
        description: Reddit
    - Roadmap:
        icon: https://cdn.jsdelivr.net/gh/homarr-labs/dashboard-icons/png/broadcastchannel.png
        href: https://roadmap.sh/devops
        description: RoadMap
```

- In the **Icon** field, you place the icon you want for the specific service
- In the **Href** field, you place the IP of the service
  
---


## 📦 Settings.yaml

```yaml
---
# For configuration options and examples, please see:
# https://gethomepage.dev/configs/settings/

title: Labops

background:
  image: https://images-assets.nasa.gov/image/carina_nebula/carina_nebula~medium.jpg
  blur: sm # sm, md, xl... see https://tailwindcss.com/docs/backdrop-blur
  saturate: 100 # 0, 50, 100... see https://tailwindcss.com/docs/backdrop-saturate
  brightness: 50 # 0, 50, 75... see https://tailwindcss.com/docs/backdrop-brightness
  opacity: 100 # 0-100

theme: dark
color: slate

layout:
  Media:
    header: true
    style: row
    columns: 4
  Social:
    header: true
    style: row
    columns: 4

providers:
  openweathermap: openweathermapapikey
  weatherapi: weatherapiapikey

```

- In the **Title** field, you place the name of your tab and dashboard
  
<img width="205" height="31" alt="image" src="https://github.com/user-attachments/assets/b87ed757-78ef-42cb-9d0c-9d0d05b1d5b6" />

- In the **Background** field, you place your specific image, and also some different configurations for it
- In the **Layout** field, you organize your services and widgets' layout
  
---

## Widgets.yaml

```yaml

---
# For configuration options and examples, please see:
# https://gethomepage.dev/configs/info-widgets/

- resources:
    cpu: true
    memory: true
    disk: /

- search:
    provider: duckduckgo
    target: _blank

- datetime:
    text_size: xl
    format:
      timeStyle: short


```

---

<img width="1861" height="1028" alt="image" src="https://github.com/user-attachments/assets/f387f75a-1e88-4907-ad16-964a2e697a1a" />


> This is part of my larger [`homelab`](https://github.com/raoulmoise/homelab)

