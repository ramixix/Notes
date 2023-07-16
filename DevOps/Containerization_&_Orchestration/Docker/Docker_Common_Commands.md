# Commonly used Docker commands along with a brief explanation and examples:
```sh
    docker run: Run a container based on an image.
    # Example:
    > docker run -it ubuntu

    docker build: Build a Docker image from a Dockerfile.
    # Example:
    > docker build -t myimage .

    docker pull: Pull an image from a registry.
    # Example:
    > docker pull nginx

    docker push: Push an image to a registry.
    # Example:
    > docker push myusername/myimage

    docker images: List available Docker images.
    # Example:
    > docker images

    docker ps: List running containers.
    # Example:
    > docker ps

    docker stop: Stop a running container.
    # Example:
    > docker stop container_id

    docker start: Start a stopped container.
    # Example:
    > docker start container_id

    docker restart: Restart a running container.
    # Example:
    > docker restart container_id

    docker rm: Remove a stopped container.
    # Example:
    > docker rm container_id

    docker rmi: Remove an image.
    # Example:
    > docker rmi image_id

    docker exec: Execute a command in a running container.
    # Example:
    > docker exec -it container_id command

    docker logs: View logs from a container.
    # Example:
    > docker logs container_id

    docker cp: Copy files between a container and the host.
    # Example:
    > docker cp container_id:/path/file.txt /host/path

    docker network ls: List Docker networks.docker
    # Example:
    > docker network ls

    docker network create: Create a Docker network.
    # Example:
    > docker network create mynetwork

    docker network connect: Connect a container to a network.
    # Example:
    > docker network connect mynetwork container_id

    docker network disconnect: Disconnect a container from a network.
    # Example:
    > docker network disconnect mynetwork container_id

    docker volume ls: List Docker volumes.
    # Example:
    > docker volume ls

    docker volume create: Create a Docker volume.
    # Example:
    > docker volume create myvolume

    docker volume rm: Remove a Docker volume.
    # Example:
    > docker volume rm myvolume

    docker-compose up: Start containers defined in a Docker Compose file.
    # Example:
    > docker-compose up -d

    docker-compose down: Stop and remove containers defined in a Docker Compose file.
    # Example:
    > docker-compose down

    docker inspect: Display detailed information about a container or image.
    # Example:
    > docker inspect container_id

    docker stats: Display resource usage of running containers.
    # Example:
    > docker stats

    docker attach: Attach to a running container.
    # Example:
    > docker attach container_id

    docker export: Export a container filesystem as a tar archive.
    # Example:
    > docker export container_id > container.tar

    docker import: Import a tar archive to create a filesystem image.
    # Example:
    > docker import container.tar myimage

    docker login: Log in to a Docker registry.
    # Example:
    > docker login

    docker logout: Log out from a Docker registry.
    # Example:
    > docker logout

    docker pause: Pause processes in a running container.
    # Example: 
    > docker pause container_id

    docker unpause: Unpause processes in a paused container.
    # Example: 
    > docker unpause container_id

    docker kill: Kill a running container.
    # Example: 
    > docker kill container_id

    docker restart: Restart a container.
    # Example: 
    > docker restart container_id

    docker top: Display the running processes in a container.
    # Example: 
    > docker top container_id

    docker diff: Show changes made to a containers filesystem.
    # Example: 
    > docker diff container_id

    docker commit: Create a new image from a containers changes.
    # Example: 
    > docker commit container_id myimage

    docker save: Save an image to a tar archive.
    # Example: 
    > docker save -o image.tar myimage

    docker load: Load an image from a tar archive.
    # Example: 
    > docker load -i image.tar

    docker history: Display the history of an image.
    # Example: 
    > docker history image_id

    docker tag: Tag an image with a name.
    # Example: 
    > docker tag image_id myusername/myimage:tag

    docker events: Get real-time events from the server.
    # Example: 
    > docker events

    docker system df: Show Docker disk usage.
    # Example: 
    > docker system df

    docker system prune: Remove unused Docker data (containers, networks, volumes, images).
    # Example: 
    > docker system prune

    docker version: Show Docker version information.
    # Example: 
    > docker version

    docker info: Display system-wide Docker information.
    # Example: 
    > docker info

    docker plugin ls: List Docker plugins.
    # Example: 
    > docker plugin ls

    docker plugin install: Install a Docker plugin.
    # Example: 
    > docker plugin install plugin_name

    docker plugin uninstall: Uninstall a Docker plugin.
    # Example: 
    > docker plugin uninstall plugin_name

    docker swarm init: Initialize a swarm.
    # Example: 
    > docker swarm init

    docker swarm join: Join a swarm as a worker or manager.
    # Example: 
    > docker swarm join --token SWMTKN-1-abc123def456...

    docker stack deploy: Deploy a stack defined in a Compose file to the swarm.
    # Example: 
    > docker stack deploy -c docker-compose.yml myapp

    docker service ls: List services in a swarm.
    # Example: 
    > docker service ls

    docker service create: Create a new service.
    # Example: 
    > docker service create --replicas 3 myimage

    docker service scale: Scale a service to a specific number of replicas.
    # Example: 
    > docker service scale myservice=5

    docker service update: Update a service with new configuration.
    # Example: 
    > docker service update --image myimage:latest myservice

    docker node ls: List nodes in the swarm.
    # Example: 
    > docker node ls

```