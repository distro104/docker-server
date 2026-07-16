FROM php:8.4-fpm

# Dependências do sistema
RUN apt-get update && apt-get install -y \
curl \
git \
zip \
unzip \
bash \
# Biblioteca de desenvolvimento
libzip-dev \
libpng-dev \
libonig-dev \
libpq-dev \
libxml2-dev \
# Banco de dados
mariadb-client \
# Node / NPM
nodejs \
npm \
gcc g++ make

# Copia o arquivo de configuração do PHP
COPY php.ini /usr/local/etc/php/php.ini

# Extencoes do PHP
COPY --from=ghcr.io/mlocati/php-extension-installer /usr/bin/install-php-extensions /usr/local/bin/
RUN install-php-extensions \
pdo_mysql \
pdo_pgsql \
pdo_sqlite \
mbstring \
bcmath \
zip \
gd \
intl \
soap \
# imagemagick \
xdebug

RUN if [ "$INSTALL_XDEBUG" = "true" ]; then \
      install-php-extensions xdebug; \
    fi

# Copia o arquivo de configuração do Xdebug
COPY xdebug.ini /usr/local/etc/php/conf.d/99-xdebug.ini

# Limpa cache
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

# Composer
# RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN curl -sS https://getcomposer.org/installer -o composer-setup.php \
    && php composer-setup.php --install-dir=/usr/local/bin --filename=composer \
    && rm composer-setup.php

WORKDIR /var/www