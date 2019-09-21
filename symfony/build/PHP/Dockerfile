FROM php:7.3-fpm-alpine

RUN apk update \
    && apk add bash git openssh ca-certificates wget freetype libpng libjpeg-turbo freetype-dev libpng-dev libjpeg-turbo-dev postgresql-dev libxml2-dev \
    && docker-php-ext-install gd pdo pdo_mysql pdo_pgsql pgsql xml soap \
    && rm /var/cache/apk/* \
    && php -r "readfile('https://getcomposer.org/installer');" | php -- --install-dir=/usr/local/bin --filename=composer \
    && chmod +x /usr/local/bin/composer

COPY init.sh /
RUN chmod +x /init.sh
CMD /init.sh
