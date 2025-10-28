FROM php:5.6-apache

RUN docker-php-ext-install mysqli pdo pdo_mysql
RUN docker-php-ext-enable mysqli opcache

RUN a2enmod rewrite

WORKDIR /var/www/html

EXPOSE 80
