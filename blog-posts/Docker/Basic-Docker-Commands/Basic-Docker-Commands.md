---
title: Basic Docker Commands 
published: true
description: description
tags: Docker
---
Docker is a powerful tool for creating, deploying, and running applications using containerization. Here are some basic Docker commands you might find useful:

## Pull an Image

To download an image from Docker Hub or another Docker registry:
```bash
docker pull [OPTIONS] NAME[:TAG|@DIGEST]
```
## List Images

To list all available Docker images:
```bash
docker images [OPTIONS] [REPOSITORY[:TAG]]
```
## Run a Container

To create a new container and start it:
```bash
docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
```
For example, to run a bash shell with Ubuntu:
```bash
docker run -it ubuntu bash
```
## List Running Containers

To list all currently running containers:
```bash
docker ps [OPTIONS]
```
## Start a Container

To start a previously created or stopped container:
```bash
docker start [OPTIONS] CONTAINER [CONTAINER...]
```
## Stop a Container

To stop a running container:
```bash
docker stop [OPTIONS] CONTAINER [CONTAINER...]
```
## Remove a Container

To remove a container:
```bash
docker rm [OPTIONS] CONTAINER [CONTAINER...]
```
## Remove an Image

To remove an image:
```bash
docker rmi [OPTIONS] IMAGE [IMAGE...]
```
For more information about these commands and their options, please refer to the official Docker documentation.
