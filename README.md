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

logrotate hash for samba services.
```
winbindd:
  log_path: "/var/log/samba/log.winbindd"
  post_rotate: "(cd /opt/docker-samba; docker-compose exec samba bash -c '[ ! -f /var/run/samba/winbindd.pid ] || kill -HUP `cat /var/run/samba/winbindd.pid`')"
  extraline: su root docker
nmbd:
  log_path: "/var/log/samba/log.nmbd"
  post_rotate: "(cd /opt/docker-samba; docker-compose exec samba bash -c '[ ! -f /var/run/samba/nmbd.pid ] || kill -HUP `cat /var/run/samba/nmbd.pid`')"
  extraline: su root docker
smbd:
  log_path: "/var/log/samba/log.smbd"
  post_rotate: "(cd /opt/docker-samba; docker-compose exec samba bash -c '/etc/init.d/smbd reload > /dev/null')"
  extraline: su root docker
```


#### preparation
- Copy env.template to .env and adjust variables. 

````
docker-compose up -d
````

Usage
-------------

````


````

