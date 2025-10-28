FROM php:7.2-apache

RUN apt-get update && apt-get install -y \
    libcurl4-openssl-dev \
    libonig-dev \
    libzip-dev \
    unzip \
    curl

RUN docker-php-ext-install mysqli pdo pdo_mysql curl
RUN docker-php-ext-enable mysqli opcache curl

RUN a2enmod rewrite
COPY ./php.ini /usr/local/etc/php/conf.d/php.ini
WORKDIR /var/www/html

EXPOSE 80