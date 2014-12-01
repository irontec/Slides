## Containers

#### List containers

```bash
$ docker ps
$ docker ps -a
$ docker ps --all
```

#### Create a container

```bash
$ docker run debian:wheezy /bin/echo "Hello world"
$ docker run debian:wheezy /bin/sh -c "while true; do echo 'Hello world'; sleep 1; done"
```
#### Interactive shell in container

```bash
$ docker run -i -t debian:wheezy /bin/bash
```

#### Run container as daemon

```bash
$ docker run -d --name="debian container" debian:wheezy /bin/sh -c "while true; do echo 'Hello world'; sleep 1; done"
```
