FROM php:8.3-cli

RUN apt-get update && \
	apt-get install -y \
	libcurl4-openssl-dev \
	libfreetype6-dev libjpeg62-turbo-dev libpng-dev \
	libzip-dev \
	git curl zip unzip \
	&& apt-get clean \
	&& rm -rf /var/lib/apt/lists/*

RUN docker-php-ext-install curl gd zip

RUN pecl install --onlyreqdeps --force redis \
	&& rm -rf /tmp/pear \
	&& docker-php-ext-enable redis

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN composer require \
    psy/psysh 

ENV PATH="${PATH}:/vendor/bin"

