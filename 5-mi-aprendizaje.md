# COMPLETAR  
Comparando sus conocimientos antes de hacer la práctica con sus conocimientos después de hacer la tarea, explicar los principales aprendizajes logrados para beneficio de su formación profesional.  

Tras concluir esta segunda práctica, mi visión sobre la infraestructura de aplicaciones ha incrementado significativamente. Si antes comprendía a los contenedores como entidades aisladas, ahora los entiendo como un ecosistema interconectado mediante redes bridge, donde la correcta gestión de variables de entorno es clave para la configuración. He aprendido a crear contenedores conectado con imágenes de alta demanda en la industria como PostgreSQL, MySQL, Nginx y WordPress, logrando que se comuniquen de forma segura y eficiente. Para mi formación profesional, esto representa un salto: ya no solo instalo software, sino que estoy cerca diseñar entornos de ejecución y escalables, fundamentales en desarrollo de software.

Si solucionó un problema presentado al realizar la práctica también se debe documentar.

Como mencioné en mi ejercicio 4, los problemas que tuve fue:
1. El primer problema fue crear el contenedor de mysql y wordpress, sin embargo aquí, al ingresar al localhost correspondiente, este mostró el error de:
   ```
   ```
   <img width="1903" height="920" alt="Captura de pantalla 2026-04-19 211339" src="https://github.com/user-attachments/assets/b1791e1b-9a1d-46a7-8b84-9fa7e8c7153c" />
   ```
   ```
    Estó me sorprendió, sin embargo tras un rato revisando, noté que luego de crear la red net-wp y crear el contenedor de mysql, este no fue creado correctamente especificando a que debía estár conectado a la red net-wp. Por ello al, crear la imagen de wordpress sucedió el error. Al inicio hubo frustración, pero recordando lo que me enseñó mi docente logré encontrá una solución. Revisando la imagen de la arquitectura proporcionada por mi docente utilicé el comando inspect para revisar si la estructura se cumplía y gracias a ello solo utilice un comando:
   ```
   docker network connect mi-mysql
   ```
Solucionandolo exitosamente

  <img width="1662" height="81" alt="image" src="https://github.com/user-attachments/assets/193a92ea-fff4-43fd-bb8c-8995124b6f48" />
```
```
   <img width="1361" height="790" alt="image" src="https://github.com/user-attachments/assets/f8ee3033-f04c-45a5-a6c7-f23b7c477d63" />

3. Otro de los problemas fue que al volver a crear el contenedor de wordpress, el localhost hacia el puerto 9300 se mostraba en blanco, lo cual no me dejó conforme porque pensé que funcionaría de nuevo, entonces volví a intentar la instalación desde cero y funcionó.
````
````
<img width="1909" height="950" alt="Captura de pantalla 2026-04-19 213839" src="https://github.com/user-attachments/assets/ff47804e-3848-4b95-9336-7e48e42f03f6" />
````
````
<img width="1641" height="165" alt="image" src="https://github.com/user-attachments/assets/8b5b2653-203b-4b7f-a18e-7e72a4d5a87a" />
````
````
<img width="1919" height="456" alt="image" src="https://github.com/user-attachments/assets/1dbbf156-c7dd-40c2-91a8-40e0cb67d2d6" />

# Consultar: Cómo se gestionan datos confidenciales con los secretos de Docker (Docker Secrets).

Durante el desarrollo de las prácticas, se ha configurado credenciales (usuarios y contraseñas) directamente en las variables de entorno. Si bien es un método funcional para entornos de desarrollo local, en un entorno de producción profesional se descubrió que esto representa un riesgo crítico de seguridad, ya que cualquier persona con acceso al comando docker inspect o al historial de la terminal podría visualizar estos datos en texto plano.

Para solventar esto, Docker ofrece una herramienta avanzada llamada Docker Secrets, diseñada específicamente para manejar información sensible como certificados SSL, claves de API y contraseñas de bases de datos.

Entender está herramienta marca el cambio entre un desarrollo básico (como se está haciendo) hacia un desarrollo profesional.
