# PRÁCTICA 2

# Ejercicio 1

**Edita el fichero Dockerfile**

```git clone https://github.com/docker/getting-started.git```

![image](https://user-images.githubusercontent.com/114391559/222123615-31bcbb20-05f8-44fa-86df-828ff9e5427e.png)

Editamos el archivo Dockerfile. Le añadimos lo siguiente:

```
# syntax=docker/dockerfile:1
   
FROM node:18-alpine
WORKDIR /app
COPY . .
RUN yarn install --production
CMD ["node", "src/index.js"]
EXPOSE 3000

```

![image](https://user-images.githubusercontent.com/114391559/222123931-995c2c20-9020-4068-ab0e-9ab5b826089a.png)

# Ejercicio 2

**Construye el contenedor**

```sudo docker build -t getting-started ../```

![image](https://user-images.githubusercontent.com/114391559/222124047-44fd79e7-90ab-4cb5-bd16-47de5263013a.png)

# Ejercicio 3

**Ejecútalo**

```sudo docker run -d -p 3000:3000 getting-started```

![image](https://user-images.githubusercontent.com/114391559/222124253-86959ba8-fcd2-48ef-80dc-3ceba353d72a.png)

![image](https://user-images.githubusercontent.com/114391559/222124279-c952bbb8-971b-4b50-84fd-d2a3da2bbe13.png)


**El ejercicio 4 está hecho en [Instalación de Docker](https://github.com/laviro98/Ejercicios_Docker/blob/main/instalacion_docker.md)
