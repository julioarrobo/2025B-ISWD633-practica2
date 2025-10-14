### Crear contenedor de Postgres sin que exponga los puertos. Usar la imagen: postgres:15-alpine3.21
docker run -d --name postgres-container -e POSTGRES_USER=admin -e POSTGRES_PASSWORD=admin -e POSTGRES_DB=mi_base postgres:15-alpine3.21
<img width="1540" height="459" alt="image" src="https://github.com/user-attachments/assets/70a9092a-2882-4037-baae-96f5f3ca73d9" />


### Crear un cliente de postgres. Usar la imagen: dpage/pgadmin4
# COMPLETAR
docker run -d --name pgadmin4 --network pgnet -e PGADMIN_DEFAULT_EMAIL=julio.arrobo@epn.edu.ec -e PGADMIN_DEFAULT_PASSWORD=admin123 -p 5050:80 dpage/pgadmin4


La figura presenta el esquema creado en donde los puertos son:
- a: (5050)
- b: (80)
- c: (5432)

![Imagen](esquema-2-ejercicio.PNG)  

## Desde el cliente
### Acceder desde el cliente al servidor postgres creado.
# COMPLETAR CON UNA CAPTURA DEL LOGIN
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/e0dae841-46df-4ba9-b3e4-c32cbad8105c" />

### Crear la base de datos info, y dentro de esa base la tabla personas, con id (serial) y nombre (varchar), agregar un par de registros en la tabla, obligatorio incluir su nombre.

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/b1e14422-9d69-4b08-9efe-4c14fb3ff7c6" />

## Desde el servidor postgresl
docker exec -it postgres-container sh
### Acceder al servidor
### Conectarse a la base de datos info
# COMPLETAR
<img width="651" height="347" alt="image" src="https://github.com/user-attachments/assets/feee4162-2fd4-4652-9763-e50e525f7cbc" />

### Realizar un select *from personas
# AGREGAR UNA CAPTURA DE PANTALLA DEL RESULTADO
<img width="702" height="452" alt="image" src="https://github.com/user-attachments/assets/416b08dd-db54-4ae1-991e-00082d11adf1" />

