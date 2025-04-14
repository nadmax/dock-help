# Networks
Networking for containers refers to the ability to connect and communicate with each other, or to non-Docker workloads.  
Networking is enabled by default, which means they can make outgoing connections.  
A container only sees a network interface with an IP address, a gateway, a routing table, DNS services, etc...  

You can create custom networks, and connect multiple containers to the same network.  
Once connected to a custom network, containers can communicate with each other using container IP addresses or container names.
```bash
docker network create -d <driver_type> <network_name> # Create a custom network by specifying driver
docker network ls # List networks
docker network inspect <network_name> # Show low-level network info (in JSON format)
docker network connect <network_name> <container_name> # Connect a container to a network
docker network disconnect <network_name> <container_name> # Disconnect a container from a network
docker network rm <network_name> # Delete network
docker network prune # Delete unused networks
docker run -d -v <source_volume>:<target_directory> <image_name>  --name <container_name> --network <driver_type> <image_name> # Start a container with a volume mount from a network driver
```
## Drivers
Drivers are pluggable interfaces implementing networking functionality for containers.  
Docker provides built-in network drivers for common use cases, including multi-host networking and encryption.  

Here are a list of some drivers:
| Driver | Description |
|----------------|-------------|
| **Bridge**     | A software device which lets containers connected to the same network, while providing isolation from containers that aren't connected to that network. It is the default network driver if you don't specify one. |
| **Host**       | Remove network isolation between the container and the Docker host, and use the host's networking directly. 
| **overlay** | Connect multiple Docker daemons together and enable Swarm services and containers to communicate across nodes.
| **none** | Completely isolate a container from the host and other containers. Not available for Swarm services.