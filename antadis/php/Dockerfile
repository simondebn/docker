FROM php:5.6-apache

RUN apt-get update && apt-get upgrade -y && apt-get install -y \
    git \
    vim 
RUN docker-php-ext-install mysql mysqli pdo pdo_mysql
COPY --from=composer:latest /usr/bin/composer /usr/local/bin/composer
