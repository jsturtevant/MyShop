# Docker Compose Example for Swarm Mode
Learn more about Docker Compose at [https://docs.docker.com/compose/](https://docs.docker.com/compose/).  

This example covers how to deploy to Docker Swarm Mode.  Check out the [Tag Compose v2](https://github.com/jsturtevant/MyShop/tree/compose-v2) for example to deploy to Swarm.  Learn the difference between [Swarm Mode and Swarm](https://sreeninet.wordpress.com/2016/07/14/comparing-swarm-swarmkit-and-swarm-mode/).

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

## To deploy to Swarm Cluster (Swarm Mode)
Connect to you Swarm Cluster Master node and run:

```cmd
docker deploy -c src/docker-compose.local.yml myshop
```

This will deploy the compose file with recommendations service scaled to 3 instances.

To tear down the stack run:

```cmd
docker stack services myshop
```

## View the services running
To get a visual representation of the services and containers running you can use [Docker Swarm Visualizer](https://github.com/ManoMarks/docker-swarm-visualizer).

To install on your swarm run:

```cmd
docker service create --name=viz --publish=8000:8080/tcp --constraint=node.role==manager --mount=type=bind,src=/var/run/docker.sock,dst=/var/run/docker.sock manomarks/visualizer
```

## Credit
This is a fork of [jcorioland/MyShop](https://github.com/jcorioland/MyShop) that has been modified.