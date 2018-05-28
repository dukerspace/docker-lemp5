FROM php:5.6-fpm

MAINTAINER Montol Saklor <montol saklord@gmail.com>

ENV TZ=Asia/Bangkok
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

RUN apt-get update && apt-get install -y \
    git \
    unzip
    
WORKDIR /var/www/
