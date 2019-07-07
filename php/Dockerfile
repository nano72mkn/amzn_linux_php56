ARG PHP_VER
FROM php:${PHP_VER}

############
# Composer:
############
RUN curl -sS https://getcomposer.org/installer | php
RUN mv composer.phar /usr/local/bin/composer

WORKDIR /var/www
