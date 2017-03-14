######
# See: https://hub.docker.com/_/php/
######

FROM php:7.0.5-fpm
MAINTAINER Dzung Nguyen <dung.nguyen@asiantech.vn>

######
# You can install php extensions using docker-php-ext-install
# https://github.com/docker-library/php/issues/75
######

RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libpng12-dev \
        zlib1g-dev libicu-dev g++ \
    && docker-php-ext-install -j$(nproc) iconv mcrypt \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd
## xdebug
RUN yes | pecl install xdebug \
    && echo "zend_extension=$(find /usr/local/lib/php/extensions/ -name xdebug.so)" > /usr/local/etc/php/conf.d/xdebug.ini \
    && echo "xdebug.remote_enable=on" >> /usr/local/etc/php/conf.d/xdebug.ini \
    && echo "xdebug.remote_autostart=off" >> /usr/local/etc/php/conf.d/xdebug.ini
## install more extension
RUN apt install -y libldb-dev
RUN apt install -y libxml2-dev
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin/ --filename=composer

RUN docker-php-ext-install zip
RUN docker-php-ext-install session
RUN docker-php-ext-install pdo
RUN docker-php-ext-install mysqli
RUN docker-php-ext-install mbstring
RUN docker-php-ext-install tokenizer
RUN docker-php-ext-install pdo_mysql
RUN docker-php-ext-install exif
RUN docker-php-ext-install fileinfo
RUN docker-php-ext-configure intl \
  && docker-php-ext-install intl
RUN apt-get install -y libcurl3-dev && docker-php-ext-install curl
RUN docker-php-ext-install xml
