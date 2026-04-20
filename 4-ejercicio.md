Esquema para el ejercicio
![Imagen](esquema-4-ejercicio.PNG)

### Crear la red
# COMPLETAR

<img width="402" height="30" alt="image" src="https://github.com/user-attachments/assets/08298b31-715f-412d-8a1a-e86fbba147a3" />

### Crear el contenedor mysql a partir de la imagen mysql:8, configurar las variables de entorno necesarias
# COMPLETAR

<img width="1012" height="223" alt="image" src="https://github.com/user-attachments/assets/cdb0b71d-f932-433d-9df3-89286e522eb3" />

### Crear el contenedor wordpress a partir de la imagen: wordpress, configurar las variables de entorno necesarias
# COMPLETAR

<img width="911" height="401" alt="image" src="https://github.com/user-attachments/assets/aafa9fcd-6fe5-46b4-bbb7-b1a74ad80cf2" />

De acuerdo con el trabajo realizado, en el esquema del ejercicio el puerto a es *9300*

Ingresar desde el navegador al wordpress y finalizar la configuración de instalación.
Ocurrió un problema debido a que mysql no está conectada a net-wp y a que las variables de entorno WORDPRESS_DB_USER Y WORDPRESS_DB_PASSWORD estaban con otros nombres y no con root y admin respectivamente.

<img width="1903" height="920" alt="image" src="https://github.com/user-attachments/assets/3b5be1bd-f1a6-4c3f-ac22-f90962441c05" />

<img width="1678" height="117" alt="image" src="https://github.com/user-attachments/assets/fe4dce07-31c8-44ec-ba87-8a62093c6598" />

# COLOCAR UNA CAPTURA DE LA CONFIGURACIÓN

<img width="1919" height="944" alt="image" src="https://github.com/user-attachments/assets/123e0b96-abf0-4ed2-bb97-7795df87f155" />

<img width="1911" height="929" alt="image" src="https://github.com/user-attachments/assets/e9da55c1-b946-4b8f-b8c8-df57361badfa" />

<img width="1906" height="928" alt="image" src="https://github.com/user-attachments/assets/5e8e4541-b1d4-44cf-9b96-1b4f2720b3f4" />

<img width="1898" height="939" alt="image" src="https://github.com/user-attachments/assets/c5cd5580-79fb-4514-ad39-1b792a82a39b" />

Desde el panel de admin: cambiar el tema y crear una nueva publicación.
Ingresar a: http://localhost:9300/ 
recordar que a es el puerto que usó para el mapeo con wordpress

<img width="1919" height="940" alt="image" src="https://github.com/user-attachments/assets/8fa1156d-2b8f-4fc7-ac5c-2351960f26db" />

# COLOCAR UNA CAPTURA DEL SITO EN DONDE SEA VISIBLE LA PUBLICACIÓN.

<img width="1915" height="943" alt="image" src="https://github.com/user-attachments/assets/8bb77129-5a7e-4150-9bf1-6ace3c513e64" />

<img width="1919" height="942" alt="image" src="https://github.com/user-attachments/assets/2e8c5089-1677-4ba4-90e8-58a557fc6e4a" />

<img width="1911" height="941" alt="image" src="https://github.com/user-attachments/assets/62dc677c-8fea-4aa0-a56f-7ff95edd9974" />

### Eliminar el contenedor wordpress
# COMPLETAR

```
docker rm -f mi-wordpress
```
<img width="419" height="53" alt="image" src="https://github.com/user-attachments/assets/ebd4bc98-5381-4fc1-adca-8f9c7fd8f13f" />

<img width="1919" height="940" alt="image" src="https://github.com/user-attachments/assets/a22d5af4-a9ba-4935-90bc-4529524253be" />

### Crear nuevamente el contenedor wordpress

<img width="1707" height="96" alt="image" src="https://github.com/user-attachments/assets/e7221b2b-e193-47a1-a999-5df4efeb9745" />

Ingresar a: http://localhost:9300/ 
recordar que a es el puerto que usó para el mapeo con wordpress

<img width="1909" height="950" alt="Captura de pantalla 2026-04-19 213839" src="https://github.com/user-attachments/assets/901cdb2d-2b2d-437e-8ccb-8fac1cadcfc0" />

<img width="1919" height="934" alt="image" src="https://github.com/user-attachments/assets/d94fbe0a-9aa1-407c-b6f9-db6bbc6f6ec8" />

### ¿Qué ha sucedido, qué puede observar?

Inicialmente, tras borrar y volver a crear el contenedor, al ingresar a *http://localhost:9300/* aparece una pantalla en blanco, no aparece ningun error. Tras realizar una investigación, se supo que es probable que el contenedor de wordpress y de mysql están enlazados con "memoria" del otro (sobre todo, mysql de wordpress) de tal manera que al borrar se pierde completamente la dirección pero al crear nuevamente, sigue sin funcionar pese a que mysql sigue apuntando a wordpress pero al antiguo, no al nuevo. Por ende, para que funcione es necesario instalar todo nuevamente incluido mysql. Luego se realizó un segundo intento de la actividad y en esta ocasión directamente se reinicia todo desde la configuración de wordpress.



# COMPLETAR

