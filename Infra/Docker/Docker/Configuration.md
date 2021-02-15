# Docker

## Uninstall old versions
_Older versions of Docker were called docker, docker.io, or docker-engine. If these are installed, uninstall them:_
```
$ sudo apt-get remove docker docker-engine docker.io
```

## Installing Docker on Ubuntu
```
$ sudo apt install docker.io
```

_Now that Docker has successfully been installed, we can start and enable it by entering the two following commands in the command line:_
```
$ sudo systemctl start docker
$ sudo systemctl enable docker
```

_Verify that Docker is successfully installed:_
```
$ docker --version
```

## Managing Docker as a non-root user
_The Docker daemon binds to a Unix socket instead of a TCP port. By default that Unix socket is owned by the user root and other users can only access it using sudo. The Docker daemon always runs as the root user._

_If you don’t want to preface the docker command with sudo, create a Unix group called docker and add users to it. When the Docker daemon starts, it creates a Unix socket accessible by members of the docker group._
```
$ sudo usermod -aG docker $USER
$ newgrp docker
```

# Reference

- [Docker Documentation](https://docs.docker.com/)
