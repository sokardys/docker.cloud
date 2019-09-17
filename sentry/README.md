# Sentry Stack

With backup on Amazon S3 and emails with Amazon SES

**IMPORTANT: Docker must have a minimum of 3Gb of RAM available for execute the migration**

The first time after starting the stack as usual:

`docker stack deploy -c docker-compose.yaml sentry`

We connected to `sentry_server` to execute the migration:

`docker exec -it <id_sentry_server> sentry upgrade`

After a long migration procedure, information is requested for the creation of a new user. **It's important to create it**
