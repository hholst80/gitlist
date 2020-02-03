FROM alpine:3.10
ARG version=1.0.2
ADD https://github.com/klaussilveira/gitlist/releases/download/$version/gitlist-$version.tar.gz /gitlist.tar.gz
RUN tar -xzf gitlist.tar.gz

FROM php:7.4.2-fpm
RUN apt-get update && apt-get install -y git && rm -r /var/lib/apt/lists/*
COPY --from=0 /gitlist/ .
RUN mkdir --mode=0777 cache
COPY config.ini .
