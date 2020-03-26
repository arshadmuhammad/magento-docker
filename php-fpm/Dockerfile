FROM php:7.3-fpm

RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libpng-dev \
        libmcrypt-dev \
        libxslt1-dev \
        libzip-dev \
        libonig-dev \
        && docker-php-ext-configure gd --with-freetype-dir=/usr/include --with-jpeg-dir=/usr/include \
        && docker-php-ext-install -j$(nproc) gd dom intl mbstring sockets pdo_mysql xsl zip soap bcmath pcntl \
        && curl -sL https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin/ --filename=composer \
        && composer --version

RUN mkdir -p /var/www/html; \
    chown -R www-data:www-data /var/www/html; \
    chmod 777 /var/www/html; \
    usermod -u 1000 www-data

CMD ["php-fpm", "-F"]
