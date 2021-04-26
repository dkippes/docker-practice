## Imagenes oficiales en https://hub.docker.com/

#### Bajar imagenes oficiales
- Para bajar el lastest directo sin tag -> `docker pull mongo`
- Para bajar con un tag(version) -> `docker pull mongo:3.6.5-jessie`
- Para ver las diferentes versiones -> `docker images | grep mongo`
- Si no lo actualizaste hace tiempo y queres bajar el nuevo lastest puede pasar que ya este creado y docker le ponga <'none'>

#### Crear imagenes propias
- FROM -> `FROM ubuntu:16.04` Sistema, primera capa
- RUN -> `RUN apt-get install -y apache` Buscar como corre "apache" en el sistema que pusimos en FROM
- Crear la imagen: `docker build --tag apache-ubuntu .`
- Se puede crear con un tag `docker build --tag apache-ubuntu:primeta .` es lo mismo que `docker build -t apache-centos:apache-cmd .`

#### Borrar contenedores / Ver contenedores
- Para ver que contenedores estan corriendo: `docker ps` para ver los contenedores muertos `docker ps -a`
- `cat Dockerfile` Con cat se puede ver que contiene un archivo

#### Para correr una imagen 
- `docker run -d apache-centos` -d le dije para irse al fondo
- Si la imagen se muere al correrla puede que le falte un CMD para funcionar
- La imagen se mantendra UP si esta corre en foreground pero sino saldra EXIT y que murio
- Hay que especificar el tag de la imagen cambiada

#### Para ver la historia de una imagen
- `docker history -H apache-centos:apache-cmd` Se puede ver la historia de una imagen
- `docker history -H apache-centos:apache-cmd --no-trunc` Ver una historia completa

#### Eliminar un contenedor corriendo
- `docker rm -fv apache` rm permite remover un contenedor

#### Correr una imagen en un puerto para visualizarlo
- `docker run -d --name apache -p 80:80 apache-centos:apache-cmd` especificamos -p para decirle que use un puerto y 80 sera el puerto "desdeNuestraMaquina:AlContenedor"
- Si vamos a "localhost:80" veremos el contenedor con la imagen corriendo, en este caso apache