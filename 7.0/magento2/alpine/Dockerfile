FROM php:7.0-fpm-alpine

# Install Dependencies
RUN apk add --update --no-cache \
        # gd
        freetype-dev libpng-dev libwebp-dev jpeg-dev \
        # mcrypt
        libmcrypt-dev \
        # xsl
        libxslt-dev \ 
        # intl
        icu-dev \
        # Other
        bash \
    && docker-php-ext-configure \
       gd --with-png-dir=/usr/include/ --with-jpeg-dir=/usr/include/ --with-webp-dir=/usr/include/ --with-freetype-dir=/usr/include/ \
    && docker-php-ext-install -j$(getconf _NPROCESSORS_ONLN) \
       # intl iconv mcrypt gd pdo_mysql zip soap json xsl mbstring simplexml xml opcache
       gd mcrypt xsl intl pdo_mysql mysqli zip soap opcache

# Create entrypoint for custom shell commands
RUN mkdir /docker-entrypoint-initphp.d
COPY docker-entrypoint.sh /usr/local/bin/
RUN ln -s /usr/local/bin/docker-entrypoint.sh /entrypoint.sh # backwards compat
ENTRYPOINT ["docker-entrypoint.sh"]

CMD ["php-fpm"]
