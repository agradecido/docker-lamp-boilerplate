# Docker LAMP Stack Boilerplate

Apache, PHP, xDebug, MySQL (o MariaDB), WP-CLI, fake SMTP server and phpMyAdmin.

## Puesta en marcha rápida

```git clone https://github.com/agradecido/docker-lamp-boilerplate```

```cd docker-lamp-boilerplate```

```docker-compose up -d```

Nota: debemos tener libres los puertos que utilizan los servicios.

## Requerimientos

### Linux

- [Docker para Linux](https://docs.docker.com/engine/install/ubuntu/)
- [Docker Compose para Linux](https://docs.docker.com/compose/install/linux/)

### MacOS

- [Docker para Mac](https://docs.docker.com/engine/install/)
- [Docker Compose para Mac](https://docs.docker.com/desktop/install/mac-install/)

Si se prefiere la aplicación de escritorio existe una versión de Docker Desktop para Mac:

- [Docker Desktop para Mac](https://docs.docker.com/desktop/install/mac-install/)

### Windows

- [Docker Desktop para Windows](https://docs.docker.com/desktop/install/windows-install/)

## Qué incluye este repositorio

Este repositorio incluye la estructura básica de ficheros y directorios para iniciar un proyecto LAMP usando contenedores Docker y docker-compose.

Proporciona los siguientes servicios:

- Apache con https
- PHP (5.4, 5.6, 7.1, 7.2, 7.3, 7.4, 8, 8.1, 8.2)
- Servidor fake SMTP
- xDebug
- WP-CLI
- MySQL (mysql57, mysql8, mariadb103, mariadb104, mariadb105, mariadb106)
- PhpMyAdmin


También se incluye el fichero launch.json para utilizar xDebug en VSCode.

Por defecto se crea una base datos ```docker``` con user ```docker``` y password ```docker```. Estos valores se pueden modificar en el fichero ```.env``` donde también podéis encontrar la password mysql de root.

## Configuración
- Lo primero copia o mueve el fichero ```.env.example``` a ```.env```, puedes hacerlo con este comando (en Linux):
  ```shell
  cp .env.example .env
  ```
- Puedes seleccionar la versión de cada aplicación, el directorio de la aplicación (docroot, por defecto es ```www```), puertos y demás parámetros editando las variables de entorno en el fichero ```.env```
- El fichero ```php.ini``` lo tenemos en ```/config/php```
- En el directorio ```config``` hay más ficheros de configuración por si se quiere modificar otros parámetros. En principio no hace falta tocarlos.

## Modo de uso

### Levantar los contenedores

```docker-compose up -d```

El parámetro -d indica que queremos que se ejecute en segundo plano.

Una vez levantados los conentedores podremos acceder al sitio accediendo a <https://localhost>, PMA lo tenemos disponible en <https://localhost:8080>. Podemos modificar el dominio por uno personalizado del tipo ```proyecto-lamp.local``` editando la variable ```LOCAL_DOMAIN``` en el fichero ```.env```

### Detener los contenedores
```docker-compose down```

### Acceder a la consola de un contenedor

1. Obtener el id del contenedor:

    ```docker ps```

    Con este comando listamos todos los contenedores en ejecución para poder copiar su ID (aparece en la primera columna).

2. Acceder a la consola
    ```docker exec -it ID_CONTAINER /bin/bash```

    El comando ```docker exec``` nos permite **ejecutar cualquier comando** dentro del contenedor seleccionado.

## Contenedores incluidos

1. Apache + PHP + Xdebug
2. WP-CLI
3. MySQL
4. PhpMyAdmin
5. Mailcatcher

## Problemas encontrados

Los ficheros y directorios creados por Docker al levantar los contenedores pertenecen a root. No es un problema para el funcionamiento del entorno, pero da un poco la lata en algunos momentos.

## To-Do

- Translate to English
- Add Nodejs container
