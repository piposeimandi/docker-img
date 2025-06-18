# Usa la imagen oficial de PHP con Apache
FROM php:8.4-apache

# Instala las dependencias necesarias
RUN apt-get update && apt-get install -y --no-install-recommends \
    unzip \
    nano \
    iputils-ping \
    libjpeg-dev \
    libpng-dev \
    libfreetype6-dev && \
    docker-php-ext-configure gd --with-freetype --with-jpeg && \
    docker-php-ext-install bcmath gd && \
    a2enmod rewrite && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

# Instala Composer globalmente
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
