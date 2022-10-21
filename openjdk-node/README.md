# openjdk-node
based on amazoncorretto's openjdk and node's alpine images. 

## included packages/dependencies
- chromium
- openjdk

## build command
```shell
export OPENJDK_VERSION=11
export NODE_VERSION=17
export ALPINE_VERSION=3.15

docker build . --build-arg OPENJDK_VERSION=$OPENJDK_VERSION --build-arg NODE_VERSION=$NODE_VERSION --build-arg ALPINE_VERSION=$ALPINE_VERSION --tag openjdk-node:openjdk$OPENJDK_VERSION-node$NODE_VERSION-alpine$ALPINE_VERSION
```

## test command
```shell
docker run --rm openjdk-node:openjdk$OPENJDK_VERSION-node$NODE_VERSION-alpine$ALPINE_VERSION /bin/sh -c "java --version && node --version"
```

## credits
- build idea based on  [Csaba Apagyi](https://github.com/thisismydesign/ruby-node-alpine)
- [amazoncorretto openjdk image](https://hub.docker.com/_/amazoncorretto)
- [node image](https://hub.docker.com/_/node)