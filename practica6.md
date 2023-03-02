# PRÁCTICA 6

# Ejercicio 1

**Ejemplo 1: Construcción de imágenes con una página estática - Desde una imagen base**

*Enlace: https://github.com/josedom24/curso_docker_ies/blob/main/modulo5/ejemplo1.md*

![image](https://user-images.githubusercontent.com/114391559/222523873-1f6c0704-e38e-4b71-9949-b57d5ee9d10d.png)

```sudo nano Dockerfile```

```
FROM debian
RUN apt-get update && apt-get install -y apache2 && apt-get clean && rm -rf /var/lib/apt/lists/*
ADD public_html /var/www/html/
EXPOSE 80
CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]
```

![image](https://user-images.githubusercontent.com/114391559/222524322-6887c8de-0ab4-4f7a-bfd6-6234f69632a9.png)

```sudo docker build -t josedom24/ejemplo1:v1 .```

![image](https://user-images.githubusercontent.com/114391559/222524628-4573304b-d2c4-40c0-ae52-b82623a3b445.png)

![image](https://user-images.githubusercontent.com/114391559/222524788-6aab896d-7f24-41dd-9d37-544d7ed4aa36.png)

# Ejercicio 2

**Ejemplo 2: Construcción de imágenes con una una aplicación PHP - Desde una imagen base**

*Enlace: https://github.com/josedom24/curso_docker_ies/blob/main/modulo5/ejemplo2.md*

```
FROM debian
RUN apt-get update && apt-get install -y apache2 libapache2-mod-php7.4 php7.4 && apt-get clean && rm -rf /var/lib/apt/lists/*
ADD app /var/www/html/
RUN rm /var/www/html/index.html
EXPOSE 80
CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]
```

![image](https://user-images.githubusercontent.com/114391559/222526709-a2d31ef6-3aa0-4f79-ab51-3b428208497d.png)

```
docker build -t josedom24/ejemplo2:v1 .
```

![image](https://user-images.githubusercontent.com/114391559/222527285-ababb931-d000-4fd9-a508-287f0e2f0c70.png)

![image](https://user-images.githubusercontent.com/114391559/222527755-681d00b6-41c7-4f56-b7eb-7ae881241cb1.png)
