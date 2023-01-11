# Ejemplos de archivos 'docker-compose.yml'

Docker Compose es una herramienta que permite la ejecución orquestada de contenedores sobre un mismo computador.
En este repositorio encontrará 6 ejemplos de como se puede llevar a cabo la ejecución de contenedores pero a través del comando `docker-compose`.

- <01-interactive>: En este directorio se presenta un `docker-compose.yml` que lanza la ejecución de un contenedor de `alpine` y el cual el usuario lo puede acceder de forma análoga a como si se hubiese ejecutado el contenedor de esta manera: 

```
docker container run --name demo --hostname demo -it alpine
```

**IMPORTANTE**
En caso de tener problemas para tener la conexión,  en otra terminal, ejecute el comando `docker container ls`, identifique el contenedor que recién se creó a través del comando `docker-compose` y haga un `attach` ha dicho contenedor usando el comando `docker container attach <container_id>`.

- <02-named-vol>: En este directorio se muestra como definir un volumen en un archivo `docker-compose.yml`.  Cuando el volumen no existe, se crea y si ya existe se reutiliza. Esta ejecución es similar a algo como lo siguiente:

  - Se crea un volumen:
  ``` 
  docker volume create mivolumen
  ``` 
  - Se lanza la ejecución del contenedor con el volumen recién creado, asociado a él:
  ``` 
  docker container run -v mivolumen:/workdir -it alpine
  ``` 

  En este mismo directorio, en el archivo `docker-compose-external.yml`, usted encuentra como usar un volumen ya existente con el comando `docker-compose`.

- <03-shared-dir-vol>: En este directorio se presenta en el archivo `docker-compose.yml` como asociar un directorio del `host` o anfitrión en el contenedor.

- <04-custom-network>: Cada vez que `docker-compose` se ejecuta, este se encarga de crear una red para comunicar los contenedores definidos en el archivo `docker-compose.yml`. Esto permite que los contenedores lanzados durante esta ejecución, no tengan que tener un contacto con otros recursos externos a ellos sino que se comuniquen con su propia red privada.

- <05-external-network>: En caso de tener una red ya creada con `docker network create`, esta red se puede usar para conectar los contenedores lanzados bajo la ejecución del comando `docker-compose`. Aquí se muestra un ejemplo.

- <getting-started>: Aquí se encuentran los archivos que se usan en la página web [getting started with docker-compose](https://docs.docker.com/compose/gettingstarted/) y donde se ejemplifica la ejecución de un aplicativo constituido por tres servicios. Esta ejecución permite evidenciar la orquestación de varios servicios para llevar una única tarea.
