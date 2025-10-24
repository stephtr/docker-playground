FROM php:8.4.14-apache
RUN apt-get update && apt-get install -y zlib1g-dev libpng-dev libjpeg-dev
RUN docker-php-ext-install pdo_mysql \
    && docker-php-ext-install mysqli \
    && docker-php-ext-configure gd --with-jpeg \
    && docker-php-ext-install gd \
    && a2enmod rewrite \
    && mv "$PHP_INI_DIR/php.ini-production" "$PHP_INI_DIR/php.ini" \
    && rm -rf /var/lib/apt/lists/