# Docker Compose
Docker Compose is a tool for defining and running multi-container applications.  
Compose simplifies the control of your entire application stack, making it easy to manage services, networks, and volumes in a single YAML configuration file.  
With a single command, you can create and start all the services from your configuration file. (see commands examples below)

```bash
docker compose up -d # Start all detached services defined in compose.yaml file
docker compose down # Stop and remove running services, networks
docker compose logs # Monitor running containers output
docker compose ps # List all the services with their current status
```

[View the compose file example here](https://github.com/nadmax/dock-help/blob/master/compose/compose.example.yaml)