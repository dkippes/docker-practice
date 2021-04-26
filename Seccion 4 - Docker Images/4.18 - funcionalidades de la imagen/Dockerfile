# Primera capa
FROM centos

# Segunda capa, si no sabes como se instalar apache o lo que quieras 
# para ese sistema buscalo en google
RUN yum install httpd -y

# Le agregamos el CMD para que se mantenga en ejecucion
CMD apachectl -DFOREGROUND

# Si la imagen se modifica hay que construirla de nuevo y despues correrla