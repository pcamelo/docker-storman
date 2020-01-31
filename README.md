# fish2/docker-storman
[![](https://images.microbadger.com/badges/image/fish2/docker-storman.svg)](https://microbadger.com/images/fish2/docker-storman "Get your own image badge on microbadger.com")

**Purpose**
Container running the Adaptec Maxview Storage Manager application and the necessary daemons.

With this container, you can manage an Adaptec RAID adapter on the dockerhost. It is based on Ubuntu from phusion/baseimage and Adaptec MSM version V3.03-23668

It should be run with --privileged, in order to have access to the hardware and insert the necessary kernel modules.

**Create Command**
Listening on port 8443 (user=root, password=docker):

	docker create --name=storman --hostname=storman --privileged -e TZ=<timezone> -e PGID=1000 -e PUID=1000 -p 8443:8443/tcp fish2/docker-storman

**Build with Custom Password**
Build first edditing the password arg

	docker build https://raw.githubusercontent.com/Fish2/docker-storman/master/Dockerfile -t fish2/docker-storman --build-arg password={your password here}
