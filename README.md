# Cheatset for docker CLI / Lista de códigos para la terminal de docker

## Run  a new Container / Ejecutar un nuevo contenedor

Start a new Container from an image / Ejecutar un contenedor desde una imagen

    docker run IMAGE
    //Example
    docker run nginx

Assign it a name / asignarle un nombre

    docker run --name CONTAINER IMAGE
    //Example
    docker run --name web nginx

Map a port / Mapear un puerto

    docker run -p HOTSPOT:CONTAINERPORT IMAGE
    //Example
    docker run -p 8080:80 nginx

Map all ports / Mapear todos los puertos

    docker run -P IMAGE
    //Example
    docker run -P nginx

Start a container in background / iniciar un contenedor en segundo plano

    docker run -d IMAGE 
    //Example
    docker run -d nginx

Assign it a hostname / Asignar al contenedor un hostname

    docker run --hostname HOSTNAME IMAGE
    //Example
    docker run --hostname srv nginx

Add a dns entry / Añadir una entrada de dns

    docker run --add-host HOSTNAME:IP IMAGE

Map a local directory into a container / mapear un directorio local en un contenedor

    docker run -v HOSTDIR:TARGETDIR IMAGE
    //Example
    docker run -v ~/:/usr/share/ngnix/html/ nginx

Change the entrypoint / Cambiar el entrypoint

    docker run -it --entrypoint EXECUTABLE IMAGE
    //Example
    docker run -it --entrypoint bash nginx

## Manage containers / Administrar contenedores

Show a list of running containers / Mostrar una lista de los contenedores ejecutados

    docker ps

Show a list of all containers / Mostrar una lista de todos los contenedores

    docker ps -a

Delete a container / Eliminar un contenedor

    docker rm CONTAINER
    //Example
    docker rm web

Delete a running container / Eliminar un contenedor que se está ejecutando

    docker rm -f CONTAINER
    //Example 
    docker rm -f web

Delete stopped containers / Eliminar un contenedor detenido

    docker container prune

Stop a running container / Detener un contenedor que se está ejecutando

    docker stop CONTAINER
    //Example
    docker stop web

Start a stopped container / Ejecutar un contenedor detenido 

    docker start CONTAINER
    //Example
    docker start web

Copy a file from a container to the host / Copiar un archivo de un contenedor al host

    docker cp CONTAINER:SOURCE TARGET
    //Example
    docker cp web:index.html index.html

Copy a file from the host to a container / copiar un archivo del host al contenedor

    docker cp TARGET CONTAINER:SOURCE
    //Example 
    docker cp index.html web:/index.html

Start a shell inside a running container / Ejecutar una terminal en el contenedor que se está ejecutando

    docker exec -it CONTAINER EXECUTABLE
    //Example
    docker exec -it web bash

Rename a container / Renombrar o retagear un contenedor

    docker rename OLD_NAME NEW_NAME
    //Example 
    docker rename 096 web

Create an image out of container / Crear una imagen de un contenedor

    docker commit CONTAINER
    //Example
    docker commit web

## Manage Images

Download an image / Descargar una imagen de un contenedor

    docker pull IMAGE[:TAG]
    //Example
    docker pull nginx

Upload an image to a repository / Subir una imagen a un repositorio

    docker push IMAGE
    //Example
    docker push myimage:1.0

Delete an image / Borrar una imagen de un repositorio

    docker rml IMAGE

Show a list of images / Mostrar una lista de imagenes

    docker images

Delete dangling images / Borrar imágenes que se quedaron colgadas o buggeadas

    docker image prune -A

Delete all unused images / Borrar todas las imágenes que no se usan

    docker image prune -a

Build an image from docker file / Construir una imagen desde un archivo de docker 

    docker build DIRECTORY
    //Example
    docker build .

Tag an image / Etiquetar una imagen

    docker tag IMAGE NEWIMAGE
    //Examples
    docker tag ubuntu ubuntu:18.04

Build an tag an image from a dockerfile / Construir una imagen desde un archivo de docker

    docker build -t IMAGE DIRECTORY
    //Example
    docker build -t myimage .

Save an image to a .tar file / Guardar una imagen como un archivo .tar

    docker save IMAGE > FILE
    //Example
    docker save ngnix > nginx.tar

Load an image from a .tar file / Leer una imagen desde un archivo .tar

    docker load -i TARFILE
    //Example
    docker load -i nginx.tar

## Info and Stats

Show the logs of a container / Mostrar los eventod de un contenedor

    docker logs CONTAINER
    //Example
    doker logs web

Show stats of running containers / Mostrar las estadísticas de un contenedor 

    docker stats

Show process of container / Mostrar los procesos de un contenedor

    docker top CONTAINER
    //Example
    docker top web

Show installed docker version / Mostrar la versión de Docker instalada

    docker version

Get detailed info about an object / Obtener información detallada de un objeto

    docker inspect NAME
    //Ejemplo
    docker inspect nginx

Show all modified files in container / Mostrar todos los archivos modificados en un contenedor

    docker diff CONTAINER
    //Example
    docker diff web

Show mapped ports of a container / Mostrar los puertod mapeados de un contenedor

    docker port CONTAINER
    //Ejemplo
    docker port web

