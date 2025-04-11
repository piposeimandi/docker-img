# Repositorio de Dockerfiles y Scripts de Construcción

Este repositorio contiene Dockerfiles y scripts de shell (SH) para construir y subir imágenes de Docker a Docker Hub.

## Propósito

El objetivo de este repositorio es proporcionar una colección de Dockerfiles y scripts que simplifiquen el proceso de creación y publicación de imágenes de Docker. Esto permite una gestión eficiente de las imágenes utilizadas en nuestros proyectos.

## Contenido

El repositorio está organizado en los siguientes directorios:

* **`nombre_directorio_1/`**: Contiene el Dockerfile y scripts relacionados para la imagen `nombre_imagen_1`.
* **`nombre_directorio_2/`**: Contiene el Dockerfile y scripts relacionados para la imagen `nombre_imagen_2`.
* **`nombre_directorio_3/`**: Contiene el Dockerfile y scripts relacionados para la imagen `nombre_imagen_3`.
* **`scripts/`**: Contiene scripts de shell reutilizables para construir y subir imágenes.

## Estructura de Directorios

Cada directorio de imagen contiene los siguientes archivos:

* **`Dockerfile`**: El archivo Dockerfile para construir la imagen.
* **`build.sh`**: Un script de shell para construir la imagen.
* **`push.sh`**: Un script de shell para subir la imagen a Docker Hub.
* **`README.md`**: (Opcional) Un archivo README.md específico para la imagen.

## Scripts de Shell

Los scripts de shell en el directorio `scripts/` proporcionan funciones reutilizables para construir y subir imágenes. Estos scripts pueden ser utilizados por los scripts `build.sh` y `push.sh` en los directorios de imágenes.

## Cómo Utilizar

1.  Clona este repositorio:

    ```bash
    git clone [https://github.com/tu_nombre_de_usuario/tu_repositorio.git](https://github.com/tu_nombre_de_usuario/tu_repositorio.git)
    ```

2.  Navega al directorio de la imagen que deseas construir:

    ```bash
    cd nombre_directorio_1
    ```

3.  Ejecuta el script `build.sh` para construir la imagen:

    ```bash
    ./build.sh
    ```

4.  Ejecuta el script `push.sh` para subir la imagen a Docker Hub:

    ```bash
    ./push.sh
    ```

## Contribución

Las contribuciones son bienvenidas. Si deseas agregar una nueva imagen o script, sigue estos pasos:

1.  Crea un nuevo directorio para tu imagen.
2.  Agrega el `Dockerfile` y los scripts necesarios.
3.  Actualiza este `README.md` con la información de tu nueva imagen.
4.  Envía un pull request.

## Licencia

Este repositorio se distribuye bajo la licencia [MIT](LICENSE).

## Contacto

Si tienes alguna pregunta o sugerencia, no dudes en contactarme en [tu_correo@ejemplo.com](mailto:tu_correo@ejemplo.com).
