# Usa la imagen oficial de PHP con Apache
FROM php:8.2-apache

# Instala las dependencias necesarias para las extensiones y compilación
RUN apt-get update && apt-get install -y \
    libzip-dev \
    libpng-dev \
    unzip \
    gnupg \
    libjpeg62-turbo-dev \
    libfreetype6-dev \
    zlib1g-dev \
    libonig-dev \
    unixodbc unixodbc-dev \
    gcc g++ make autoconf libc-dev pkg-config git wget \
    libssl-dev libxml2-dev curl libcurl4-openssl-dev \
    && docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-install mbstring zip gd

# Agrega la clave y el repo de Microsoft para msodbcsql17
RUN wget https://packages.microsoft.com/keys/microsoft.asc && \
    apt-key add microsoft.asc && \
    curl https://packages.microsoft.com/config/debian/10/prod.list > /etc/apt/sources.list.d/mssql-release.list

RUN apt-get update && ACCEPT_EULA=Y apt-get install -y msodbcsql17

# Intenta instalar sqlsrv y pdo_sqlsrv desde PECL, si falla compila desde GitHub
RUN pecl install sqlsrv pdo_sqlsrv \
    && docker-php-ext-enable pdo_sqlsrv sqlsrv \
    || ( \
        git clone --depth=1 https://github.com/microsoft/msphpsql.git /tmp/msphpsql && \
        cd /tmp/msphpsql/source/sqlsrv && phpize && ./configure && make && make install && \
        cd /tmp/msphpsql/source/pdo_sqlsrv && phpize && ./configure && make && make install && \
        docker-php-ext-enable sqlsrv pdo_sqlsrv && \
        rm -rf /tmp/msphpsql \
    )

# Habilita los módulos de Apache necesarios
RUN a2enmod rewrite

# Instala Composer globalmente
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer