# uap-docker

This repo contains the build context used to create a Docker container for the ``uap`` workflow manager.
It is meant to be used as a test environment for users that want to get in touch with the system.

The core files are:
* Makefile
* Dockerfile.uap.0.0.2

## Makefile
The Makefile contains several targets. They are explained below.

### docker-build
Straight-forward **docker build** command. Sets network to host for container and tags it as **kmpf/uap**.

### docker-build-no-cache
Same as **docker-build** target, but with the additionally set **--no-cache** parameter. This is useful if you want to force complete rebuild of container (necessary to get updated content from used git repositories).

### docker-run
Starts the container in interactive mode with an pseudo-TTY.

### docker-push
Pushes the container **kmpf/uap** to [dockerhub](https://hub.docker.com/r/kmpf/uap/).
