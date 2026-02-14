FROM php:8.5-fpm-alpine

ARG USER_ID=1000
ARG GROUP_ID=1000

RUN apk add --no-cache \
    bash \
    curl \
    git \
    unzip \
    icu-dev \
    libzip-dev \
    oniguruma-dev \
    && docker-php-ext-install \
    pdo \
    pdo_mysql \
    mbstring \
    intl \
    zip \
    opcache

RUN addgroup -g ${GROUP_ID} app \
    && adduser -D -G app -u ${USER_ID} app

WORKDIR /var/www
USER app
