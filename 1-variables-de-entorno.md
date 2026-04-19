# Variables de Entorno
### ¿Qué son las variables de entorno?

Las variables de entorno son valores dinámicos que residen en el sistema operativo y funcionan como una "memoria de corto plazo" para las aplicaciones y procesos. En lugar de escribir datos sensibles o rutas específicas directamente en el código de un programa (lo cual es poco seguro y rígido), se almacenan en estas variables para que el software las consulte en tiempo de ejecución. Son fundamentales en el desarrollo de software y en Docker, ya que permiten cambiar el comportamiento de una aplicación (como las credenciales de una base de datos o el puerto de un servidor) dependiendo de si se encuentra en un entorno de pruebas o en uno de producción, sin necesidad de modificar ni una sola línea de código.

# COMPLETAR

### Para crear un contenedor con variables de entorno

```
docker run -d --name <nombre contenedor> -e <nombre variable1>=<valor1> -e <nombre variable2>=<valor2>
```
```
docker run -d --name mi-servidor-nginx -e username=estudiante -e role=admin nginx:alpine
```

<img width="999" height="73" alt="image" src="https://github.com/user-attachments/assets/a133fb3d-ed25-4b0b-891e-c7b2d13ab4cd" />

### Crear un contenedor a partir de la imagen de nginx:alpine con las siguientes variables de entorno: username y role. Para la variable de entorno rol asignar el valor admin.

# COMPLETADO

# CAPTURA CON LA COMPROBACIÓN DE LA CREACIÓN DE LAS VARIABLES DE ENTORNO DEL CONTENEDOR ANTERIOR
```
docker exec mi-servidor-nginx env
```

<img width="996" height="299" alt="image" src="https://github.com/user-attachments/assets/048a78a5-6b64-433e-9032-dff27a39e97f" />

### Crear un contenedor con la imagen de mysql, mapear todos los puertos
# COMPLETAR

<img width="516" height="230" alt="image" src="https://github.com/user-attachments/assets/a9bcb1fb-05a7-4057-b9b3-b651635b55e9" />

<img width="770" height="49" alt="image" src="https://github.com/user-attachments/assets/0701c70f-a529-4a79-8d4d-92db7ac2a738" />

### ¿El contenedor se está ejecutando?

No se está ejecutando.

# COMPLETAR

<img width="936" height="250" alt="image" src="https://github.com/user-attachments/assets/077e525d-6d3b-4a1d-a658-3c470fca92bf" />

### Identificar el problema
# COMPLETAR

<img width="736" height="138" alt="image" src="https://github.com/user-attachments/assets/d3328409-790d-401a-bc1c-7259e358a09a" />

Se ejecutó correctamente.

<img width="550" height="55" alt="image" src="https://github.com/user-attachments/assets/d8f8cf49-0387-4f09-9bf8-9b2d30ab676f" />

### Para crear un contenedor con variables de entorno especificadas
- Portabilidad: Las aplicaciones se vuelven más portátiles y pueden ser desplegadas en diferentes entornos (desarrollo, pruebas, producción) simplemente cambiando el archivo de variables de entorno.
- Centralización: Todas las configuraciones importantes se centralizan en un solo lugar, lo que facilita la gestión y auditoría de las configuraciones.
- Consistencia: Asegura que todos los miembros del equipo de desarrollo o los entornos de despliegue utilicen las mismas configuraciones.
- Evitar Exposición en el Código: Mantener variables sensibles como contraseñas, claves API, y tokens fuera del código fuente reduce el riesgo de exposición accidental a través del control de versiones.
- Control de Acceso: Los archivos de variables de entorno pueden ser gestionados con permisos específicos, limitando quién puede ver o modificar la configuración sensible.

### ¿Qué bases de datos existen en el contenedor creado?
# COMPLETAR

<img width="921" height="230" alt="image" src="https://github.com/user-attachments/assets/0a96f1a9-e815-4afc-af31-f9851d5690b3" />

