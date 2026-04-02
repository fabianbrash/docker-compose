# docker-compose

#### We need to create our network and if this is your first tine running n8n create a volume


````
docker network create traefik-public
docker volume create n8n_data

````


#### We also need to setup a few things for traefik

````
sudo mkdir -p /opt/traefik/certs
sudo touch /opt/traefik/dynamic_conf.yml
````

````
sudo vim /opt/traefik/dynamic_conf.yml
````

```Contents of /opt/traefik/dynamic_conf.yml```


````
tls:
  certificates:
    - certFile: /certs/wildcard.crt
      keyFile: /certs/wildcard.key
````


##### You obviously need to add your cert and key to the above and then

````
sudo chmod 600 /opt/traefik/certs/wildcard.key
````
