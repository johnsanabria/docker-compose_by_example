# Ejecución de un contenedor en modo interactivo

En este directorio encuentra un archivo [`docker-compose.yml`](docker-compose.yml) que al ser usado al momento de ser ejecutado el comando `docker-compose` me genera un contenedor que se puede acceder de manera interactiva.

Ejecutar el comando `docker-compose up` en este directorio y es posible que no ingreses inmediatamente de forma interactiva al contenedor. 
Es posible que quedes con una terminal bloqueada con estas instrucciones:

```
Starting demo ... done
Attaching to demo
```

Una opción es identificar el contenedor que se acaba de generar y posteriormente ejecutar el comando `docker container attach <CONTAINER_ID>`.
