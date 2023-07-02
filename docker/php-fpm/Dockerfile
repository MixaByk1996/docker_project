FROM php:7.4-fpm

RUN apt-get update && apt-get install -y\
    libpq-dev\
    wget \
    zlib1g-dev \
    libmcrypt-dev \
    libzip-dev \
    openssl \
    libpng-dev \
    libicu-dev \
    libfreetype6-dev \
    libjpeg-dev



RUN docker-php-ext-configure intl
RUN docker-php-ext-configure gd \
    --with-jpeg=/usr/include/ \
    --with-freetype=/usr/include/

RUN docker-php-ext-install mysqli
RUN docker-php-ext-install pdo pdo_mysql gd intl

RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" && php composer-setup.php && php -r "unlink('composer-setup.php');" && mv composer.phar /usr/local/bin/composer

WORKDIR /www






