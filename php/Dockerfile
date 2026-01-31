FROM php:8.4-fpm

RUN apt-get update && apt-get install -y \
    git \
    curl \
    zip \
    unzip \
    nodejs \
    npm \
    libzip-dev \
    libpng-dev \
    libonig-dev \
    libpq-dev \
    mariadb-client \
    bash \
    && docker-php-ext-install \
        pdo \
        pdo_mysql \
        pdo_pgsql \
        pdo_sqlite \
        mbstring \
        bcmath \
        zip \
        gd \
        ctype \
        fileinfo \
        json \
        openssl \
        tokenizer \
        xml

    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

COPY --from=composer:2 /usr/bin/composer /usr/bin/composer

WORKDIR /var/www

