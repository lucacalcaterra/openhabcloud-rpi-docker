
# openhabcloud-rpi-docker

This is an arrangement of docker-compose (ARM images) for running openhab cloud instance on your ARM device (Raspberry, TinkerBoard,etc.) 

Currently tested on my instance , with Raspberry and Asus Tinkerboard

It's not so wide tested, so...Feel to open new issues and ask if you have troubles.

## How to launch

Clone the repo using --recurse-submodules (the repo contain reference to openhab-cloud):

 1. **git clone --recurse-submodules https://github.com/lucacalcaterra/openhabcloud-rpi-docker.git**
 2. Copy  docker-compose.yml.EXAMPLE to docker-compose.yml and change  variables refer to your domain and changing with your openhab server port
 3. Copy openhabcloud_nginx.conf.EXAMPLE to openhabcloud_nginx.conf and change variables refer to your    domain
 4. launch with **docker-compose up -d** 

*Check docker logs , if have troubles open an issue on the repo.*


@ 2019 - Luca Calcaterra 
