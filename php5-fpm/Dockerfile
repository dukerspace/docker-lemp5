FROM php:5.6-fpm

MAINTAINER Montol Saklor <montol saklord@gmail.com>

ENV TZ=Asia/Bangkok
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

# Install extensions
RUN apt-get update \
	&& apt-get install -y libmcrypt-dev zip zlib1g-dev curl libpng-dev libjpeg-dev libfreetype6-dev libmagickwand-dev \
	&& docker-php-ext-install -j$(nproc) mcrypt \
	&& docker-php-ext-install pdo_mysql \
	&& docker-php-ext-install zip \
	&& docker-php-ext-install pcntl \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
	&& docker-php-ext-install gd \
	&& docker-php-ext-install soap \
    && pecl install imagick \
    && docker-php-ext-enable imagick
    
WORKDIR /var/www/
