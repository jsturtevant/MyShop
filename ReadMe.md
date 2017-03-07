# Docker Compose Example
Learn more about Docker Compose at [https://docs.docker.com/compose/](https://docs.docker.com/compose/).

## Run using compose
To run this sample clone the repository and then run:

```cmd
docker-compose -f src\docker-compose.local.yml up
```

You can now browse to http://localhost:8080/.

### Remove containers from docker
Run:

```cmd
docker-compose -f src\docker-compose.local.yml down
```

This removes all the running docker containers and cleans up the resources according the compose file.

## Credit
This is a fork of [jcorioland/MyShop](https://github.com/jcorioland/MyShop) that has modified.