# Variables de Entorno
### ¿Qué son las variables de entorno?
son valores configurables que puedes pasar a un contenedor al momento de crearlo o ejecutarlo, y sirven para controlar el comportamiento de la aplicación dentro del contenedor sin necesidad de modificar su código.

### Para crear un contenedor con variables de entorno

```
docker run -d --name <nombre contenedor> -e <nombre variable1>=<valor1> -e <nombre variable2>=<valor2>
```

### Crear un contenedor a partir de la imagen de nginx:alpine con las siguientes variables de entorno: username y role. Para la variable de entorno rol asignar el valor admin.
docker run -d --name srv-nginx -e username=julio -e role=admin nginx:alpine

# CAPTURA CON LA COMPROBACIÓN DE LA CREACIÓN DE LAS VARIABLES DE ENTORNO DEL CONTENEDOR ANTERIOR
<img width="1313" height="266" alt="Captura de pantalla 2025-10-07 151816" src="https://github.com/user-attachments/assets/01b0d1ca-c309-495d-aba9-6ae8ce9c421b" />

### Crear un contenedor con la imagen de mysql, mapear todos los puertos
# COMPLETAR: docker run -d --name mysql-server -e MYSQL_ROOT_PASSWORD=admin -p 3306:3306 mysql

### ¿El contenedor se está ejecutando?
# COMPLETAR
<img width="1283" height="115" alt="image" src="https://github.com/user-attachments/assets/304b5a21-4be7-442d-a463-686b79d07ec4" />

### Identificar el problema
# COMPLETAR

### Para crear un contenedor con variables de entorno especificadas
- Portabilidad: Las aplicaciones se vuelven más portátiles y pueden ser desplegadas en diferentes entornos (desarrollo, pruebas, producción) simplemente cambiando el archivo de variables de entorno.
- Centralización: Todas las configuraciones importantes se centralizan en un solo lugar, lo que facilita la gestión y auditoría de las configuraciones.
- Consistencia: Asegura que todos los miembros del equipo de desarrollo o los entornos de despliegue utilicen las mismas configuraciones.
- Evitar Exposición en el Código: Mantener variables sensibles como contraseñas, claves API, y tokens fuera del código fuente reduce el riesgo de exposición accidental a través del control de versiones.
- Control de Acceso: Los archivos de variables de entorno pueden ser gestionados con permisos específicos, limitando quién puede ver o modificar la configuración sensible.

### Crear un contenedor con mysql, mapear todos los puertos y configurar las variables de entorno mediante un archivo
# COMPLETAR: docker run -d --name mysql-container --env-file .env -p 3306:3306 mysql


# CAPTURA CON LA COMPROBACIÓN DE LA CREACIÓN DE LAS VARIABLES DE ENTORNO DEL CONTENEDOR ANTERIOR 
<img width="1056" height="343" alt="image" src="https://github.com/user-attachments/assets/da2cf715-cb81-452d-8644-5c7d43dc4c4d" />

### ¿Qué bases de datos existen en el contenedor creado?
<img width="1060" height="576" alt="image" src="https://github.com/user-attachments/assets/cf1de42b-ceab-4891-8568-ebbda994cce1" />

