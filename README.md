# Docker Cloud

Different directories with interesting stacks for the deployment with docker
swarm.

## Configuration

In all stacks, copy the file `env.sample` to `.env` and make the appropriate
changes.

There will be a `README.md` in complex stacks to configure.

## Compilation and Start up

After each modification of the `.env` file, the `make` command must be executed
to generate the `docker-compose.yaml` file.

With the `docker-compose.yaml` generated, execute this command for start up de
stack:

```
docker stack deploy -c docker-compose.yaml <STACK_NAME>
```