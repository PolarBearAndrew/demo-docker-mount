# demo-docker-mount

demo docker mount local file

## Build

build a node.js server, you can use any server you like.

```
$ docker build .
```

## Run

Run with port 3000 and mount folder.

```
$ docker run -it -p 3000:3000 -v <folder-you-want-mount>:/src/localFolder <your-image-id>
```

If successfully, you'll get image id.

```
ending build context to Docker daemon  56.83kB
Step 1/1 : FROM node:8-alpine
 ---> 9391a12dde70
Successfully built 9391a12dde70
```

## Get container ID

```
# docker ps
```

You will get something like this.

```
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS                    NAMES
c28bc8aa6027        9391a12dde70        "node"              10 seconds ago      Up 10 seconds       0.0.0.0:3000->3000/tcp   unruffled_swanson
```

What we need is container id: `c28bc8aa6027`, you will get your own id.

## Get into the docker

```
$ docker exec -it <your-container-id>
```

here you can get everything you mounted.

```
cd src/localFolder
```