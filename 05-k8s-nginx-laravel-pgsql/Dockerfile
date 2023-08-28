FROM php:8.2-fpm

USER root

RUN apt-get update

RUN apt-get install -y curl

# Install pgsql
RUN apt-get install -y libpq-dev && docker-php-ext-install pdo pdo_pgsql

# Install composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Install git
RUN apt-get -y install git

# Install Zip extension
RUN apt install zip unzip
RUN apt-get install -y libzip-dev \
    && docker-php-ext-install zip

COPY ./code /var/www/html

RUN php artisan key:generate

RUN chown -R www-data:www-data /var/www/html/

EXPOSE 9000
