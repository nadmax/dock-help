# Bind mounts
Bind mounts create a direct link between a host system path and a container, allowing access to files or directories stored anywhere on the host.
By contrast, they aren't isolated by Docker.  
Which means, if you specified a mount path that doesn't exist on the host, it will produce an error.  
Both non-Docker processes on the host and container processes can modify the mounted files simultaneously.  

Use bind mounts when you need to be able to access files from both the container and the host.
```bash
docker run -d --name <container_name> --mount type=bind,src=<host-path>,dst=<container-path> <image_name> # Start a detached container with a bind mount
docker run -d --name <container_name> --volume <host-path>:<container-path> <image_name> # Shortest way to start a detached container with a bind mount
```