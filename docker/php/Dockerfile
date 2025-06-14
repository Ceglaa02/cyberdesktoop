FROM php:8.4-fpm

RUN apt-get update && apt-get install -y \
    unzip \
    libzip-dev \
    git \
 && docker-php-ext-install pdo pdo_mysql

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN pecl install xdebug \
    && docker-php-ext-enable xdebug

COPY ./xdebug.ini /usr/local/etc/php/conf.d/xdebug.ini

RUN chown -R www-data:www-data /var/www/html
WORKDIR /var/www/html

CMD ["php-fpm"]