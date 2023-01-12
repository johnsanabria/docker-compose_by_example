# Ejecución de un contenedor en modo interactivo

En este directorio encuentra un archivo [`docker-compose.yml`](docker-compose.yml) que al ser usado al momento de ser ejecutado el comando `docker-compose` me genera un contenedor que se puede acceder de manera interactiva.

Ejecutar el comando `docker-compose up` en este directorio, es posible que no ingreses inmediatamente de forma interactiva al contenedor. 
Es posible que quedes con una terminal bloqueada y visualizando algo como esto:

```
Starting demo ... done
Attaching to demo
```

Abre otra terminal y **ubícate en el directorio donde acabas de ejecutar el comando `docker-compose up`**.
Ejecutar el comando `docker-compose ps`.
Este comando debería mostrarte algo como lo siguiente:

```
Name   Command   State   Ports
------------------------------
demo   /bin/sh   Up           
```

Ahora, te puedes conectar al contenedor `demo` usando el comando `docker container attach demo`.

