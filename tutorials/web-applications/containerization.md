---
title: "Containerization of Flask apps"
layout: default
parent: Web Applications
parent_path: /tutorials/web-applications/
---
We will use buildpacks to generate a Docker image of our source code. Make sure that Docker is installed and [configured for WSL2](wsl.md).

## Setup
Install buildpacks.
```bash
curl -sSL "https://github.com/buildpacks/pack/releases/download/v0.15.0/pack-v0.15.0-linux.tgz" | sudo tar -C /usr/local/bin/ --no-same-owner -xzv pack
```

Build the Python app image. After the following command completes, you should be able to view the app image in the Docker GUI.
```bash
pack build testrepo/testcontainer:1.0.0.0 --builder heroku/buildpacks:18
```

Run the app image, using Docker.
```bash
docker run --rm -p 8080:8080 testrepo/testcontainer:1.0.0.0
```

# Further reading
* [Python like a pro - build Docker containers](https://tanzu.vmware.com/developer/guides/python/cnb-gs-python/)
* [How to remove docker images containers and volumes](https://www.digitalocean.com/community/tutorials/how-to-remove-docker-images-containers-and-volumes)