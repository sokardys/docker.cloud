## Micro-service Stack
* [Traefik](https://hub.docker.com/_/traefik)
* [Postgres](https://hub.docker.com/_/postgres)
* [Bitnami Rabbit](https://hub.docker.com/r/bitnami/rabbitmq/)
* [Rasa NLU](https://hub.docker.com/r/rasa/rasa_nlu)
* [Rasa NGINX](https://hub.docker.com/r/rasa/nginx)
* [Rasa Logger](https://hub.docker.com/r/rasa/logger)
* [Rasa X](https://hub.docker.com/r/rasa/rasa-x)
* [Rasa X Demo](https://hub.docker.com/r/rasa/rasa-x-demo)
* [Rasa Duckling](https://hub.docker.com/r/rasa/duckling)
* [Rasa Core](https://hub.docker.com/r/rasa/rasa_core)

Deployment using [Docker Swarm](https://docs.docker.com/engine/swarm/)


## Getting Started
There are 2 ways of getting started. The quickest + semi-automatic way and the lowest + manal process. On this guidelines we are using the quickest way. Alternatively, you can always go and do the manual set up on [https://rasa.com/docs/rasa-x/deploy/](https://rasa.com/docs/rasa-x/deploy/).

### Semi-Automatic set up
1. Download and run the install script on the server:
```bash
$ curl -sSL -o install.sh https://storage.googleapis.com/rasa-x-releases/stable/install.sh
$ sudo bash ./install.sh
```
Replace stable with a version number if you want to install a specific version. You will be prompted to accept the terms and conditions. Type `YES` and hit `return`.

This will likely install the rasa directory in `/etc/rasa`. 

2. If you are using Rasa X CE, please set your admin password:
```bash
$ cd /etc/rasa
$ sudo python rasa_x_commands.py create --update admin me PASSWORD
```