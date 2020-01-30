FROM php:7.3-apache

RUN apt-get -y update
RUN apt-get -y upgrade

# Important Libraries
RUN apt-get install -y apt-utils build-essential git curl libcurl4 libcurl4-gnutls-dev libzip-dev zip unzip

# Composer
COPY --from=composer:latest /usr/bin/composer /usr/local/bin/composer

# PHP Extensions
RUN apt-get install -y libmcrypt-dev
RUN apt-get install -y libsqlite3-dev libsqlite3-0 default-mysql-client
RUN docker-php-ext-install pdo_mysql
RUN docker-php-ext-install pdo_sqlite
RUN docker-php-ext-install mysqli
RUN docker-php-ext-install curl
RUN docker-php-ext-install tokenizer
RUN docker-php-ext-install json
RUN apt-get -y install zlib1g-dev
RUN docker-php-ext-install zip
RUN apt-get -y install libicu-dev
RUN docker-php-ext-install -j$(nproc) intl
RUN docker-php-ext-install mbstring

# Enable Apache Modules
RUN a2enmod rewrite headers
