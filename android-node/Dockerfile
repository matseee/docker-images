ARG ALPINE_VERSION
ARG ANDROID_VERSION
ARG NODE_VERSION

FROM node:$NODE_VERSION-alpine$ALPINE_VERSION AS node
FROM alpine:$ALPINE_VERSION

# prepare nodejs
COPY --from=node /usr/lib /usr/lib
COPY --from=node /usr/local/share /usr/local/share
COPY --from=node /usr/local/lib /usr/local/lib
COPY --from=node /usr/local/include /usr/local/include
COPY --from=node /usr/local/bin /usr/local/bin

# install java openjdk
RUN apk add openjdk11

# prepare android cmdline tools
RUN cd /opt && \
    mkdir android-sdk && cd android-sdk && \
    wget https://dl.google.com/android/repository/commandlinetools-linux-8512546_latest.zip && \
    mv commandlinetools-linux-8512546_latest.zip android.zip && unzip android.zip && \
    cd ./cmdline-tools/ && mkdir latest && \
    mv ./NOTICE.txt ./latest/. && mv ./lib ./latest/. && \
    mv ./source.properties ./latest/. && mv ./bin ./latest/. && \
    cd .. && rm android.zip

ENV ANDROID_VERSION $ANDROID_VERSION

# install sdk
RUN yes | /opt/android-sdk/cmdline-tools/latest/bin/sdkmanager --licenses
RUN /opt/android-sdk/cmdline-tools/latest/bin/sdkmanager "platform-tools" "platforms;android-33"
