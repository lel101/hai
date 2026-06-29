FROM richarvey/nginx-php-fpm:3.1.6

WORKDIR /var/www/html

COPY app/ /var/www/html/
COPY docker/nginx.conf /etc/nginx/sites-available/default.conf
COPY docker/entrypoint.sh /entrypoint.sh

RUN chmod +x /entrypoint.sh

RUN composer install --no-dev --optimize-autoloader

RUN chmod -R 775 storage bootstrap/cache

EXPOSE 80

ENTRYPOINT ["/entrypoint.sh"]