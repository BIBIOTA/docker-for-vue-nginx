FROM node:lts-alpine3.10

RUN apk update && apk add bash

WORKDIR /app

RUN apk update \
    && apk add --update python make g++ \
    && npm install -g npm \
    && npm install -g @vue/cli

RUN apk add --update python make g++\
   && rm -rf /var/cache/apk/*

WORKDIR /app

# Entrypoint
COPY ./app-entrypoint.sh /
RUN chmod -R 0755 /app-entrypoint.sh
ENTRYPOINT /app-entrypoint.sh