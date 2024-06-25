FROM alpine:latest

RUN apk upgrade
RUN apk add --no-cache --repository=https://dl-cdn.alpinelinux.org/alpine/edge/community hugo
RUN apk add git

ENV GID=1000
ENV UID=1000

EXPOSE 1313

RUN addgroup --gid "$GID" -S hugo && adduser -S hugo -G hugo --uid "$UID"

RUN mkdir -p /usr/src/app && \
    chown -R hugo:hugo /usr/src/app

WORKDIR /usr/src/app

USER hugo

ENTRYPOINT ["hugo"]
