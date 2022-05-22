FROM php:7.4.28-fpm-alpine AS base

LABEL maintainer="Matheus Bloise <matheusbloisev@hotmail.com>"

WORKDIR /app

ADD https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/

COPY --from=composer /usr/bin/composer /usr/bin/composer

RUN apk --update add --no-cache ${PHPIZE_DEPS} \
    && chmod +x /usr/local/bin/install-php-extensions \
    && rm -rf /var/cache/apk/*

FROM base AS development

ADD conf.d/dev.ini "$PHP_INI_DIR/conf.d/php.ini"

RUN mv "$PHP_INI_DIR/php.ini-development" "$PHP_INI_DIR/php.ini" \
    && pecl install xdebug-3.1.4 \
    && docker-php-ext-enable xdebug


FROM base AS production

ADD conf.d/prod.ini "$PHP_INI_DIR/conf.d/php.ini"

RUN mv "$PHP_INI_DIR/php.ini-production" "$PHP_INI_DIR/php.ini" \
    && install-php-extensions opcache