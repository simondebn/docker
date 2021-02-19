FROM php:7.4-apache

RUN apt-get update && apt-get upgrade -y && apt-get install -y \
    git \
    bash
RUN docker-php-ext-install mysqli pdo pdo_mysql
RUN a2enmod rewrite
RUN service apache2 restart

COPY --from=composer:latest /usr/bin/composer /usr/local/bin/composer
COPY rest.conf /etc/apache2/sites-enabled/000-default.conf
#COPY php.ini /usr/local/etc/php
