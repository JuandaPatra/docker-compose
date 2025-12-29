# Gunakan base image PHP 8.2 dengan Apache
FROM php:8.2-apache

# Install ekstensi yang umum dipakai (pdo_mysql, gd, zip, dll)
RUN apt-get update && apt-get install -y \
    libcurl4-openssl-dev \
    libonig-dev \
    libzip-dev \
    unzip \
    curl


RUN docker-php-ext-install mysqli pdo pdo_mysql curl
RUN docker-php-ext-enable mysqli opcache curl

# Aktifkan mod_rewrite Apache
RUN a2enmod rewrite

# Set working directory
WORKDIR /var/www/html

# Expose port 80
EXPOSE 80
