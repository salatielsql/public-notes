### Glossary

- Image - Image used to create the container
- Container - instance of a running machine
- Volume - preserves/stores the data from a container. So when a container restarts you can restore the container data from volume

### Volume types

- `bind`: creates a volume taking a existing directory and mounts it on the container
- `volume`: creates a volume that will store data

# The Dockerfile

**Properties**

- `FROM`: Which image the new image will be based on. You are extending from that image.
- `RUN`: What command will be run when the container is building. Each `RUN` will create a layer and only the current layer can write on its own layer meaning the next `RUN` command can’t write the contents of the previous layer since the previous is read-only.
- `ENV`: Set an environment variable to the container
- `LABEL`: Create a label with the syntax: `label_name=”CONTENT”`
- `VOLUME`: Set the path for a volume and creates a volume for the container (type=volume only)
- `EXPOSE`: Exposes a port

# Docker terminal commands

## Container commands

**List running containers.**

Add `-a` to list all containers even the ones that is not running at the moment

```bash
docker container ls (-a)
```

**Running a container**

```bash
docker run container -ti ubuntu
```

`-ti` stands for terminal and interactivity meaning run a container and connect to its terminal so you can access right way.

`-d` run container as daemon meaning in foreground or not as main process

`ctrl + pq` Exit a container without terminating is docker process.

**Accessing a running container**

```bash
docker container attach (CONTAINER_ID|NAME)
```

**Executing a command inside a container**

```bash
docker container exec -ti (CONTAINER_ID|NAME)(command)

// Example:
docker container exec -ti crazy_dewdney bash
```

**Managing a container status**

```bash
docker container start (CONTAINER_ID|NAME)

docker container stop (CONTAINER_ID|NAME)

docker container restart (CONTAINER_ID|NAME)

docker container pause (CONTAINER_ID|NAME)

docker container unpause (CONTAINER_ID|NAME)
```

Removing a container

```bash
docker container rm (-f) (CONTAINER_ID|NAME)
```

`-f` to remove a running container

**Deleting all unused containers**

```bash
docker container prune
```

**Get information about a container**

This command will return information about network, environment variables, IP, mount points, memory e a lot more.

```bash
docker container inspect (CONTAINER_ID|NAME)
```

Show a stats dashboard of a container (CPU, memory, network i/o)

```bash
docker container stats (CONTAINER_ID|NAME)
```

**List a container process**

```bash
docker container top (CONTAINER_ID|NAME)
```

**Getting logs from a container**

```bash
docker container logs -f (CONTAINER_ID|NAME)
```

## Volume commands

**Creating a volume**

```bash
docker volume create VOLUME_NAME
```

**Deleting a volume**

```bash
docker volume rm VOLUME_NAME
```

**Deleting all unused volumes**

```bash
docker volume prune
```

**List volumes**

```bash
docker volume ls
```

**Creating a container with a volume from a existing directory**

```bash
docker container run -ti --mount type=bind,src=DIRECTORY_PATH,dst=/DESTINATION_PATH
```

**Creating a container with a volume**

```bash
docker container run -ti --mount type=volume,src=VOLUME_NAME,dst=/DESTINATION_PATH
```

## Container images commands

**Building a image with a name (`-t` for tag)**

Assuming you have a `Dockerfile` on current directory `.`

```bash
docker build -t my-image .
```
