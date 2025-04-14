# Containers
A container is a runtime instance of a Docker image.  
A container will always run the same, regardless of the infrastructure.  

They isolate software from its environment and ensure that it works uniformly despite differences for instance between development and staging.

Here are some examples of Docker commands related to containers:
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