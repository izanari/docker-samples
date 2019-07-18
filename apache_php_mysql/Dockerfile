FROM php:7.2-apache
RUN \
    { apt-get update; \
    apt-get -y install default-mysql-client-core ; \
    docker-php-ext-install mysqli ; \
    docker-php-ext-configure mysqli ; \
    }