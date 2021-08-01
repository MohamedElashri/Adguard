[![Build Status](https://app.travis-ci.com/MohamedElashri/Adguard.svg?branch=main)](https://app.travis-ci.com/MohamedElashri/Adguard)
[![MIT License](https://img.shields.io/apm/l/atomic-design-ui.svg?)](https://github.com/tterb/atomic-design-ui/blob/master/LICENSEs)
[![Multi Platform Build & Push to Dockerhub](https://github.com/MohamedElashri/Adguard/actions/workflows/docker_image.yml/badge.svg)](https://github.com/MohamedElashri/Adguard/actions/workflows/docker_image.yml)

# Adguard
 Unofficial  docker image for Adguard for personal use

Official Docker Image for AdGuardHome here - https://hub.docker.com/r/adguard/adguardhome

AdGuard Home is a network-wide software for blocking ads & tracking. After you set it up, It will cover all your home devices with the need for a client apps. 

![AdGuardHome](https://raw.githubusercontent.com/MrKsey/AdGuardHome/master/adh.PNG)


## Image features

* Small container size (about 100 MB)
* Image size itself is ~ 40 MB
* Low memory usage (~ 128 MB) 

## Installation

* docker host ip (for example) - 100.100.1.10 .
* create ```/AdGuardHome``` directory on your docker host for configuration files, filters and data.
* create container from docker image "ksey/adguardhome", connect host ```/home/AdGuardHome``` directory to the container directory ```/opt/AdGuardHome/data``` and start container.

Example:
```
docker pull ksey/adguardhome
docker run --name AdGuardHome -d -p <ip>:53:53/udp -p <ip>:53:53/tcp -p 3000:3000 -v /AdGuardHome:/opt/AdGuardHome/data --restart always melashri/adguardhome
```

* Open the browser and navigate to http://<ip>:3000/ to control your AdGuardHome service.
* When you run AdGuard Home for the first time, there is a simple configuration wizard.
* Remember to set "Admin Web Interface" port to 3000.
* AdGuardHome DNS works on <ip>, default port 53.
* Edit file ```/AdGuardHome/AdGuardHome.yaml``` (on the host) to change the password and other parameters.

## License

Available under [the MIT license](https://github.com/MohamedElashri/ME-Resume/blob/Main/LICENSE.md).
