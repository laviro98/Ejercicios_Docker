# PRÁCTICA 4 - Almacenamiento y redes en Docker

# Ejercicio 1

**Ejemplo 1: Despliegue de la aplicación Guestbook**

_Enlace: https://github.com/josedom24/curso_docker_ies/blob/main/modulo3/guestbook.md_

```sudo docker network create red_guestbook```

![image](https://user-images.githubusercontent.com/114391559/222420509-b9b609d2-18a8-4496-9d50-d8cf891f96ef.png)

```sudo docker run -d --name redis --network red_guestbook -v /opt/redis:/data redis redis-server --appendonly yes```

![image](https://user-images.githubusercontent.com/114391559/222420567-0fdb1f03-efa2-48db-aee6-22f9a58b27fc.png)

```sudo docker run -d -p 8080:5000 --name guestbook --network red_guestbook iesgn/guestbook```

![image](https://user-images.githubusercontent.com/114391559/222420625-80ad0e1a-71ef-4950-ae54-e7b4a0ef830e.png)

*En el documento de github le da el puerto 80, pero yo lo tengo en uso, asi que le doy el 8080.

![image](https://user-images.githubusercontent.com/114391559/222420669-28b61f0c-2f8f-4ac0-96b6-edc907d92bb0.png)

# Ejercicio 2

**Ejemplo 2: Despliegue de la aplicación Temperaturas**

_Enlace: https://github.com/josedom24/curso_docker_ies/blob/main/modulo3/temperaturas.md_

Antes de empezar paro los contenedores:

![image](https://user-images.githubusercontent.com/114391559/222420928-ba5f1301-63ad-4717-b197-043b64127601.png)

```sudo docker network create red_temperaturas```

```sudo docker run -d --name temperaturas-backend --network red_temperaturas iesgn/temperaturas_backend```

![image](https://user-images.githubusercontent.com/114391559/222421039-a49ff38c-cea9-4ce7-910d-1df6527e2961.png)

```sudo docker run -d -p 8080:3000 --name temperaturas-frontend --network red_temperaturas iesgn/temperaturas_frontend```

![image](https://user-images.githubusercontent.com/114391559/222421064-b424805b-8b15-4a31-8f97-2c23a5522e63.png)

![image](https://user-images.githubusercontent.com/114391559/222421098-20d66133-04ab-41f3-8dae-515b9fa82de3.png)

# Ejercicio 3

**Ejemplo 3: Despliegue de Wordpress + mariadb**

_Enlace: https://github.com/josedom24/curso_docker_ies/blob/main/modulo3/wordpress.md_

```sudo docker network create red_wp```

```
sudo docker run -d --name servidor_mysql \
                --network red_wp \
                -v /opt/mysql_wp:/var/lib/mysql \
                -e MYSQL_DATABASE=bd_wp \
                -e MYSQL_USER=user_wp \
                -e MYSQL_PASSWORD=asdasd \
                -e MYSQL_ROOT_PASSWORD=asdasd \
                mariadb
 ```

![image](https://user-images.githubusercontent.com/114391559/222421329-c06daa34-8125-464c-b337-7ba96193fdc6.png)

```
sudo docker run -d --name servidor_wp \
                --network red_wp \
                -v /opt/wordpress:/var/www/html/wp-content \
                -e WORDPRESS_DB_HOST=servidor_mysql \
                -e WORDPRESS_DB_USER=user_wp \
                -e WORDPRESS_DB_PASSWORD=asdasd \
                -e WORDPRESS_DB_NAME=bd_wp \
                -p 8080:80 \
                wordpress
```

![image](https://user-images.githubusercontent.com/114391559/222421411-2673552c-2a3e-49a0-85c5-aab58a83f912.png)

![image](https://user-images.githubusercontent.com/114391559/222421441-4549a3ec-5818-4c15-82c8-71d283bde735.png)
