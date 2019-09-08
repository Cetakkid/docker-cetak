# Dockerizing Cetak

## Overview

django and vuejs configurations for the Cetak system using docker. Nginx will serve to collect static like staticfile for Django.
this project is still under development and only work if using django server. all contributions is very helpful and welcome.


## Requirements

- Docker
- Python (latest version)
- Django (latest version)
- Nodejs
- Vuejs
- Gunicorn

## Project structure

| workdir | function |
|--------|----------|
| `backend` | Where all Django environment stored there |
| `frontend` | Where all Vuejs environment stored there |
| `nginx` | Create reverse proxy to handling user request |

## To use Django project

Use the default Django development server.

- Update the environment variables in the *docker-compose.yml* file.
- Build the images and run the containers:

    ```sh
    $ docker-compose up -d --build
    ```

    Test it out at [http://localhost:8000](http://localhost:8000). The "backend" directory is mounted into the container and your code changes apply automatically.

## Note

if you have facing experience problems or even get an error like the unsupported docker compose, you can change the variable version to version 3 or you can update the latest version of the docker