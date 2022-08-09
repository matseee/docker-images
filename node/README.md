# node
based on node's alpine image.

## included packages/dependencies
- chromium

## build command
```shell
export NODE_VERSION=17
export ALPINE_VERSION=3.15

docker build . --build-arg NODE_VERSION=$NODE_VERSION --build-arg ALPINE_VERSION=$ALPINE_VERSION --tag node:node$NODE_VERSION-alpine$ALPINE_VERSION
```

## test command
```shell
docker run --rm node:node$NODE_VERSION-alpine$ALPINE_VERSION /bin/sh -c "node --version"
```

## credits
- [node image](https://hub.docker.com/_/node)