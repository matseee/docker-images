# android
based on golang's and node's alpine images. 

## included packages/dependencies
- chromium
- build-base
- fftw-dev 
- libayatana-appindicator-dev 
- gtk+3.0-dev 

## build command
```shell
export GOLANG_VERSION=1.17.6
export NODE_VERSION=17
export ALPINE_VERSION=3.15

docker build . --build-arg GOLANG_VERSION=$GOLANG_VERSION --build-arg NODE_VERSION=$NODE_VERSION --build-arg ALPINE_VERSION=$ALPINE_VERSION --tag golang-node:go$GOLANG_VERSION-node$NODE_VERSION-alpine$ALPINE_VERSION
```

## test command
```shell
docker run --rm golang-node:go$GOLANG_VERSION-node$NODE_VERSION-alpine$ALPINE_VERSION /bin/sh -c "go version && node --version"
```

## credits
- build idea based on  [Csaba Apagyi](https://github.com/thisismydesign/ruby-node-alpine)
- [node image](https://hub.docker.com/_/node)
- [golang image](https://hub.docker.com/_/golang)