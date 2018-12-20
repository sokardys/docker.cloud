# Traefik Stack

Traefik is an inverse proxy capable of listen changes in docker and configure
routing of deployed services

## Configuration

Copy the file `env.sample` to `.env` and make the appropriate changes:

- TRAEFIK_VERSION**: Traefik version to deploy.
- TRAEFIK_ACME_EMAIL**: Contact email to configure in Let's Encrypt.
- TRAEFIK_BASIC_AUTH**: Basic Auth to use, result of the command:
`echo $(htpasswd -b <user> <password>) | sed s/e s/$/\\$$/g`
- TRAEFIK_DOMAIN**: Domain to be used for Traefik UI

### SSL certificate settings

Just by indicating a contact email in the configuration and copying a file, the
stack is already able to to work with Let's Encrypt.

Even if Let's Encrypt is configured, you can use certificates from other
providers.

#### Use Let's Encrypt (https://letsencrypt.org/)

This is the default pre-configuration of the stack.
Only must copy the file `acme.sample.json` with the name `acme.json` and
restrict access to the file with `chmod 600 acme.json`

#### Use other providers

Uncomment lines 33 and 59 of the file.
Divide the certificate in two files: one with the complet certificate stack
(.cert) and one with the private key (.key) and place them in the `./certs`
directory.

Change line 33 according to the names of the generated files. The .cert and .key
files are separated by commas (**,**) and the various semicolon domains (**;**)

## Compilation and Start up

After each modification of the `.env` file, the `make` command must be executed to generate the `docker-compose.yaml` file.

With the `docker-compose.yaml` generated, execute this command for start up de stack:

```
docker stack deploy -c docker-compose.yaml traefik
```

