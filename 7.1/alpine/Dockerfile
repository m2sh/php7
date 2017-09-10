FROM php:7.1-fpm-alpine

# intl, zip, soap
RUN apk add --update --no-cache libintl icu icu-dev libxml2-dev \
    && docker-php-ext-install intl zip soap

# mysqli, pdo, pdo_mysql
RUN docker-php-ext-install mysqli pdo pdo_mysql

# mcrypt, gd, iconv
RUN apk add --update --no-cache freetype-dev libjpeg-turbo-dev libmcrypt-dev libpng-dev \
    && docker-php-ext-install iconv mcrypt \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install gd

# gmp, bcmath
RUN apk add --update --no-cache gmp gmp-dev \
    && docker-php-ext-install gmp bcmath

# redis, apcu
RUN docker-php-source extract \
    && apk add --no-cache --virtual .phpize-deps-configure $PHPIZE_DEPS \
    && pecl install redis \
    && pecl install apcu \
    && docker-php-ext-enable redis apcu \
    && apk del .phpize-deps-configure \
    && docker-php-source delete

# imagick
RUN apk add --update --no-cache autoconf g++ imagemagick-dev libtool make pcre-dev \
    && pecl install imagick \
    && docker-php-ext-enable imagick \
    && apk del autoconf g++ libtool make pcre-dev

# git client, mysql-client
RUN apk add --update --no-cache git mysql-client

# pcntl
RUN docker-php-ext-install pcntl 

RUN sed -i -e 's/listen.*/listen = 0.0.0.0:9000/' /usr/local/etc/php-fpm.conf

RUN echo "expose_php=0" > /usr/local/etc/php/php.ini

CMD ["php-fpm"]

