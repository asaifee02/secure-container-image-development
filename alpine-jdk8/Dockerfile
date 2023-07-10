FROM  azul/zulu-openjdk-alpine:11-jre-headless
# Create app user
RUN apk update && apk add ca-certificates && rm -rf /var/cache/apk/*
RUN update-ca-certificates
RUN mkdir -p /usr/src/app \
    && addgroup app \
    && adduser -h /usr/src/app -G app -D app \
    && apk add --no-cache wget \
    && apk add --update -u openssl \
    && rm -rf /var/cache/apk/* \
    && apk add --update -u apk-tools \
    && apk add --no-cache tar \
    && apk add --no-cache gzip \
    && apk add  curl \
    && openssl version
RUN chown -R app:app /usr/src/app
RUN chmod 755 /usr/src/app 
RUN chmod 777 /opt
### App
WORKDIR /usr/src/app
USER app


