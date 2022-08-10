ARG ALPINE_VERSION
ARG NODE_VERSION

FROM node:$NODE_VERSION-alpine$ALPINE_VERSION AS node

RUN apk add chromium

ENV CHROME_BIN=/usr/bin/chromium-browser