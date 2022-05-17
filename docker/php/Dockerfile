FROM php:8.1-fpm-alpine AS base

LABEL maintainer="Matheus Bloise <matheusbloisev@hotmail.com>"

WORKDIR /app

COPY --from=composer /usr/bin/composer /usr/bin/composer

RUN apk --update add --no-cache ${PHPIZE_DEPS} \
    && rm -rf /var/cache/apk/*

FROM base AS development

ADD conf.d/dev.ini "$PHP_INI_DIR/conf.d/php.ini"

RUN mv "$PHP_INI_DIR/php.ini-development" "$PHP_INI_DIR/php.ini" \
    && pecl install xdebug-3.1.2 \
    && docker-php-ext-enable xdebug


FROM base AS production

ADD conf.d/prod.ini "$PHP_INI_DIR/conf.d/php.ini"

RUN mv "$PHP_INI_DIR/php.ini-production" "$PHP_INI_DIR/php.ini" \
    && docker-php-ext-install opcache