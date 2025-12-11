# HOMARR DASHBOARD
![Project Logo](./img/homarr.png)


media-stack
------------------------------

This repo contains Docker Compose configurations for my media stack:
- Gluetun # uses vpn to hide torrent traffic from isp
- Jellyfin # media server
- Sonarr # manages tv shows
- Radarr # manages movies
- Lidarr # manages music
- qBittorrent # downsloads content
- Jackett # shares indexers with prowlarr
- Prowlarr # manages indexers
- Whisparr # adult movie manager
- Homarr # dashboard for media ARR stack

Reqirements:
------------------------------

This has been tested on Linux based opperating systems. You may need to change file directories and permissions for a different OS.
Must have protonVPN account to hide torrent traffic behind Gluetun from your isp.

Directions:
------------------------------

create and use creditials from protonVPN for vpn to work. In AAR-stack in gluetun look for and replace creditials
 - OPENVPN_USER=add_your_usrname-here
 - OPENVPN_PASSWORD=add_your_password-here

Change your local network. Look for and change to your network ip
- LOCAL_NETWORK=10.0.0.0/24

Addjust time zone as required
- TZ=America/Los_Angeles

- -------------------------

Homarr requires a 64 character sh secret key
Go here to generate one and then add it under homarrs settings. Look for this in docker-compose under homarr
  
  environment:
      - SECRET_ENCRYPTION_KEY=
      
Generate the key here.........

https://secretkeygen.vercel.app/


# Commands for creating and giving folders correct permisions:

Create Media folders ---- Copy and Paste
-------------------------------
sudo mkdir -p /srv/media/downloads && sudo chown -R 1000:1000 /srv/media/downloads && sudo chmod -R 775 /srv/media/downloads
sudo mkdir -p /srv/media/movies && sudo chown -R 1000:1000 /srv/media/movies && sudo chmod -R 775 /srv/media/movies
sudo mkdir -p /srv/media/tv && sudo chown -R 1000:1000 /srv/media/tv && sudo chmod -R 775 /srv/media/tv
sudo mkdir -p /srv/media/music && sudo chown -R 1000:1000 /srv/media/music && sudo chmod -R 775 /srv/media/music

Lidarr ----
-------------------------------
sudo mkdir -p /srv/docker/lidarr/config && sudo chown -R 1000:1000 /srv/docker/lidarr && sudo chmod -R 775 /srv/docker/lidarr

qBittorrent ----
------------------------------
sudo mkdir -p /srv/docker/qbittorrent/config && sudo chown -R 1000:1000 /srv/docker/qbittorrent/config && sudo chmod -R 775 /srv/docker/qbittorrent/config

Jackett ----
------------------------------
sudo mkdir -p /srv/docker/jackett/config && sudo chown -R 1000:1000 /srv/docker/jackett/config && sudo chmod -R 775 /srv/docker/jackett/config

Radarr ----
------------------------------
sudo mkdir -p /srv/docker/radarr/config && sudo chown -R 1000:1000 /srv/docker/radarr/config && sudo chmod -R 775 /srv/docker/radarr/config

Sonarr ----
-----------------------------
sudo mkdir -p /srv/docker/sonarr/config && sudo chown -R 1000:1000 /srv/docker/sonarr/config && sudo chmod -R 775 /srv/docker/sonarr/config

Prowlarr ----
-----------------------------
sudo mkdir -p /srv/docker/prowlarr/config && sudo chown -R 1000:1000 /srv/docker/prowlarr/config && sudo chmod -R 775 /srv/docker/prowlarr/config

Whisparr ----
-----------------------------
sudo mkdir -p /srv/docker/whisparr/config && sudo chown -R 1000:1000 /srv/docker/whisparr/config && sudo chmod -R 775 /srv/docker/whisparr/config
sudo mkdir -p /srv/docker/whisparr/data && sudo chown -R 1000:1000 /srv/docker/whisparr/data && sudo chmod -R 775 /srv/docker/whisparr/data

Homarr ----
-----------------------------
sudo mkdir -p /srv/docker/homarr/data && sudo chown -R 1000:1000 /srv/docker/homarr/data && sudo chmod -R 775 /srv/docker/homarr/data

Jellyfin ----
-----------------------------
sudo mkdir -p /srv/docker/jellyfin/config && sudo chown -R 1000:1000 /srv/docker/jellyfin/config && sudo chmod -R 775 /srv/docker/jellyfin/config

HOW TO DEPLOY
-----------------------------
Run in terminal
---------------
docker-compose up -d --build

If using portainer " Recomended " 
Live veiw-> stacks-> new stack-> 
give name gluetun-gluetunvpn
copy and paste contents of docker-compose into file editor and deploy stack after editing gluetun usrnam and pawwrds




