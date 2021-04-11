---
title: "Docker"
layout: default
link: "landing"
parent: Docker
parent_path: /docker/
---
Docker generates an image of our app, making it easier to deploy.

## Commands
Run hello world app
```bash
docker run hello-world
```

See all containers currently running
```bash
docker ps
```

Remove all inactive containers
```bash
docker container prune
```

Inspect a container
```bash
docker inspect CONTAINERID
```

Execute a command in a container
```bash
docker exec CONTAINERID cat /etc/hosts
```

## Resources
* [Docker connection refused](https://pythonspeed.com/articles/docker-connection-refused/)