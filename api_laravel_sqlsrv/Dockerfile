# Usa la imagen oficial de PHP con Apache
FROM php:8.4-apache

# Instala las dependencias necesarias para las extensiones
RUN apt-get update && apt-get install -y \
    libzip-dev \
    libpng-dev \
    unzip \
    gnupg \
    libjpeg62-turbo-dev \
    libfreetype6-dev \
    zlib1g-dev \
    libonig-dev \
    && docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-install mbstring zip gd

    RUN apt-get install -y \
    unixodbc unixodbc-dev \
    gcc g++ make autoconf libc-dev pkg-config

# Instala la extensión sqlsrv
RUN pecl install sqlsrv pdo_sqlsrv \
    && docker-php-ext-enable pdo_sqlsrv sqlsrv

#RUN curl https://packages.microsoft.com/keys/microsoft.asc | apt-key add -
RUN apt-get update && apt-get install -y wget
RUN wget https://packages.microsoft.com/keys/microsoft.asc
RUN apt-key add microsoft.asc

RUN curl https://packages.microsoft.com/config/debian/10/prod.list > /etc/apt/sources.list.d/mssql-release.list
RUN apt-get update && ACCEPT_EULA=Y apt-get install -y msodbcsql17

# Habilita los módulos de Apache necesarios
RUN a2enmod rewrite

# Instala Composer globalmente
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
