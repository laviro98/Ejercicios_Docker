# PRÁCTICA 3

# Ejercicio 1

**Descarga la imagen de Ubuntu**

```sudo docker pull ubuntu```

![image](https://user-images.githubusercontent.com/114391559/222125563-259a2c8b-bd93-4d47-bcf5-1eb7282a06d0.png)

# Ejercicio 2

**Descarga la imagen de hello-world**

```sudo docker pull hello-world```

![image](https://user-images.githubusercontent.com/114391559/222125629-4a37174b-1b65-41e6-928d-b4098dc0e770.png)

# Ejercicio 3

**Descarga la imagen de Nginx**

```sudo docker pull nginx```

![image](https://user-images.githubusercontent.com/114391559/222125709-47119cf8-757e-4ce8-8953-b6a953b6c27f.png)

# Ejercicio 4

**Muestra un listado de todas las imágenes**

```sudo docker images```

![image](https://user-images.githubusercontent.com/114391559/222125756-eae19a2f-1081-47e3-b52b-e0d4592deb4d.png)

# Ejercicio 5

**Ejecuta un contenedor hello-world y dale nombre "myhello1"**

```sudo docker run --name myhello1 hello-world```

# Ejercicio 6

**Ejecuta un contenedor hello-world y dale nombre "myhello2"**

```sudo docker run --name myhello2 hello-world```

# Ejercicio 7

**Ejecuta un contenedor hello-world y dale nombre "myhello3"**

```Sudo docker run --name myhello3 hello-world```

![image](https://user-images.githubusercontent.com/114391559/222126075-6853b432-af2a-4657-889f-4cb53600bdb3.png)


# Ejercicio 8

**Muestra los contenedores que se están ejecutando**

```sudo docker ps```

![image](https://user-images.githubusercontent.com/114391559/222126102-a3ba2738-f9b7-43d6-9ef1-1db7ebe15389.png)


**El ejercicio 9 y el 10 --> Al ser un script paran solos**


# Ejercicio 11

**Borra el contenedor "myhello1"**

```sudo docker rm myhello1```

```sudo docker ps -a```

![image](https://user-images.githubusercontent.com/114391559/222419236-3450beb1-fb46-4341-91d0-30c9c5e6817a.png)

# Ejercicio 12

**Muestra los contenedores que se están ejecutando**

```sudo docker ps```

![image](https://user-images.githubusercontent.com/114391559/222419353-40c162af-3bf3-47b6-91ff-d52f26c5204c.png)

# Ejercicio 13

**Borra todos los contenedores**

```sudo docker rm myhello2```
```sudo docker rm myhello3```

![image](https://user-images.githubusercontent.com/114391559/222419486-7206c432-34d0-478e-9d31-765165ed9fe3.png)

```sudo docker rm mi_contenedor_ubuntu```

![image](https://user-images.githubusercontent.com/114391559/222419610-0497f5ae-4c0a-4112-9490-cc97aad9e4a8.png)

```sudo docker ps -a```

![image](https://user-images.githubusercontent.com/114391559/222419631-ff6bd6d7-836b-4eab-b886-e7933c267fbf.png)
