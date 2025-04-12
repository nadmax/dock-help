# dock-help

## What is Docker?

Docker is an open-source platform which provides the ability to package and run an application in an isolated environment called container.   
Thanks to the isolation, it allows you to run many containers simultaneously on a given host.  

You can share containers while you work, it ensures that everyone gets the same container that works in the same way.

## Installation
They are two ways to install Docker:  
- [Docker Desktop](https://www.docker.com/products/docker-desktop/): A user-friendly, all-in-one application for container management.
- [Docker Engine](https://docs.docker.com/engine/install/): The containerization technology for building and containerizing your applications.

## General commands
```bash
docker -d # Start the docker daemon
docker <optional_subcommand> --help # Get help with Docker. Works with subcommand like build, images etc...
docker info # Display system-wide information
```

## Images
Before running a container, you need an image of your application.  
A Docker image is a lightweight, standalone, executable package of software that includes everything needed to run an application (code, runtime, system tools, system libraries and settings).
```bash
docker build -t <image_name> . # Build an image from a Dockerfile
docker build -t <image_name> . --no-cache # Build an image from a Dockerfile without the cache
docker images # List local images
docker rmi <image_name> # Delete an image
docker image prune # Remove all unused images
docker rmi -f $(docker images -aq) # Delete all images
docker inspect <image_name> # Show low-level image info (in JSON format)
docker history <image_name> # Show the image history by listing its ancestors
docker tag <repo_name>/<image_name>|<image_name>:<tag_name> # Tag an image
docker push <repo_name>/<image_name>|<image_name>:<tag_name> # Push an image/repo to a registry
docker pull <repo_name>/<image_name>|<image_name>:<tag_name> # Pull an image/repo from a registry
docker search <text> # Search an image on the official registry
```

## Containers
A container is a runtime instance of a Docker image.  
A container will always run the same, regardless of the infrastructure.  

They isolate software from its environment and ensure that it works uniformly despite differences for instance between development and staging.
```bash
docker run --name <container_name> <image_name> # Create and run a container from an image, with a custom name
docker run -p <host_port>:<container_port> --name <container_name> <image_name> # Create and run a container with a custom name and publish a container's port to the host.
docker run -d --name <container_name> <image_name> # Create and run a container with a custom name, in the background
docker start|stop <container_name>|<container_id> # Start or stop an existing container by specifying its name or its ID
docker rm <container_name> # Remove a stopped container
docker exec -it <container_name> # Open a shell inside a running container
docker logs -f <container_name> # Fetch and follow container logs
docker container ls # List containers
docker container inspect <container_name>|<container_id> # Inspect a running container (in JSON format)
docker ps # List currently running containers
docker ps -a|--all # List running and stopped containers
docker ps -q # Only list container IDs
docker container stats # View resource usage stats
docker commit <container_name> <image_name> # Commit a snapshot of the container
```

## Volumes
Volumes are persistent data stores for containers.  
When you create a volume (see examples below), it's stored within a directory on the Docker host.  
When you mount the volume into a container (see examples below), this directory is what's mounted into the container.  
By default, mounted volumes are read-write volumes but you can mount a volume as read-only.

Volumes are managed by Docker and are isolated from the core functionality of the host machine.
If you need to access files or directories from both containers and the host, use bind mounts.  
```bash
docker volume create <volume_name> # Create a new volume
docker volume ls # List volumes
docker volume inspect <volume_name> # Show low-level volume info (in JSON format)
docker volume rm <volume_name> # Delete a volume
docker run -d --name <container_name> --mount source=<volume_name>,target=<directory> <image_name> # Start a container with a volume
docker run -d --name <container_name> -v <source_volume>:<target_directory> <image_name> # Shortest way to start a container with a volume
docker run -d --name <container_name> --mount source=<volume_name>,target=<directory>, readonly <image_name> # Start a container with a read-only volume
docker run -d --name <container_name> -v <source_volume>:<target_directory>:ro <image_name> # Shortest way to start a container with a read-only volume
```