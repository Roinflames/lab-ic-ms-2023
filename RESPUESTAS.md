# Respuestas

Indica tu nombre a continuación: 

Por cada etapa agrega una sección abajo y escribe las respuestas a las preguntas de cada etapa.

## ETAPA 1

Revisa el contenido del diretorio sql_migrations.

¿Cuál es la diferencia entre los archivos con el verbo `Create` con los archivos con el verbo `Add`?
Los archivos CREATE sirven para crear tablas.
Los archivos ADD sirven para insertar datos o filas o registros.

Revisa el contenido del archivo `docker-compose.yml`. 

¿Cómo se llama el servicio que se declara en el archivo `docker-compose.yml`?
flyway.

¿Cuál es el comando que se ejecuta en el servicio declarado?
command: -locations=filesystem:/flyway/sql -connectRetries=60 migrate

## ETAPA 2

¿Qué pasa si cambias el nombre del servicio de `postgres` a `db`? ¿Qué otros cambios tendrías que hacer?
Los contenedores se quedan en estado RUNNING (postgres, flyway).
No corren las migraciones.
Por consola me llega:
migration_flyway     | WARNING: Connection error: The connection attempt failed. (Caused by postgres) Retrying in 1 sec...

## ETAPA 3

Revisa el archivo `movies-api/Dockerfile`.

¿Qué te llama la atención?
Todo, no estoy familiarizado con GO. Veo que corre sobre Debian 11

Revisa el archivo `docker-compose.yml`.

¿Cómo se relacionan el archivo `docker-compose.yml` y el archivo `movies-api/Dockerfile`?
Creo que el build context toma la ruta del Dockerfile para la construcción del contenedor de este servicio.

¿Qué crees que hace el atributo `context` debajo de `build` (está en la linea 6 del archivo `docker-compose.yml`)?
Lo mismo que respondí en la pregunta anterior.

## ETAPA 4

Compara los archivos `Dockerfile` de `movies-api` y `movies-front`. 

Compara el atributo `build` del servicio `movies-api` con el de `movies-front`. 
¿Cuál es la diferencia? 
En los Dockerfiles:
 - `movies-api` se construye sobre una imagen golang:1.19 y una imagen gcr.io/distroless/base-debian11.
 - `movies-api` tiene 2 stages.
 
 - `movies-front` se construye sobre una imagen node:20.5-alpine3.17
 - `movies-front` tiene 1 stage.

En el atributo `build`:
 - `movies-api` tiene un atributo context.
 - `movies-front` NO tiene un atributo context.

¿Qué pasa si los dejas iguales?
