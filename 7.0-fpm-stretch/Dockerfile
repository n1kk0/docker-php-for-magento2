FROM php:7.0-fpm-stretch

MAINTAINER "Jeremy CURNY" <jeremy.curny.pro@gmail.com>

ARG DEBIAN_FRONTEND=noninteractive

RUN \
  apt-get install -y \
    libfreetype6-dev libicu-dev libjpeg62-turbo-dev libmcrypt-dev libpng-dev libxml2-dev libxslt-dev
    
RUN \
  docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ --with-png-dir=/usr/include/ \
  && docker-php-ext-install gd
  
RUN \
  docker-php-ext-install bcmath mcrypt mysqli intl opcache pdo_mysql soap xsl zip
  
RUN \
  curl -sLS -o /usr/local/bin/composer https://getcomposer.org/composer.phar \
  && chmod +x /usr/local/bin/composer
