## Esquema para el ejercicio
![Imagen](esquema-4-ejercicio.PNG)

### Crear la red
# COMPLETAR: docker network create net-wp -d bridge

### Crear el contenedor mysql a partir de la imagen mysql:8, configurar las variables de entorno necesarias
# COMPLETAR: docker run -d --name mysql-wp --network net-wp -e MYSQL_ROOT_PASSWORD=root123 -e MYSQL_DATABASE=wordpress -e MYSQL_USER=wp_user -e MYSQL_PASSWORD=wp_pass mysql:8

### Crear el contenedor wordpress a partir de la imagen: wordpress, configurar las variables de entorno necesarias
# COMPLETAR: docker run -d --name wordpress-wp --network net-wp -e WORDPRESS_DB_HOST=mysql-wp:3306 -e WORDPRESS_DB_USER=wp_user -e WORDPRESS_DB_PASSWORD=wp_pass -e WORDPRESS_DB_NAME=wordpress -p 8080:80 wordpress

De acuerdo con el trabajo realizado, en el esquema del ejercicio el puerto a es **(8080)**

Ingresar desde el navegador al wordpress y finalizar la configuración de instalación.
# COLOCAR UNA CAPTURA DE LA CONFIGURACIÓN
configuracion wordpress
<img width="826" height="828" alt="image" src="https://github.com/user-attachments/assets/c7b20e83-4c3a-4735-a879-2f0073002efa" />

Desde el panel de admin: cambiar el tema y crear una nueva publicación.
Ingresar a: http://localhost:9300/ 
recordar que a es el puerto que usó para el mapeo con wordpress
# COLOCAR UNA CAPTURA DEL SITO EN DONDE SEA VISIBLE LA PUBLICACIÓN.
<img width="960" height="1080" alt="image" src="https://github.com/user-attachments/assets/11963761-1291-4d9e-b0ff-4096218f4e42" />


### Eliminar el contenedor wordpress
# COMPLETAR
docker stop wordpress, docker rm wordpress

### Crear nuevamente el contenedor wordpress
Ingresar a: http://localhost:9300/ 
recordar que a es el puerto que usó para el mapeo con wordpress

### ¿Qué ha sucedido, qué puede observar?
# COMPLETAR
La pagina de wordpress se reinicio y volvio a pedir las credenciales
<img width="960" height="1080" alt="image" src="https://github.com/user-attachments/assets/91c9856b-9c7b-4d3c-af49-53bc2d68b03a" />
