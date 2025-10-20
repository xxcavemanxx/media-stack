# 🎬 Media Automation Stack

This project is a modular, reproducible Docker Compose stack for managing media acquisition, optimization, and playback. It integrates Sonarr, Radarr, Prowlarr, Tdarr, Emby, Traktarr, Buildarr, Recyclarr, ArrEm-sync, and Homarr into a unified ecosystem.

---

## 🧩 Included Services

| Service       | Role                                                                 |
|---------------|----------------------------------------------------------------------|
| Sonarr        | TV show management and acquisition                                   |
| Radarr        | Movie management and acquisition                                     |
| Prowlarr      | Indexer aggregation and search routing                               |
| Tdarr         | Transcoding and media health automation                              |
| Emby          | Media server frontend with user profiles and playback                |
| Traktarr      | Syncs Trakt.tv lists into Sonarr/Radarr                              |
| Buildarr      | Declarative config management for Sonarr/Radarr/Prowlarr             |
| Recyclarr     | Syncs TRaSH-Guides profiles and custom formats                       |
| ArrEm-sync    | Syncs Sonarr/Radarr tags into Emby metadata                          |
| Homarr        | Dashboard for service visibility and quick access                    |

---

## 🧱 Setup Instructions

1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/media-stack.git
   cd media-stack
   ```

2. Create a `.env` file using the provided template:
   ```bash
   cp .env.example .env
   ```

3. Fill in your API keys and adjust paths as needed.

4. Launch the stack:
   ```bash
   docker compose up -d
   ```

---

## 📁 Folder Structure

```
media-stack/
├── .env
├── .gitignore
├── docker-compose.yml
├── README.md
├── config/
│   ├── sonarr/
│   ├── radarr/
│   ├── prowlarr/
│   ├── tdarr/
│   ├── homarr/
│   ├── emby/
│   ├── traktarr/
│   ├── buildarr/
│   ├── recyclarr/
│   └── arrem/
├── data/
│   ├── tv/
│   └── movies/
├── downloads/
├── transcode_cache/
└── icons/
```

---

## 🔁 Automation Highlights

- **Traktarr**: Syncs Trakt.tv lists into Sonarr/Radarr every 6 hours
- **Recyclarr**: Syncs TRaSH-Guides profiles daily
- **ArrEm-sync**: Updates Emby tags from Sonarr/Radarr every 12 hours
- **Tdarr**: Transcodes new media and maintains health
- **Buildarr**: Watches config files and applies changes automatically
- **Homarr**: Displays live status widgets and links to all services

---

## 🧠 Notes

- All containers share a `media_net` Docker network for seamless communication
- Volumes are labeled for clarity and backup automation
- Homarr auto-discovers services and supports custom icons
- Emby scans optimized media from Tdarr and receives tags via ArrEm-sync
- Recyclarr ensures TRaSH-compliant quality and format scoring

---

## 📜 License

MIT