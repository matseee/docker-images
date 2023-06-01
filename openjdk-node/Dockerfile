ARG ALPINE_VERSION
ARG OPENJDK_VERSION
ARG NODE_VERSION

FROM node:$NODE_VERSION-alpine$ALPINE_VERSION AS node
FROM amazoncorretto:$OPENJDK_VERSION-alpine$ALPINE_VERSION

COPY --from=node /usr/lib /usr/lib
COPY --from=node /usr/local/share /usr/local/share
COPY --from=node /usr/local/lib /usr/local/lib
COPY --from=node /usr/local/include /usr/local/include
COPY --from=node /usr/local/bin /usr/local/bin

RUN apk add fftw-dev libayatana-appindicator-dev gtk+3.0-dev build-base
RUN apk add git
RUN apk add chromium

ENV CHROME_BIN=/usr/bin/chromium-browser