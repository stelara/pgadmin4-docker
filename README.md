# pgAdmin 4 - docker build

This is a simple Docker image for running pgAdmin 4 in a container. The default
configuration is not intended for production use (it runs in "desktop mode",
so authentication is disabled).

This image uses an unprivileged user, and uses port `5050` instead of `80`.
To access the web-interface on port `80` instead of `5050`, you can map the
port using `-p 80:5050`.

## Upgrades to original repo

- Base image : python:3.8-alpine3.12
- Python 2.7 => 3.8
- Alpine3.8 => 3.12
- PgAdmin version could be specified at build time

## Example build image
```docker build -t image_name --build-arg pgadmin_version=4.24 .```

## Example run container (host machine access)
```docker run -d --net=host  -name pgadmin4 image_name```

## Example run container (when postgres server is docker container)
```docker run -d -p 5050:5050 -name pgadmin4 image_name```

## All available options
https://github.com/thaJeztah/pgadmin4-docker
