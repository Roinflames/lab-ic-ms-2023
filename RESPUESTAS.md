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

Escribe respuestas de la etapa 2 acá

...