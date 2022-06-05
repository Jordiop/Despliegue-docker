# Despliegue docker

*Autores: Jordi Osarenkhoe, Andreu Salleras, Biel Tomàs*

Como se nos ha solitado, tenemos que realizar un despliegue de nuestro proyecto utilizando Docker. Siguiendo los tutoriales y echándole un poco de imaginación, se puede conseguir.

## 1. Creación del Dockerfile

`nano Dockerfile`

```
FROM tomcat:latest
LABEL maintainer = "Jordi, Andreu, Biel"
ADD . /usr/local/tomcat/webapps
EXPOSE 8080
CMD ["catalina.sh", "run"]
```

Guardamos y salimos. El archivo debe ser sin extensión.

## 2. Montaje de la imagen

En este paso, construiremos la imagen teniendo en cuenta nuestro .war, que será la exportación de nuestro proyecto.

![imagen](https://user-images.githubusercontent.com/95173613/172065141-e7eef05f-9794-4ed9-8ac8-dcbe1728a89b.png)

## 3. Despliegue

En teoría, tendríamos que poder depslegar nuestro contenedor docker con nuestro proyecto. Nos dirigimos a localhost:8008/GAI (gai es realmente el nombre de nuestro contenedor).

![imagen](https://user-images.githubusercontent.com/95173613/172066006-b5f4a608-711f-4755-b318-f1484c48b929.png)

## 4. Docker-compose

Ahora, tenemos que realizar un archivo .yml para hacer el docker-compose. 

El código de dentro del archivo será:

![imagen](https://user-images.githubusercontent.com/95173613/172066711-37e26cb6-24e6-4bf9-857b-48acd8b45a7d.png)

Y ejecutaremos el comando

`docker-compose up -d`

## 5. Tendremos las 3 imágenes corriendo

