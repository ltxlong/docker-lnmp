FROM alpine:latest
MAINTAINER ltxlong

# install php-fpm
RUN apk --update add \
        php7 \
        php7-apcu \
        php7-bz2 \
        php7-bcmath \
        php7-dom \
        php7-cli \
        php7-ctype \
        php7-curl \
        php7-common \
        php7-calendar \
        php7-exif \
        php7-ftp \
        php7-fpm \
        php7-fileinfo \
        php7-gd \
        php7-gmp \
        php7-gettext \
        php7-ldap \
        php7-iconv \
        php7-intl \
        php7-imap \
        php7-imagick \
        php7-json \
        php7-mbstring \
        php7-mcrypt \
        php7-mysqlnd \
        php7-mysqli \
        php7-sqlite3 \
        php7-odbc \
        php7-opcache \
        php7-openssl \
        php7-pdo \
        php7-pdo_odbc \
        php7-pdo_dblib \
        php7-pdo_mysql \
        php7-pdo_pgsql \
        php7-pdo_sqlite \
        php7-pear \
        php7-phar \
        php7-pgsql \
        php7-pcntl \
        php7-posix \
        php7-sockets \
        php7-session \
        php7-soap \
        php7-tokenizer \
        php7-xdebug \
        php7-xsl \
        php7-xml \
        php7-xmlrpc \
        php7-xmlreader \
        php7-simplexml \
        php7-zlib \
        php7-zip \
    && rm -rf /var/cache/apk/*

# ensure www-data user exists
RUN set -x \
    && addgroup -g 82 -S www-data \
    && adduser -u 82 -D -S -G www-data www-data

ENV PHP_EXTRA_CONFIGURE_ARGS --enable-fpm --with-fpm-user=www-data --with-fpm-group=www-data

EXPOSE 9000

CMD ["php-fpm7","-F"]