# NODEJS
NodeJs Dockerfiles with additional libraries (mainly for our needs)

## Example of Usage

Move to the folder containing the desired Dockerfile.

Build the image
```
docker build -t <dockertag> .
```

Create a shell script called `<command><version>.sh` with this content :
```
#!/bin/bash
docker run --rm --interactive --tty \
  --workdir /usr/src/app \
  --volume $PWD:/usr/src/app \
  --user $(id -u):$(id -g) \
  <dockertag> <command> "$@"
```

## Dockerhub
All images are available at : https://hub.docker.com/r/ihneo/node

You can pull all images with the command :
```
docker pull ihneo/node:<dockertag>
```

## Supported tags and respective `Dockerfile` links

-	[`13-alpine`](https://github.com/ihneo/node/blob/master/13/alpine/Dockerfile)
-	[`14-alpine`](https://github.com/ihneo/node/blob/master/14/alpine/Dockerfile)
-	[`15-alpine`](https://github.com/ihneo/node/blob/master/15/alpine/Dockerfile)
-	[`16-alpine`](https://github.com/ihneo/node/blob/master/16/alpine/Dockerfile)
-	[`17-alpine`, `latest`](https://github.com/ihneo/node/blob/master/17/alpine/Dockerfile)

## Example of usage with the images available at Dockerhub
```
#!/bin/bash
docker run --rm --interactive --tty \
  --workdir /usr/src/myapp \
  --volume $PWD:/usr/src/myapp \
  --user $(id -u):$(id -g) \
  ihneo/node:<dockertag> <command> "$@"
```