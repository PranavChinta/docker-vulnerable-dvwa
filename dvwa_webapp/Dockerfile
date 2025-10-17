FROM php:7.4-apache

RUN apt-get update && apt-get install -y \
    libpng-dev libjpeg62-turbo-dev libfreetype6-dev zlib1g-dev \
 && docker-php-ext-configure gd --with-freetype --with-jpeg \
 && docker-php-ext-install gd mysqli pdo_mysql

WORKDIR /var/www/html

COPY dvwa/ /var/www/html/
COPY config.inc.php /var/www/html/config/
COPY php.ini /usr/local/etc/php/php.ini

RUN rm -f /var/www/html/index.html && chown -R www-data:www-data /var/www/html

EXPOSE 80
