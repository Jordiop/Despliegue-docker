# Despliegue docker

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

