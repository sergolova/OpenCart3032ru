FROM php:7.4-fpm

RUN apt-get update \
    && apt-get install -y \
        gcc \
        make \
        autoconf \
        libc-dev \
        libzip-dev \
        unzip \
        pkg-config \
        libssl-dev

RUN apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libpng-dev

RUN pecl install \
        xdebug-2.9.8

RUN docker-php-ext-install pdo_mysql \
    && docker-php-ext-install zip \
    && docker-php-ext-install mysqli

RUN docker-php-ext-install iconv \
    && docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-install gd
