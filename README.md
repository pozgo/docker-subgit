### SubGit in a docker.

[![CircleCI Build Status](https://img.shields.io/circleci/project/pozgo/docker-subgit/master.svg)](https://circleci.com/gh/pozgo/docker-subgit)
[![GitHub Open Issues](https://img.shields.io/github/issues/pozgo/docker-subgit.svg)](https://github.com/pozgo/docker-subgit/issues)
[![GitHub Stars](https://img.shields.io/github/stars/pozgo/docker-subgit.svg)](https://github.com/pozgo/docker-subgit)
[![GitHub Forks](https://img.shields.io/github/forks/pozgo/docker-subgit.svg)](https://github.com/pozgo/docker-subgit)  
[![Stars on Docker Hub](https://img.shields.io/docker/stars/polinux/subgit.svg)](https://hub.docker.com/r/polinux/subgit)
[![Pulls on Docker Hub](https://img.shields.io/docker/pulls/polinux/subgit.svg)](https://hub.docker.com/r/polinux/subgit)  
[![](https://images.microbadger.com/badges/version/polinux/subgit.svg)](http://microbadger.com/images/polinux/subgit)
[![](https://images.microbadger.com/badges/license/polinux/subgit.svg)](http://microbadger.com/images/polinux/subgit)
[![](https://images.microbadger.com/badges/image/polinux/subgit.svg)](http://microbadger.com/images/polinux/subgit)

[Docker Image](https://registry.hub.docker.com/u/polinux/subgit/) with SubGit. It's using tiny image provided by Alpine.  

[SubGit Website](https://subgit.com/)  

Purpose of this image was to simplify the process of using SubGit.

Workdir is set to `/subgit`

### Usage

    docker run \
      -ti \
      --name subgit \
      polinux/subgit

Mount Volume into working directory

    docker run \
      -ti \
      --name subgit \
      -v ${PWD}/workdir:/subgit \
      polinux/subgit

### Build

    docker build -t polinux/subgit .

Docker troubleshooting
======================

Use docker command to see if all required containers are up and running:
```
$ docker ps
```

Check logs of subgit server container:
```
$ docker logs subgit
```

Sometimes you might just want to review how things are deployed inside a running
 container, you can do this by executing a _bash shell_ through _docker's
 exec_ command:
```
docker exec -ti subgit /bin/bash
```

History of an image and size of layers:
```
docker history --no-trunc=true polinux/subgit | tr -s ' ' | tail -n+2 | awk -F " ago " '{print $2}'
```

## Author

Przemyslaw Ozgo (<linux@ozgo.info>)
