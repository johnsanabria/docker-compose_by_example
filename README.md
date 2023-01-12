# Ejemplos de archivos 'docker-compose.yml'

Docker Compose es una herramienta que permite la ejecución orquestada de contenedores sobre un mismo computador.
En este repositorio encontrará 6 ejemplos de como se puede llevar a cabo la ejecución de contenedores pero a través del comando `docker-compose`.

- [01-interactive](01-interactive/): En este directorio se presenta un `docker-compose.yml` que lanza la ejecución de un contenedor de `alpine` y el cual el usuario lo puede acceder de forma análoga a como si se hubiese ejecutado el contenedor de esta manera: 

```
docker container run --name demo --hostname demo -it alpine
```

- [02-named-vol](02-named-vol/): En este directorio se muestra como definir un volumen externo en un archivo `docker-compose.yml`.  Vale la pena aclarar que cuando el volumen no existe, se crea y si ya existe se reutiliza. La ejecución llevada a cabo por `docker-compose up` es similar a una ejecución como la siguiente pero con el comando `docker`:

  - Se crea un volumen:
  ``` 
  docker volume create mivolumen
  ``` 
  - Se lanza la ejecución del contenedor con el volumen recién creado, asociado a él:
  ``` 
  docker container run -v mivolumen:/workdir -it alpine
  ``` 

  En este mismo directorio, en el archivo `docker-compose-external.yml`, usted encuentra como usar un volumen ya existente con el comando `docker-compose`.

- [03-shared-dir-vol](03-shared-dir-vol/): En este directorio se presenta en el archivo `docker-compose.yml` como compartir un directorio del `host` o anfitrión con el contenedor.

- [04-custom-network](04-custom-network/): Cada vez que `docker-compose` se ejecuta, este se encarga de crear una red para comunicar los contenedores/servicios definidos en el archivo `docker-compose.yml`. Esto permite que los contenedores lanzados durante esta ejecución, no tengan que compartir su medio de comunicación (red de datos) con otras entidades externas a ellos sino que se comuniquen con su propia red privada. En este ejemplo se muestra como darle un nombre a esa red (`mypn`) que será usada por los contenedores para su intercomunicación.

- [05-external-network](05-external-network/): Como se indicó anteriormente, cada vez que se ejecuta el comando `docker-compose up` este crea una red para comunicar a los contenedores/servicios definidos en el `docker-compose.yml`. En este ejemplo, se asume que se tiene ya una red creada con  el  comando `docker network create` y esta será la red que se usará para conectar los contenedores/servicios lanzados bajo la ejecución del comando `docker-compose`. 

- [getting-started](getting-started/): Aquí se encuentran los archivos que se usan en la página web [getting started with docker-compose](https://docs.docker.com/compose/gettingstarted/) y donde se ejemplifica la ejecución de un aplicativo constituido por dos servicios. Esta ejecución permite evidenciar la orquestación de varios servicios para llevar una única tarea.
