FROM php:7.3.25-fpm
RUN apt-get update -y && apt-get install -y libcurl4-openssl-dev libxml2-dev zip libzip-dev libpng-dev && apt-get clean -y
RUN docker-php-ext-install mysqli pdo pdo_mysql curl xml gd zip
