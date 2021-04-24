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
- Se puede crear con un tag `docker build --tag apache-ubuntu:primeta .`