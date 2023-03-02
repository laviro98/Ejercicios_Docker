# PRÁCTICA 5 -  Creando escenarios multicontenedor con docker-compose

# Ejercicio 1

**Ejemplo 1: Despliegue de la aplicación Guestbook**

_Enlace: https://github.com/josedom24/curso_docker_ies/blob/main/modulo4/guestbook.md_

```sudo nano docker-compose.yml```

```
version: '3.1'
services:
  app:
    container_name: guestbook
    image: iesgn/guestbook
    restart: always
    ports:
      - 8081:5000
  db:
    container_name: redis
    image: redis
    restart: always
```

![image](https://user-images.githubusercontent.com/114391559/222422872-60ed7dde-5801-40c8-bb76-abbc4c017a74.png)

```sudo docker compose up -d```

![image](https://user-images.githubusercontent.com/114391559/222422944-01e924f3-5ada-4496-a7c0-a608902b5688.png)

```sudo docker compose ps```

![image](https://user-images.githubusercontent.com/114391559/222422983-e8dd7502-c41f-458a-8e46-6a672f4a923d.png)

```sudo docker compose stop```

```sudo docker compose down```

![image](https://user-images.githubusercontent.com/114391559/222423012-ccd023cf-cc53-4bb6-a608-40ff00ebf8fc.png)

# Ejercicio 2

**Ejemplo 2: Despliegue de la aplicación Temperaturas**

_Enlace: https://github.com/josedom24/curso_docker_ies/blob/main/modulo4/temperaturas.md-

```sudo nano docker-compose.yml```

```
version: '3.1'
services:
  frontend:
    container_name: temperaturas-frontend
    image: iesgn/temperaturas_frontend
    restart: always
    ports:
      - 8081:3000
    depends_on:
      - backend
  backend:
    container_name: temperaturas-backend
    image: iesgn/temperaturas_backend
    restart: always
```

![image](https://user-images.githubusercontent.com/114391559/222423274-e62838f3-6530-4459-8cf9-02d1ad6c7d11.png)

```sudo docker compose up -d```

```sudo docker compose ps```

![image](https://user-images.githubusercontent.com/114391559/222423323-4b8b4bc6-0992-4cc1-801f-0adc16c736a1.png)

# Ejercicio 3

**Ejemplo 3: Despliegue de Wordpress + mariadb**

_Enlace: https://github.com/josedom24/curso_docker_ies/blob/main/modulo4/wordpress.md-

```sudo nano docker-compose.yml```

```
version: '3.1'
services:
  wordpress:
    container_name: servidor_wp
    image: wordpress
    restart: always
    environment:
      WORDPRESS_DB_HOST: db
      WORDPRESS_DB_USER: user_wp
      WORDPRESS_DB_PASSWORD: asdasd
      WORDPRESS_DB_NAME: bd_wp
    ports:
      - 8081:80
    volumes:
      - wordpress_data:/var/www/html/wp-content
  db:
    container_name: servidor_mysql
    image: mariadb
    restart: always
    environment:
      MYSQL_DATABASE: bd_wp
      MYSQL_USER: user_wp
      MYSQL_PASSWORD: asdasd
      MYSQL_ROOT_PASSWORD: asdasd
    volumes:
      - mariadb_data:/var/lib/mysql
volumes:
    wordpress_data:
    mariadb_data:
```

![image](https://user-images.githubusercontent.com/114391559/222423567-c32b7ed4-5467-4512-be18-1f3679c38df3.png)


```sudo docker compose up -d```

```sudo docker compose ps```

```sudo docker compose stop```

```sudo docker compose rm```

```sudo docker compose down -v```

![image](https://user-images.githubusercontent.com/114391559/222423625-01a35e66-6131-4086-9423-0c5d1600d00e.png)
