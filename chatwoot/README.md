# Traefik Stack

Manage conversations, build relationships and delight your customers, all from one place.

## Configuration

Copy the file `.env.example` to `.env` and make the appropriate changes.

### Deploying the stack
Once fully deployed then go to the `app` instance with the following command:
```yaml
 docker exec -it  <STACK_ID> sh 
```

Then, run the following command to trigger the db seeding process:
`bundle exec rails db:reset`

Now you are good to go!
