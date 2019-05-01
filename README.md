docker-openvas
====================

Docker compose file and docker file for running openvas based on mikesplain/openvas:9 container

Persistent volumes for openvas
 - "/data/openvas:/var/lib/openvas/mgr"  

for nginx / ssl
 - "/etc/letsencrypt:/etc/letsencrypt"

webserver runs on port 443
openvas exposed directly on port 8443
logrotation is enabled for all containers
daily update of nvt's are managed by the deck-chores container

Contents
-------------


Instruction running docker-compose.yml standalone
-------------

#### preparation
- Copy env.template to .env and adjust variable to set admin password, base_path and public hostname. 
- edit ssl certificate locations in nginx_ssl.conf to point to valid certificate. 

#### start compose project
````
docker-compose up -d
````

#### Remarks for usage with puppet-docker_compose in foreman. 

Certificate locations nginx_ssl.conf in repository must match correct SSL certificate locations, this can currently not be managed by environment variables which is not best practice but currently acceptable.






