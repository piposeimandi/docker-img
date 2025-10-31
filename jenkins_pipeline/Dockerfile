# Usa la imagen oficial de PHP con Apache
FROM bajosega/api_laravel_sqlsrv:latest


# Instala Docker y Docker Compose para pipelines de Jenkins (DinD)
RUN apt-get update && apt-get install -y \
    docker.io \
    docker-compose \
    && rm -rf /var/lib/apt/lists/*


# Habilita los módulos de Apache necesarios
RUN a2enmod rewrite
