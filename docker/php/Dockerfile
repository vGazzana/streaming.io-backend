FROM php:8.2-fpm

WORKDIR /var/www/html

RUN apt-get update && apt-get install -y \
	zip unzip curl git libpng-dev libonig-dev libxml2-dev libzip-dev libjpeg-dev libfreetype6-dev libpq-dev \
	&& docker-php-ext-install pdo_mysql pdo_pgsql mbstring zip exif pcntl bcmath gd

RUN pecl install redis && docker-php-ext-enable redis

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer
