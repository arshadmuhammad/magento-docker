FROM nginx:latest

COPY ./magento.conf /etc/nginx/conf.d/default.conf

COPY ./composer/auth.json /var/www/.composer/auth.json

RUN mkdir -p /var/www/html; \
    chown -R www-data:www-data /var/www/html; \
    chmod 777 /var/www/html; \
    usermod -u 1000 www-data

RUN chown -R www-data:www-data /var/www/.composer; \
    chmod 777 /var/www/.composer; \
    usermod -u 1000 www-data

WORKDIR /var/www/html
