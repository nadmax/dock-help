# Images
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