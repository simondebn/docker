# Dockerfile
FROM php:7.4-cli

# Remove restirction from installing PHP packages
RUN rm /etc/apt/preferences.d/no-debian-php

# Install required packages
RUN apt update && apt install wget php-mysql php-json php-mbstring php-xml php-curl -y

# Extension install
RUN docker-php-ext-install mysqli pdo pdo_mysql

# Install Symfony package
RUN wget https://get.symfony.com/cli/installer -O - | bash && mv /root/.symfony/bin/symfony /usr/local/bin/symfony

# Open port 80
EXPOSE 80

# Run it
CMD cd /var/www/html && symfony server:start --no-tls --port=80
