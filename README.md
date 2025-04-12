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
docker inspect <container_name>|<container_id> # Inspect a running container
docker ps # List currently running containers
docker ps -a|--all # List running and stopped containers
docker ps -q # Only list container IDs
docker container stats # View resource usage stats
```