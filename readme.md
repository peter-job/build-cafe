# Build Cafe

## Docker Compose

Docker Compose for Cardboard Cafe

### Configurator

**Configurator** is a bash script that will populate a .env file
for Docker Compose.

### Override

Template **docker-compose.yml** is extended by **docker-compose.override.yml**. This override will bind mount the local source directory into the docker container, and run ts-node in watch mode.

To run ***with*** override, use the default command:

```docker-compose up```

To run ***without*** override, use the following command:

```docker-compose -f docker-compose.yml up```

### Push

Docker images can be pushed to Docker Hub with the command

```sh
docker-compose push
```

## Submodules

Build Cafe has two submodules:

- [cardboard-cafe](https://github.com/peter-job/cardboard-cafe)
- [cardboard-ddns](https://github.com/peter-job/cardboard-ddns)

To clone these repos, run the following commands from build-cafe:

```sh
# clone all
git submodule init
git submodule update
# switch all to master
git submodule foreach -q --recursive 'branch="$(git config -f $toplevel/.gitmodules submodule.$name.branch)"; git switch $branch'
```
