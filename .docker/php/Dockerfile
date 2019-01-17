FROM php:7.2.10-fpm

RUN apt-get update \
    && apt-get install -y --no-install-recommends vim curl debconf subversion git \
    build-essential locales acl wget \
    sudo

RUN docker-php-ext-install pdo pdo_mysql

COPY php.ini /usr/local/etc/php/php.ini
COPY php-fpm-pool.conf 	/usr/local/etc/php/pool.d/www.conf

RUN curl -sSk https://getcomposer.org/installer | php -- --disable-tls && \
	mv composer.phar /usr/local/bin/composer

RUN groupadd dev -g 999
RUN useradd dev -g dev -d /home/dev -m
RUN passwd -d dev

WORKDIR /home/wwwroot/

EXPOSE 9000
CMD ["php-fpm"]
