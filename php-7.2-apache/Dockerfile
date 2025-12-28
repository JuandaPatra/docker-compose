FROM php:7.2-apache

# Fix Debian Buster EOL
RUN sed -i 's|deb.debian.org|archive.debian.org|g' /etc/apt/sources.list \
 && sed -i 's|security.debian.org|archive.debian.org|g' /etc/apt/sources.list \
 && sed -i '/buster-updates/d' /etc/apt/sources.list

RUN apt-get update && apt-get install -y \
    libcurl4-openssl-dev \
    libonig-dev \
    libzip-dev \
    unzip \
    curl \
 && docker-php-ext-install mysqli pdo pdo_mysql zip \
 && docker-php-ext-enable mysqli opcache \
 && apt-get clean \
 && rm -rf /var/lib/apt/lists/*

RUN a2enmod rewrite

COPY php.ini /usr/local/etc/php/conf.d/php.ini

WORKDIR /var/www/html
EXPOSE 80
