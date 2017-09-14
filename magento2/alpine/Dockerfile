FROM php:7.0-fpm-alpine

# Install extensions
RUN apk add --update --no-cache \
        # gd
        freetype-dev libpng-dev libwebp-dev jpeg-dev \
        # mcrypt
        libmcrypt-dev \
        # xsl
        libxslt-dev \ 
        # intl
        icu-dev \
    && docker-php-ext-configure \
       gd --with-png-dir=/usr/include/ --with-jpeg-dir=/usr/include/ --with-webp-dir=/usr/include/ --with-freetype-dir=/usr/include/ \
    && docker-php-ext-install -j$(getconf _NPROCESSORS_ONLN) \
       # intl iconv mcrypt gd pdo_mysql zip soap json xsl mbstring simplexml xml opcache
       gd mcrypt xsl intl pdo_mysql zip soap opcache

CMD ["php-fpm"]
