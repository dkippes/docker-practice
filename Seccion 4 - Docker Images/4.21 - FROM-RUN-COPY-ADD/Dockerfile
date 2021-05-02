# Primera capa
FROM centos

# Segunda capa, si no sabes como se instalar apache o lo que quieras 
# para ese sistema buscalo en google
RUN yum install httpd -y

# ADD tiene la misma funcionalidad, pero puede traer datos de una URL
# el /var/www/html es donde se encuentra apache
COPY src /var/www/html

# Le agregamos el CMD para que se mantenga en ejecucion
CMD apachectl -DFOREGROUND

# Si la imagen se modifica hay que construirla de nuevo y despues correrla
# docker build -t apache-centos .
# docker run -p -d 80:80 apache-centos