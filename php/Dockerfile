FROM php:8.3-fpm-alpine

RUN apk add --no-cache \
    git \
    curl \
    libpng-dev \
    oniguruma-dev \
    libxml2-dev \
    zip \
    unzip

RUN docker-php-ext-install pdo_mysql mbstring exif pcntl gd

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

COPY ./src/composer.json ./src/composer.lock ./

RUN composer install --no-scripts --no-autoloader

WORKDIR /var/www/html

COPY src .

RUN composer dump-autoload --optimize

EXPOSE 9000

CMD ["php-fpm"]
