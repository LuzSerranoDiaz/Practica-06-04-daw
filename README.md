# Practica-06-04-daw

## Dockerfile

```yml
FROM nginx
```
Utiliza la imagen nginx como base
```yml
WORKDIR /usr/share/nginx/html/
```
Indica el directorio donde se van a ejecutar los cambios
```yml
RUN apt update \
    && apt install git -y \
    && rm -rf /var/lib/apt/lists/*
```
Se actualizan los paquetes, se instala git y se eliminan los archivos .txt de apt.
```yml
RUN git clone https://github.com/josejuansanchez/2048 /app \
    && cp -R /app/* /usr/share/nginx/html/ \
    && rm -rf /app
```
Se clona el repositorio de la aplicacion en un directorio temporal y los archivos se trasladan al WORKDIR.
```yml

#No necesario 

EXPOSE 80

# ENTRYPOINT ["entrypoint.sh"]

CMD ["nginx", "-g", "daemon off;"]
```
Se abre el puerto 80 de la maquina y se utiliza `CMD ["nginx", "-g", "daemon off;"]` para lanzar un comando con nginx.
