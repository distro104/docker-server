FROM php:8.4-cli

# Dependências do sistema
RUN apt-get update && apt-get install -y \
git \
curl \
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

# Limpa cache
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

# Extencoes do PHP
COPY --from=ghcr.io/mlocati/php-extension-installer /usr/bin/install-php-extensions /usr/local/bin/
RUN install-php-extensions gd xdebug
RUN install-php-extensions pdo pdo_mysql pdo_pgsql pdo_sqlite mbstring bcmath zip gd

# Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

WORKDIR /var/www