# Docker

## The storage location of Docker images and containers
```
$ sudo su -
$ cd /var/lib/docker/
```

## Copy files/folders between a container and the local filesystem

_Host -> Container_
```
$ docker cp [HOST_PATH] [CONTAINER_NAME]:[CONTAINER_PATH]
```

_Container -> Host_
```
$ docker cp [CONTAINER_NAME]:[CONTAINER_PATH] [HOST_PATH]
```