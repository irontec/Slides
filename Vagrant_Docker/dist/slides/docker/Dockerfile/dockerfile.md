## Dockerfile

Structure

```CoffeeScript
FROM debian:wheezy
MANTAINER Luis García <lfgarcia@irontec.com>

# ENV variables
ENV key value

# update repos
RUN apt-get update

# Install mysql
RUN apt-get install -y mysql-server

# Expose mysql port 3306 (for intercontainer links)
EXPOSE 3306

# Volumes
VOLUME /host/folder:/container/folder

# Copy files
ADD ./file_relative_to_dockerfile_in_host /container/file
ADD ./file_relative_to_dockerfile_in_host.tar.gz /container/folder

COPY ./file_relative_to_dockerfile_in_host.tar.gz /container/folder
COPY ./file_relative_to_dockerfile_in_host.tar.gz /container/file.tar.gz

# User 
USER vagrant

# Workdir
WORKDIR /opt
WORKDIR klear-development

# Entry Point (only one per dockerfile) (can't be overwritten)
ENTRYPOINT ["/user/bin/influxdb", "-config=/opt/influxdbconfig.toml"]
ENTRYPOINT supervisor

# command (only one per dockerfile) (can be overwritten) (Can use as param of ENTRYPOINT)

CMD ["/usr/local/bin/diamond", "-f"]
CMD echo "This is a test. " | wc -
CMD ["--help"]

# On build
ONBUILD [instruction]

```

