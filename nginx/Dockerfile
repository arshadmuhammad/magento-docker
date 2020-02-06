FROM nginx:latest

COPY ./magento.conf /etc/nginx/conf.d/default.conf

RUN mkdir -p /var/www/html; \
    chown -R www-data:www-data /var/www/html; \
    chmod 777 /var/www/html; \
    usermod -u 1000 www-data

WORKDIR /var/www/html
