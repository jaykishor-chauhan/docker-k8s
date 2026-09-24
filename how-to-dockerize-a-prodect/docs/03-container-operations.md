# Inspect and Manage Containers

These commands are useful after starting the app with `docker run` or Docker
Compose.

## List containers

Show running containers:

```bash
docker ps
```

Show running and stopped containers:

```bash
docker ps --all
```

Use the `NAMES` or `CONTAINER ID` column as the value for commands that follow.

## Open a shell in a container

For the standalone container created in the image workflow:

```bash
docker exec --interactive --tty todo-app sh
```

You can also use its ID:

```bash
docker exec --interactive --tty <container-id> sh
```

For a Compose service, prefer the service name from the project directory:

```bash
docker compose exec backend sh
```

## View logs

View logs by container name:

```bash
docker logs todo-app
```

Or use the container ID:

```bash
docker logs <container-id>
```

Follow new log output as it arrives:

```bash
docker logs --follow todo-app
```

For Compose services:

```bash
docker compose logs --follow backend
```

## Stop, start, and remove a container

```bash
docker stop todo-app
docker start todo-app
docker rm todo-app
```

The container must be stopped before it can be removed. To stop and remove it
in one command, use:

```bash
docker rm --force todo-app
```

Removing a container does not remove the image used to create it.