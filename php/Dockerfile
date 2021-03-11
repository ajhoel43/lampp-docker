FROM php:5.6-fpm-alpine
RUN apk update; \
    apk upgrade;
RUN docker-php-ext-install mysqli pdo pdo_mysql
RUN apk add freetype libpng libjpeg-turbo freetype-dev libpng-dev libjpeg-turbo-dev libmcrypt-dev
RUN docker-php-ext-install -j$(nproc) iconv mcrypt
RUN docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ 
RUN docker-php-ext-install -j$(nproc) gd
RUN docker-php-ext-enable pdo pdo_mysql mysqli
COPY php.ini /usr/local/etc/php/php.ini