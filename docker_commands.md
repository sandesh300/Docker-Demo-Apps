Here's an updated version of your Docker commands cheat sheet with additional commands for working with files and data management:

# Docker Commands Cheat Sheet

## Basic Container Management
### `docker images`
Lists docker images on the host machine.

### `docker build`
Builds image from Dockerfile.
```bash
docker build -t my-image:tag .  # Build with tag
docker build --no-cache .       # Build without cache
```

### `docker run`
Runs a Docker container with common options:
```bash
docker run -d                  # Run in background (detached)
docker run -p 8080:80          # Port mapping (host:container)
docker run --name my-container # Name the container
docker run -v /host:/container # Volume mounting
docker run -e VAR=value        # Set environment variables
docker run --rm                # Auto-remove when stopped
docker run -it                 # Interactive terminal
```

### `docker ps`
```bash
docker ps        # Lists running containers
docker ps -a     # Lists all containers (including stopped)
docker ps -q     # List only container IDs
```

### `docker stop`
```bash
docker stop container_name  # Stop by name
docker stop container_id    # Stop by ID
```

### `docker start`
```bash
docker start container_name  # Start by name
docker start container_id    # Start by ID
```

## File Operations
### `docker cp`
Copy files between host and container:
```bash
docker cp container_id:/path/to/file /host/path  # Copy from container
docker cp /host/path container_id:/container/path # Copy to container
```

### Volume Management
```bash
docker volume create my-vol    # Create a volume
docker volume ls              # List volumes
docker volume inspect my-vol  # Volume details
```

## Image Management
### `docker rmi`
```bash
docker rmi image_id          # Remove image by ID
docker rmi my-image:tag      # Remove by name:tag
docker image prune           # Remove unused images
```

### `docker pull/push`
```bash
docker pull image:tag        # Download image
docker push myrepo/image:tag # Upload image
```

## Advanced Operations
### `docker exec`
```bash
docker exec -it container_id bash  # Interactive shell
docker exec container_id ls /app   # Run command
```

### `docker logs`
```bash
docker logs container_id      # View logs
docker logs -f container_id   # Follow logs
```

### `docker inspect`
```bash
docker inspect container_id  # Detailed container info
```

### `docker network`
```bash
docker network ls            # List networks
docker network create my-net # Create network
docker network inspect bridge # Network details
```

## Cleanup Commands
```bash
docker system prune          # Remove unused data
docker container prune       # Remove stopped containers
docker image prune -a        # Remove all unused images
```

## Dockerfile Common Instructions
```dockerfile
COPY src dest          # Copy files
ADD src dest           # Copy with extraction
WORKDIR /path          # Set working directory
VOLUME ["/data"]       # Create mount point
EXPOSE 80              # Document port
ENV KEY=value          # Set environment variable
```

Remember you can always use `--help` with any command for more options:
```bash
docker run --help
docker build --help
```
