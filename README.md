# Overview
This repo includes the files to set up a MediaWiki installation on
a Raspberry Pi 3 with Docker.

# Database
The config for MediaWiki is set up to use MySQL.  Using a MariaDB
container works if the networking is set up correctly within
docker (but with DHCP swapping IP addresses each time you start up, 
that can be a challenge).  

# Portainer Stack
To make it easier to set up a mini-network with a MariaDB container
networked by DNS the docker-compose.yml file can be used to create
a "stack" in Portainer.  (Portainer is a Docker management console
that also runs in a container.) This also maps some host-volumes to
keep the actual database data files, and the wiki upload directory
out of the container's overlay filesystem.  This can be done manually
but docker compose (i.e. portainer stacks) is easier.

# Notes
* The wiki is configured under a web subdirectory named "/wiki"
* Nginx is configured to kick requests for the root of the web host to the Main_Page


# Docker Hub
* See: https://cloud.docker.com/repository/docker/rthomas67/rpi-mediawiki

