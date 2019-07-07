ARG AMZN_LINUX_VER

FROM amazonlinux:${AMZN_LINUX_VER}

############
# yum update:
############
USER root
RUN yum -y update
RUN yum clean all

# Development Tools install
RUN yum -y groupinstall "Development Tools"

############
# PHP:
############
ARG PHP_VER
RUN yum -y install \
    php${PHP_VER} \
    php${PHP_VER}-devel \
    php${PHP_VER}-mysqlnd \
    php${PHP_VER}-mbstring \
    php${PHP_VER}-gd

############
# Composer:
############
RUN curl -sS https://getcomposer.org/installer | php
RUN mv composer.phar /usr/local/bin/composer

WORKDIR /var/www
