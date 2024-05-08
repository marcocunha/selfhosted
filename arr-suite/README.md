# Docker stack consisting of various arr-services:
TV shows and movies download, sorted, with the desired quality and subtitles, behind a VPN, ready to watch, in a beautiful media player. All automated.

```
!Attention! I do not encourage/support piracy, this is for information only.
```

## Overview
This is composed of multiple tools working together to have an automated way to monitor and watch your favourite TV Shows and Movies.

**Downloaders**:
- [Gluetun](https://github.com/qdm12/gluetun-wiki) (optional but highly recommended): Used for establishing an openvpn/wireguard killswitch vpn connection for  qbittorrent. It requires an active subscription for a vpn provider
- [Qbittorrent](https://docs.linuxserver.io/images/docker-qbittorrent/)
Used as download client; run behind gluetun vpn killswitch container.
- [Prowlarr](https://prowlarr.com/): is an indexer manager/proxy built on the popular *arr .net/reactjs base stack to integrate with your various PVR apps. Prowlarr supports the management of both Torrent Trackers and Usenet Indexers.
- [Bazarr](https://www.bazarr.media/) is a companion application to Sonarr and Radarr. It manages and downloads subtitles based on your requirements. You define your preferences by TV show or movie and Bazarr takes care of everything for you.

**Download orchestration**:

- [Sonarr](https://sonarr.tv): manage TV show, automatic downloads, sort & rename
- [Radarr](https://radarr.video): basically the same as Sonarr, but for movies
- [Lidarr](https://github.com/lidarr/Lidarr): Lidarr is a music collection manager for Usenet and BitTorrent users
- [Readarr](https://github.com/Readarr/Readarr): Readarr is an ebook and audiobook collection manager for Usenet and BitTorrent users

**Media Center**:

- [Emby](https://emby.media/): Emby organizes video, music, live TV, and photos from personal media libraries and streams them to smart TVs, streaming boxes and mobile devices.

**Optional**:
- [Flaresolverr](https://github.com/FlareSolverr/FlareSolverr) FlareSolverr is a proxy server to bypass Cloudflare and DDoS-GUARD protection. Used to bypass Cloudflare for prowlarr. It must be added to prowlarr as indexer with the tag flaresolverr
- [Jellyseerr](https://github.com/Fallenbagel/jellyseerr) Jellyseerr is a free and open source software application for managing requests for your media library. It is a fork of Overseerr built to bring support for Jellyfin & Emby media servers!


### The following bind mount volumes are used:

```/arr-suite/configs/<container-name>```
Holds the config files of an arr container

```/arr-suite/media/```
Holds the media files such as movies, music, books, tv-shows, qbittorrent downloads etc.

#### Resources
- [Arr-Suite example docker compose](https://github.com/Haxxnet/Compose-Examples/tree/main/examples/arr-suite)
- [Quick Arr Stack](https://github.com/Rick45/quick-arr-Stack)