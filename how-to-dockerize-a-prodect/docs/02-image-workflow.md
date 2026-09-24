# Build, Publish, and Pull the Image

This workflow builds the production image defined by the final stage in the
Dockerfile and publishes it to Docker Hub.

## 1. Build the image

From the `getting-started-todo-app` directory, run:

```bash
docker build --tag jaykishorc/getting-started-todo-app:latest .
```

The tag identifies the Docker Hub account, repository, and image version. The
`:latest` tag is explicit here so the same image reference can be used for the
push, pull, and run commands.

## 2. Sign in to Docker Hub

```bash
docker login
```

Follow the prompts to authenticate. Do not place your password or access token
in a command that may be saved in shell history.

## 3. Push the image

```bash
docker push jaykishorc/getting-started-todo-app:latest
```

The repository must exist under the `jaykishorc` Docker Hub account, or Docker
Hub must be configured to create it for your account.

## 4. Pull the image on another machine

After signing in on the target machine, download the image:

```bash
docker pull jaykishorc/getting-started-todo-app:latest
```

## 5. Run the published image

```bash
docker run --detach \
  --name todo-app \
  --publish 8080:3000 \
  jaykishorc/getting-started-todo-app:latest
```

The `--publish 8080:3000` option maps host port 8080 to the container's port
3000. Open [http://localhost:8080](http://localhost:8080) to use the app.

> PowerShell also accepts the command as one line. If you split it across
> lines, use the PowerShell backtick instead of the Bash backslash.