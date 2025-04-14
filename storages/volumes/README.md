# Volumes
Volumes are persistent data stores for containers.  
When you create a volume (see examples below), it's stored within a directory on the Docker host.  
When you mount the volume into a container (see examples below), this directory is what's mounted into the container.  
By default, mounted volumes are read-write volumes but you can mount a volume as read-only.

Volumes are managed by Docker and are isolated from the core functionality of the host machine.
If you need to access files or directories from both containers and the host, use bind mounts. 

Here are some examples of Docker commands related to volumes:
```bash
docker volume create <volume_name> # Create a new volume
docker volume ls # List volumes
docker volume inspect <volume_name> # Show low-level volume info (in JSON format)
docker volume rm <volume_name> # Delete a volume
docker run -d --name <container_name> --mount source=<volume_name>,target=<directory> <image_name> # Start a detached container with a volume
docker run -d --name <container_name> -v <source_volume>:<target_directory> <image_name> # Shortest way to start a detached container with a volume
docker run -d --name <container_name> --mount source=<volume_name>,target=<directory>, readonly <image_name> # Start a detached detached container with a read-only volume
docker run -d --name <container_name> -v <source_volume>:<target_directory>:ro <image_name> # Shortest way to start a detached container with a read-only volume
```