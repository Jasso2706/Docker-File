# Docker-File
Hola para utilizar el docker file por favor seguir los siguientes comandos:
mkadir prueba
cd prueba
vi prueba (una vez en VI pegar lo siguiente)
ROM httpd:2.4
COPY index.html /usr/local/apache2/htdocs/index.html
RUN  mkdir -p /run/apache2/ && \
     chown www-data:www-data /run/apache2/ && \
     chmod 777 /run/apache2/
RUN apt-get update
RUN apt-get install ssh -y
EXPOSE 80
docker build prueba
docker images #verificar que este imagen
docker run -dit --name "nombre del contenedor" -p 8080:80 prueba
### ir a http://localhost:80 para comprobar sitio
