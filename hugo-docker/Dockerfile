FROM alpine:latest

RUN apk upgrade
RUN apk add --no-cache --repository=https://dl-cdn.alpinelinux.org/alpine/edge/community hugo

EXPOSE 1313

RUN mkdir -p /usr/src/app

WORKDIR /usr/src/app

ENTRYPOINT ["hugo"]
