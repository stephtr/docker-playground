FROM php:8.3-apache
RUN apt-get update && apt-get install -y zlib1g-dev libpng-dev libjpeg-dev libwebp-dev libfreetype6-dev
RUN docker-php-ext-install pdo_mysql \
    && docker-php-ext-install mysqli exif intl \
    && docker-php-ext-configure gd --with-jpeg --with-webp --with-freetype \
    && docker-php-ext-install gd \
    && a2enmod rewrite \
    && mv "$PHP_INI_DIR/php.ini-production" "$PHP_INI_DIR/php.ini" \
    && rm -rf /var/lib/apt/lists/
