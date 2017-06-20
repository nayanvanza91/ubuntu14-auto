# ubuntu14-auto
#### Docker Container - Ubuntu Server 14.04 LTS (Trusty Tahr).

This Docker container gears with the basic dependency packages installation and foremost effort is on autostart system services on container, while the host system restart or docker service restart.

Includes the following system components:
* SSH
* cron
* git
* rsync
* vim

Contains system services are autostart:
* SSH
* cron

Installation from [Docker registry hub] (https://hub.docker.com/r/nayanvanza91/ubuntu14-auto/).
----

You can download the image using the following command:

```bash
  docker pull nayanvanza91/ubuntu14-auto
```

This image has exposes essential ports for development application configuration.
#### ports `22`, `80`, `3306`, `8080`, `9200` 

This expose ports are used to enable varnish, elasticsearch.  
Also, we can map our container drive to host machine and secure our data.

### Use cases
----
#### Lauch Container with name as server.
docker run –i –t –d --hostname server --name server nayanvanza91/ubuntu14-auto
#### Lauch Container with name as server and map ports.
docker run –i –t –d --hostname server -p 1022:22 -p 1080:80 -p 1088:8080 -p 1036:3306 name server nayanvanza91/ubuntu14-auto
#### Lauch Container with name as server and map ports with directory mapping.
docker run –i –t –d --hostname server -p 1022:22 -p 1080:80 -p 1088:8080 -p 1036:3306 -v /srv/project/webroot:/var/www/html name server nayanvanza91/ubuntu14-auto
