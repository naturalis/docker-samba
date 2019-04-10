docker-samba
====================

Docker compose file for running samba fileserver, using naturalis/samba-join-ad container

Persistent volumes
 - "/data:/data"  

Contents
-------------
samba_ad_join dockerfile, from: https://github.com/fjudith/docker-samba-join-ad 
custom build since dockerhub container did not have version numbers. 


Instruction running docker-compose.yml
-------------

#### preparation
- Copy env.template to .env and adjust variables. 

````
docker-compose up -d
````

Usage
-------------

````


````

