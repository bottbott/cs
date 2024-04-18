---
lang: en
title: Docker
viewport: width=device-width, initial-scale=1.0
---
## Useful commands

- `docker compose build`
    - **Description**: Builds or rebuilds services defined in a `docker-compose.yml` file. It does not start the containers after building them.

- `docker compose up -d`
    - **Description**: Starts the containers in detached mode, allowing you to continue using the terminal.
    - **Flags**:
    - `-d`: Detached mode.

- `docker compose -f docker-compose.dev.yml up --build -d`
    - **Description**: Uses a custom Docker compose file to start the containers, forcing a build of the images before starting, in detached mode.
    - **Flags**:
    - `-f`: Specifies a custom file (in this case, `docker-compose.dev.yml`).
    - `--build`: Forces a build of the images.
    - `-d`: Detached mode.

- `docker compose down -v`
    - **Description**: Stops and removes containers, networks, and the default network associated with the composition. Additionally, removes the volumes.
    - **Flags**:
        - `-v`: Removes the volumes.

- `docker compose -f docker-compose.dev.yml down -v`
    - **Description**: Stops and removes containers, networks, and volumes specified in a custom Docker compose file.
    - **Flags**:
      - `-f`: Specifies a custom file (`docker-compose.dev.yml`).
      - `-v`: Removes the volumes.

- `docker exec -it django-dev bash`
    - **Description**: Executes an interactive bash shell inside the running container named `django-dev`.
    - **Flags**:
        - `-it`: Interactive terminal.

- `docker build . -t api`
    - **Description**: Builds a Docker image from the Dockerfile in the current directory, tagging it as `api`.
    - **Flags**:
        - `-t`: Tag the image.

- `docker run -p 8000:8000 -e DJANGO_SECRET_KEY=$DJANGO_SECRET_KEY api`
    - **Description**: Runs a container from the `api` image, exposing port 8000 and setting the `DJANGO_SECRET_KEY` environment variable.
    - **Flags**:
        - `-p 8000:8000`: Maps port 8000 of the container to port 8000 on the host.
        - `-e DJANGO_SECRET_KEY=$DJANGO_SECRET_KEY`: Sets an environment variable inside the container.

- `docker image prune`
    - **Description** Removes dangling images. 