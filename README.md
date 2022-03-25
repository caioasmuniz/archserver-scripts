# archserver-scripts
  This is a collection of scripts I use on my **Arch Linux** home server.

- ## docker-compose
  This is a docker-compose file to deploy the following services on the local network, the docker images used are from [Linuxserver.io](https://www.linuxserver.io/), you can find extra instructions on the image's linked Docker Hub.
  - #### [Heimdall](https://heimdall.site/) ([DockerHub](https://hub.docker.com/r/linuxserver/heimdall))
    -  **config**: `~/.config/heimdall`
    -  **ports**: tcp:80 tcp:443 (dashboard)
  - #### [Home-assistant](https://www.home-assistant.io/) ([DockerHub](https://hub.docker.com/r/linuxserver/homeassistant))
    -  **config**: `~/.config/home-assistant`
    -  **ports**: tcp:8123 (dashboard)
  - #### [Nextcloud](https://nextcloud.com/) ([DockerHub](https://hub.docker.com/r/linuxserver/nextcloud))
    -  **config**: `~/.config/nextcloud`
    -  **ports**: tcp:8081 (dashboard)
    -  **volumes**: `~/nextcloud-data` (file storage location)
  - #### [Transmission](https://transmissionbt.com/) ([DockerHub](https://hub.docker.com/r/linuxserver/transmission))
    -  **config**: `~/.config/transmission`
    -  **ports**: tcp:51413, udp:51413 (torrenting); tcp:8081 (dashboard)
    -  **volumes**: `~/library/torrent` (downloads location)
  - #### [Prowlarr](https://github.com/Prowlarr/Prowlarr) ([DockerHub](https://hub.docker.com/r/linuxserver/prowlarr))
    -  **config**: `~/.config/prowlarr`
    -  **ports**: tcp:9696 (dashboard)
  - #### [Radarr](https://github.com/Radarr/Radarr) ([DockerHub](https://hub.docker.com/r/linuxserver/radarr))
    -  **config**: `~/.config/radarr`
    -  **ports**: tcp:7878 (dashboard)
    -  **volumes**: `~/library` (content location)
  - #### [Lidarr](https://github.com/Lidarr/Lidarr) ([DockerHub](https://hub.docker.com/r/linuxserver/lidarr))
    -  **config**: `~/.config/lidarr`
    -  **ports**: tcp:8686 (dashboard)
    -  **volumes**: `~/library` (content location)
  - #### [Sonarr](https://github.com/Sonarr/Sonarr) ([DockerHub](https://hub.docker.com/r/linuxserver/sonarr))
    -  **config**: `~/.config/sonarr`
    -  **ports**: tcp:8989 (dashboard)
    -  **volumes**: `~/library` (content location)
  - #### [Jellyfin](https://jellyfin.org/) ([DockerHub](https://hub.docker.com/r/linuxserver/jellyfin))
    -  **config**: `~/.config/jellyfin`
    -  **ports**: tcp:9696 (dashboard); tcp:7359 udp:7359 (device discovery)
    -  **volumes**: `~/library/media` (content location)
  ### *Arr suite (Prowlarr, Radarr, Sonarr, Lidarr)
    - These torrent collection managers are configured following the folder structure detailed in this guide on [Servarr Wiki](https://wiki.servarr.com/en/docker-guide), in this case, the *data* directory is stored in `~/library`
    - The **transmission** contatainer has access to the subfolder `~/library/torrents`  
    - The **Jellyfin** contatainer has access to the subfolder `~/library/media`  