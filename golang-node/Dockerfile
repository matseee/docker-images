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

RUN apk update
RUN apk upgrade
RUN apk add fftw-dev g++ make # libsndfile1-dev