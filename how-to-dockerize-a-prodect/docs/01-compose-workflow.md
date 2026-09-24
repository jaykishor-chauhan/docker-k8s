# Run the App with Docker Compose

Docker Compose starts the complete development stack: the frontend, backend,
MySQL database, reverse proxy, and phpMyAdmin.

## 1. Clone the project

Run these commands from the directory where you keep your projects:

```bash
git clone https://github.com/docker/getting-started-todo-app
cd getting-started-todo-app
```

## 2. Build and start the stack

Build the application images and start all services in the background:

```bash
docker compose up --build --detach
```

The `--build` option rebuilds images when the Dockerfile or application files
change. The `--detach` option leaves the services running in the background.

## 3. Check service status

```bash
docker compose ps
```

Wait until the database health check passes and the application services are
running. The Compose file exposes the reverse proxy on host port 80.

## 4. Open the application

Open [http://localhost](http://localhost) in a browser.

The development stack also provides phpMyAdmin at
[http://db.localhost](http://db.localhost).

## 5. Stop the stack

Stop and remove the containers while keeping the named database volume:

```bash
docker compose down
```

To remove the database volume as well, use this only when you no longer need
the stored Todo data:

```bash
docker compose down --volumes
```