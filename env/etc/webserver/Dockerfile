FROM php:7.3-apache

RUN apt-get -y update
RUN apt-get -y upgrade

# Important Libraries
RUN apt-get install -y apt-utils build-essential git curl libcurl4 zip unzip software-properties-common

# Composer
RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" && \
    php composer-setup.php --install-dir=/usr/local/bin --filename=composer && \
    php -r "unlink('composer-setup.php');"

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

# Install Webmin
RUN echo "deb http://download.webmin.com/download/repository sarge contrib"  >> /etc/apt/sources.list.d/webmin.list && \
    wget http://www.webmin.com/jcameron-key.asc && \
    apt-key add jcameron-key.asc && \
    apt-get update && \
    apt-get install webmin

# Enable Apache Modules
RUN a2enmod rewrite headers

EXPOSE 80 8080 443 10000
