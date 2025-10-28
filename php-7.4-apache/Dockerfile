FROM php:7.4-apache

RUN docker-php-ext-install mysqli pdo pdo_mysql
RUN docker-php-ext-enable mysqli opcache

# Install MongoDB extension via PECL
RUN pecl install mongodb-1.11.1 \
    && docker-php-ext-enable mongodb

RUN a2enmod rewrite

WORKDIR /var/www/html

EXPOSE 80
