FROM imega/base-builder:1.1.0

MAINTAINER Dmitry Gavriloff <info@imega.ru>

ENV COMPOSER_CACHE_DIR=/cache

RUN echo "@stale http://dl-4.alpinelinux.org/alpine/edge/testing" >> /etc/apk/repositories && \
    apk add --update curl \
        git \
        php7@stale \
        php7-common@stale \
        php7-cgi@stale \
        php7-phar@stale \
        php7-json@stale \
        php7-ctype@stale \
        php7-xml@stale \
        php7-dom@stale \
        php7-openssl@stale \
        php7-mbstring@stale && \
    ln -s /usr/bin/php7 /usr/bin/php && \
    curl -k -sS https://getcomposer.org/download/1.1.0-RC/composer.phar -o /usr/local/bin/composer && \
    chmod +x /usr/local/bin/composer && \
    apk del curl && \
    rm -rf /var/cache/apk/*

ENTRYPOINT ["/usr/local/bin/composer"]
