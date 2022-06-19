# Orthanc rapid PACS setup

My rapid setup to have security friendly PACS system.

## Elements

- Orthanc, easy to use PACS :   [Official site](https://www.orthanc-server.com/)
- Caddy, simple web server :    [Official site](https://caddyserver.com/)
- Docker, service container :   [Official site](https://www.docker.com/)

## Documentation

- Orthanc : https://www.orthanc-server.com/static.php?page=documentation
- Caddy :   https://caddyserver.com/docs/
- Docker :  https://docs.docker.com/

## Goal

The `docker-compose.yml` sets up a Orthanc container (the one with plugin), and a Caddy webserver as a reverse proxy.

## Steps

Edit the `Caddyfile` :
- Line 1 :  add your domain name.
- Line 2 :  add the IPs you want to be able to access Orthanc

Edit the `orthanc.json`
- Line 237 : Set a password for the _vip_ user 

> Note that Caddy must be available from internet on port 80/TCP and 443/TCP.<br />It will be able yto get SSL certificates from ZeroSSL or Let's Encrypt.

Launch containers :
```bash
sudo docker-compose up -d
```

## Downside
- This setup is not meant for heavy load, you should consider using a database, and have a plan
- Use it at **your own risk**
