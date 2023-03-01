Antes de realizar cualquier instalación, debemos hacer un update:

```sudo apt update```

```sudo apt install apt-transport-https ca-certificates curl software-properties-common```

```curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -```

```sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"```

```sudo apt update```

```apt-cache policy docker-ce```

![image](https://user-images.githubusercontent.com/114391559/222104217-ee171b04-b6eb-41e1-8118-c58e18e42583.png)

```sudo apt install docker-ce```

```sudo systemctl status docker```

![image](https://user-images.githubusercontent.com/114391559/222104200-58e05d5f-7eb0-4f86-81b1-024596a4707c.png)


**Debemos tener nuestro Docker con Dockerhub:**




