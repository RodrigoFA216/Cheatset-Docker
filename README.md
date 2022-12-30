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

Add a dns entry

    docker run --add-host HOSTNAME:IP IMAGE

Map a local directory into a container 

    docker run -v HOSTDIR:TARGETDIR IMAGE
    //Example
    docker run -v ~/:/usr/share/ngnix/html/ nginx

Change the entrypoint

    docker run -it --entrypoint EXECUTABLE IMAGE
    //Example
    docker run -it --entrypoint bash nginx

## Manage containers / Administrar contenedores

Show a list of running containers

    docker ps

Show a list of all containers 

    docker ps -a

Delete a container

    docker rm CONTAINER
    //Example
    docker rm web

Delete a running container 

    docker rm -f CONTAINER
    //Example 
    docker rm -f web

Delete stopped containers 

    docker container prune

Stop a running container

    docker stop CONTAINER
    //Example
    docker stop web

Start a stopped container 

    docker start CONTAINER
    //Example
    docker start web

Copy a file from a container to the host

    docker cp CONTAINER:SOURCE TARGET
    //Example
    docker cp web:index.html index.html

Copy a file from the host to a container

    docker cp TARGET CONTAINER:SOURCE
    //Example 
    docker cp index.html web:/index.html

Start a shell inside a running container

    docker exec -it CONTAINER EXECUTABLE
    //Example
    docker exec -it web bash

Rename a container

    docker rename OLD_NAME NEW_NAME
    //Example 
    docker rename 096 web

Create an image out of container

    docker commit CONTAINER
    //Example
    docker commit web

## Manage Images

Download an image

    docker pull IMAGE[:TAG]
    //Example
    docker pull nginx

Upload an image to a repository

    docker push IMAGE
    //Example
    docker push myimage:1.0

Delete an image

    docker rml IMAGE

Show a list of images

    docker images

Delete dangling images

    docker image prune -A

