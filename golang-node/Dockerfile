ARG NODE_VERSION
ARG GOLANG_VERSION
ARG ALPINE_VERSION

FROM node:$NODE_VERSION-alpine$ALPINE_VERSION AS node
FROM golang:$GOLANG_VERSION-alpine$ALPINE_VERSION

COPY --from=node /usr/lib /usr/lib
COPY --from=node /usr/local/share /usr/local/share
COPY --from=node /usr/local/lib /usr/local/lib
COPY --from=node /usr/local/include /usr/local/include
COPY --from=node /usr/local/bin /usr/local/bin

RUN apt-get update
RUN apt-get upgrade
RUN apt-get install libfftw3-dev libsndfile1-dev