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

En teoría, tendríamos que poder depslegar nuestro contenedor docker con nuestro proyecto. Lo iniciamos pero por algún motivo desconocido, este no es capaz de reflejar nuestro frontend, dando como resultado esto:

![imagen](https://user-images.githubusercontent.com/95173613/172065619-059a63a6-69fd-4280-8f3b-e874d116989b.png)

