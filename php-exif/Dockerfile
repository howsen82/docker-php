FROM php:8.1.16-zts-alpine3.17

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin --filename=composer
RUN docker-php-ext-install exif

WORKDIR /var/www/html

COPY /www/ /var/www/html/

RUN chown -R www-data /var/www/html

USER www-data
RUN composer require erusev/parsedown

VOLUME [ "/var/www/html", "/var/www/html/vendor" ]