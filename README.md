# Practica Docker

Aplicacion con PHP, Vue.js y MySQL dockerizada.

## Proceso documentado

### Backend Dockerfile
Multi-stage build con PHP 8.1 y Alpine. Instalo bash para el script wait-for-it.sh y las extensiones PDO para MySQL.

### Frontend Dockerfile
Imagen de Node 18, instalo dependencias y ejecuto npm run serve.

### docker-compose.yml
4 contenedores:
- **mysql_contenidor**: Base de datos con volumen para los datos. Ejecuta init.sql al arrancar.
- **backend_contenidor**: Espera a MySQL con wait-for-it.sh antes de arrancar.
- **frontend_contenidor**: Vue en el puerto 8080.
- **adminMySQL_contenidor**: phpMyAdmin en el puerto 8081.


## URLs

- Frontend: http://localhost:8080
- Backend: http://localhost:8000/api/items
- phpMyAdmin: http://localhost:8081
