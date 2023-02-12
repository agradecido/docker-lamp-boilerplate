# Docker LAMP Stack Scaffold

Estructura de ficheros y directorios para iniciar un proyecto LAMP usando contenedores Docker.

Incluye:
- Apache con https
- PHP (5.4, 5.6, 7.1, 7.2, 7.3, 7.4, 8, 8.1)
- xDebug
- WP-CLI
- MySQL (mysql57, mysql8, mariadb103, mariadb104, mariadb105, mariadb106)
- PhpMyAdmin
- Servidor fake SMTP

También se incluye el fichero launch.json para utilizar xDebug en VSCode.

## Requerimientos
### Linux
- Docker https://docs.docker.com/engine/install/ubuntu/
- Docker Compose https://docs.docker.com/compose/install/linux/

### MacOS
- Docker https://docs.docker.com/engine/install/
- Docker Compose https://docs.docker.com/desktop/install/mac-install/

Si se prefiere la aplicación de escritorio existe una versión de Docker Desktop para Mac
- https://docs.docker.com/desktop/install/mac-install/
### Windows
- Docker Desktop https://docs.docker.com/desktop/install/windows-install/

## Configuración

- Puedes seleccionar la versión de cada aplicación, el directorio de la aplicación (docroot), puertos y demás parámetros editando el fichero .env
- El fichero php.ini lo tenemos en /config/php
- En el directorio config hay más ficheros de configuración por si se quiere modificar otros parámetros. En principio no hace falta tocarlos.
- El directorio por defecto para la aplicación es www

## Contenedores

1. Apache + PHP + Xdebug
2. WP-CLI
3. MySQL
4. PhpMyAdmin
5. Mailcatcher

## Instrucciones
1. TODO Levantar los contenedores
2. TODO Acceder a la consola shell de un contenedor
