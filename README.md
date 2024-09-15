# Certbot Proxy Docker example
This docker compose example sets up a Docker based configuration with Nginx, certbot and certbot_proxy.

## Prerequisite
- Docker and docker compose must be installed
- The instance must be public reachable on port 80 and 443
- There must be a DNS pointer to the public address for the SERVER_NAME
- Modify `.env` so it fits your setup

## Setup
Modify `.env` so it fits your setup.

Run `./init-letsencrypt.sh`, this will start nginx with a dummy certificate and then try to install a LetsEncrypt certificate for the SERVER_NAME.

Run `docker compose up -d` for starting the rest of the docker instances in the background.