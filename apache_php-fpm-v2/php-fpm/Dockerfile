FROM php:8.0.13-fpm
COPY etc/php-custom.ini /usr/local/etc/php/conf.d/php-custom.ini
COPY etc/php-fpm.conf /usr/local/etc/php-fpm.conf
COPY etc/php-fpm.d/www.conf /usr/local/etc/php-fpm.d/www.conf 
RUN apt-get update \
  && apt-get install -y libzip-dev libjpeg-dev libpng-dev libwebp-dev \
  && docker-php-ext-install zip \
  && docker-php-ext-install pdo_mysql \
  && docker-php-ext-configure gd --with-jpeg --with-webp && docker-php-ext-install -j$(nproc) gd \
  && docker-php-ext-install opcache 
