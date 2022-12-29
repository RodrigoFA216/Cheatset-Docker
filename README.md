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

