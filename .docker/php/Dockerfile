FROM php:7.2.10-fpm

RUN apt-get update \
    && apt-get install -y --no-install-recommends vim curl debconf subversion git \
    build-essential locales acl wget \
    sudo

RUN docker-php-ext-install pdo pdo_mysql

RUN curl -sSk https://getcomposer.org/installer | php -- --disable-tls && \
	mv composer.phar /usr/local/bin/composer

WORKDIR /home/wwwroot/

EXPOSE 9000
CMD ["php-fpm"]
