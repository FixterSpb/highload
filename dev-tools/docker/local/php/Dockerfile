FROM phpdockerio/php74-fpm

ARG DEBIAN_FRONTEND=noninteractive

WORKDIR /app

RUN apt-get update \
    && apt-get install -y php7.4-pgsql php7.4-xml php7.4-gd php7.4-curl

#add user
ARG USER_ID=1000
RUN addgroup --gid $USER_ID dev \
    && useradd -u $USER_ID -g $USER_ID -s /bin/bash -d /home/develop develop \
    && mkdir /home/develop \
    && chown 1000:1000 /home/develop \
    && addgroup develop www-data

EXPOSE 9000
EXPOSE 8080
