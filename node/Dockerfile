ARG NODE_VERSION
ARG ALPINE_VERSION

FROM node:$NODE_VERSION-alpine$ALPINE_VERSION AS node

RUN apk add chromium

ENV CHROME_BIN=/usr/bin/chromium-browser