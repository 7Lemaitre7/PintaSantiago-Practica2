# Redes

Las redes son un componente fundamental que permite la comunicación entre contenedores, así como la comunicación de los contenedores con el mundo exterior.


![Imagen](redes.PNG)

* Bridge: Esta es la red por defecto en Docker. Permite la comunicación entre contenedores en el mismo host. Cada contenedor conectado a la red bridge tiene una IP propia en la subred de la red bridge.

  * Brige por default: Cuando se ejecuta un contenedor, Docker crea automáticamente una red de tipo bridge por default. Esta red se utiliza para permitir la comunicación entre contenedores en el mismo host. Cada contenedor conectado a esta red obtiene su propia dirección IP en la subred de la red bridge.
  * Bridge creada por nosotros: Un usuario también puede crear sus propias redes de tipo bridge en Docker. Esto puede ser útil para organizar y segmentar los contenedores de una aplicación de manera más controlada. Al crear una red bridge personalizada, se puede especificar un rango de direcciones IP y otras configuraciones de red específicas. Los contenedores conectados a esta red utilizarán las direcciones IP de la subred definida por el usuario.
* Host: Con esta red, los contenedores comparten la red del host en lugar de tener su propia interfaz de red. Esto puede mejorar el rendimiento de red, pero los contenedores pueden entrar en conflicto con los puertos del host si intentan utilizar los mismos puertos.
* None: Con esta red, se deshabilita la configuración de red. Los contenedores que usan esta red tienen su propia red de loopback y no pueden comunicarse con otros contenedores a menos que se conecten explícitamente a una red.

### Crear una red de tipo bridge

```
docker network create <nombre red> -d bridge
```

```
docker network create primer-red -d bridge
```

```
docker network create net-curso01 -d bridge
docker network create net-curso02 -d bridge
```

### Crear un contenedor vinculado a una red

<img width="596" height="42" alt="image" src="https://github.com/user-attachments/assets/8b1550c7-832a-4562-8de8-763505d66a9d" />

<img width="589" height="103" alt="image" src="https://github.com/user-attachments/assets/efa61ccd-036d-4191-a25e-36d964eceb77" />


```
docker run -d --name <nombre contenedor> --network <nombre red> <nombre imagen>
```

```
docker run -d --name contenedor1 --network net-curso01 nginx:alpine
docker run -d --name contenedor2 --network net-curso01 nginx:alpine
docker run -d --name contenedor3 --network net-curso01 nginx:alpine
docker run -d --name contenedor4 --network net-curso01 nginx:alpine
```

<img width="786" height="173" alt="image" src="https://github.com/user-attachments/assets/aaaefe0e-e87f-4745-9cee-82c6757079df" />


### Para saber a qué red está conectado un contenedor

```
docker inspect <nombre contenedor>
```

```
docker inspect contenedor1
docker inspect contenedor2
docker inspect contenedor3
docker inspect contenedor4
```

<img width="865" height="442" alt="image" src="https://github.com/user-attachments/assets/99f4ff97-6128-4224-92a2-5e171f28a55f" />

<img width="947" height="439" alt="image" src="https://github.com/user-attachments/assets/c495c1e4-970a-4483-a1c0-8c1c20d63654" />

<img width="929" height="444" alt="image" src="https://github.com/user-attachments/assets/640c7e8f-9799-458b-bb8f-c9e5e3266a96" />

<img width="816" height="424" alt="image" src="https://github.com/user-attachments/assets/589febc8-027c-4cc9-9482-a91ba82cf1d9" />

ó

```
docker network inspect <nombre red> 
```

```
docker network inspect net-curso01 
```

<img width="691" height="874" alt="image" src="https://github.com/user-attachments/assets/35c8af8c-2f43-4346-96f0-b82cbcf47055" />

### Vincular contenedor a una red

```
docker network connect <nombre red> <nombre contenedor>
```
```
docker network connect net-curso02 contenedor1
```

<img width="679" height="49" alt="image" src="https://github.com/user-attachments/assets/5c4b8770-210b-4f8c-a63e-5466127b6400" />

<img width="782" height="604" alt="image" src="https://github.com/user-attachments/assets/3c8489fd-96cd-4170-824c-bfb48503097f" />

### Para desvincular un contenedor de una red

```
docker network disconnect <nombre red> <nombre contenedor>
```

```
docker network disconnect net-curso01 contenedor1
```

<img width="485" height="41" alt="image" src="https://github.com/user-attachments/assets/c0412928-1859-41ea-a219-b1b1ba2715f0" />

<img width="700" height="775" alt="image" src="https://github.com/user-attachments/assets/8e0422c5-297b-4980-84d9-4f6e57519ac2" />

### Para listar las redes existentes

```
docker network ls
```

<img width="336" height="118" alt="image" src="https://github.com/user-attachments/assets/e7bfde5b-b042-4115-85b4-32e1f3d384f5" />

### Crear los contenedores y las redes que se presentan en el esquema. Usar para todos los contenedores la imagen de nginx:alpine

![Imagen](esquema-ejercicio-redes.PNG)

# COLOCAR UNA CAPTURA DE LAS REDES EXISTENTES CREADAS

<img width="416" height="68" alt="image" src="https://github.com/user-attachments/assets/9b378db0-bf12-46a2-895b-6f8167379737" />

# COLOCAR UNA(S) CAPTURAS(S) DE LOS CONTENEDORES CREADOS EN DONDE SE EVIDENCIE A QUÉ RED ESTÁN VINCULADOS

<img width="627" height="825" alt="image" src="https://github.com/user-attachments/assets/fd0352fe-2019-4058-834a-9e1629a6f909" />

<img width="594" height="735" alt="image" src="https://github.com/user-attachments/assets/d4098372-7964-4704-8ac2-3bb455023608" />

### Para eliminar las redes creadas

```
docker network rm <nombre de la red>
```

```
docker network rm primer-red
```

<img width="1530" height="205" alt="image" src="https://github.com/user-attachments/assets/9e636055-8389-432a-a9ee-160881933bc0" />

<img width="921" height="114" alt="image" src="https://github.com/user-attachments/assets/39eb7369-0899-4988-9bbb-8423e596e8a5" />

