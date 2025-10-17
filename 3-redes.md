# Redes
Las redes son un componente fundamental que permite la comunicación entre contenedores, así como la comunicación de los contenedores con el mundo exterior. 
![Imagen](redes.PNG)
- Bridge: Esta es la red por defecto en Docker. Permite la comunicación entre contenedores en el mismo host. Cada contenedor conectado a la red bridge tiene una IP propia en la subred de la red bridge.
    -  Brige por default: Cuando se ejecuta un contenedor, Docker crea automáticamente una red de tipo bridge por default. Esta red se utiliza para permitir la comunicación entre contenedores en el mismo host. Cada contenedor conectado a esta red obtiene su propia dirección IP en la subred de la red bridge.
    - Bridge creada por nosotros: Un usuario también puede crear sus propias redes de tipo bridge en Docker. Esto puede ser útil para organizar y segmentar los contenedores de una aplicación de manera más controlada. Al crear una red bridge personalizada, se puede especificar un rango de direcciones IP y otras configuraciones de red específicas. Los contenedores conectados a esta red utilizarán las direcciones IP de la subred definida por el usuario.
- Host: Con esta red, los contenedores comparten la red del host en lugar de tener su propia interfaz de red. Esto puede mejorar el rendimiento de red, pero los contenedores pueden entrar en conflicto con los puertos del host si intentan utilizar los mismos puertos.
- None: Con esta red, se deshabilita la configuración de red. Los contenedores que usan esta red tienen su propia red de loopback y no pueden comunicarse con otros contenedores a menos que se conecten explícitamente a una red.

### Crear una red de tipo bridge

```
docker network create <nombre red> -d bridge: docker run -d -name web-container --network redBdridge nginx
```

### Crear un contenedor vinculado a una red

```
docker run -d --name <nombre contenedor> --network <nombre red> <nombre imagen>: docker run -d --name web-container --network redBdridge nginx
```

### Para saber a qué red está conectado un contenedor

```
docker inspect <nombre contenedor>: docker : 
```
ó
```
docker network inspect <nombre red>: network inspect redBdridge 
```

### Vincular contenedor a una red
```
docker network connect <nombre red> <nombre contenedor>
```

### Para desvincular un contenedor de una red
```
docker network disconnect <nombre red> <nombre contenedor>: docker network disconnect redBdridge web-container
```

### Para listar las redes existentes
```
docker network ls
```

### Crear los contenedores y las redes que se presentan en el esquema. Usar para todos los contenedores la imagen de nginx:alpine

![Imagen](esquema-ejercicio-redes.PNG)
redes creadas
docker network create net-curso01 -d bridge
docker network create net-curso02 -d bridge

contenedores creados
docker run -d --name contenedor1 --network net-curso01 nginx:alpine
docker run -d --name contenedor2 --network net-curso01 nginx:alpine
docker run -d --name contenedor3 --network net-curso01 nginx:alpine
docker run -d --name contenedor4 --network net-curso02 nginx:alpine


# COLOCAR UNA CAPTURA DE LAS REDES EXISTENTES CREADAS
<img width="435" height="218" alt="image" src="https://github.com/user-attachments/assets/0ab46d15-7405-444b-87cf-aaf87879346f" />

# COLOCAR UNA(S) CAPTURAS(S) DE LOS CONTENEDORES CREADOS EN DONDE SE EVIDENCIE A QUÉ RED ESTÁN VINCULADOS
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/abc54d71-acb6-40c1-a4e6-1780eb189c9a" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/77e8c9b3-c760-4cdd-b9d0-bab6182da666" />


### Para eliminar las redes creadas
```
docker network rm <nombre de la red>
```

