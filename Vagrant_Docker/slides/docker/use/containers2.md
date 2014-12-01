## Containers

#### Expose ports

```bash
$ docker run -d mysql /usr/sbin/mysqld
$ docker run -d -p 13306:3306 mysql /usr/sbin/mysqld
$ docker run -d -P mysql /usr/sbin/mysqld
```

#### Volumes

```bash
$ docker run -it -v /host/folder:/container/folder mysqld
```

#### Limit memory

```bash
$ docker run -d -P -m 1g mysql /usr/sbin/mysqld # Available units: b, k, m, g.
$ docker run -d -P --memory="1000m" mysql /usr/sbin/mysqld
```

#### Limit CPU

```bash
$ docker run -d -P -c 10 mysql /usr/sbin/mysqld # Relative weight
$ docker run -d -P --cpu-shares=10 mysql /usr/sbin/mysqld # Relative weight
$ docker run -d -P --cpuset="0,1" mysql /usr/sbin/mysqld # CPUs in which to allow execution (0-3, 0,1)
```
