# API REST - Gestión de Biblioteca

API REST desarrollada en Laravel para la gestión de libros y usuarios con autenticación basada en JWT (JSON Web Tokens).

## Tecnologías Utilizadas

- Framework: Laravel 12
- Lenguaje: PHP 8.2+
- Autenticación: JWT (tymon/jwt-auth)
- Base de Datos: MySQL

## Instalación y Configuración Local

1. Clonar el repositorio:
   git clone <URL_DE_TU_REPOSITORIO>
   cd <NOMBRE_DE_LA_CARPETA>

2. Instalar dependencias de PHP:
   composer install

3. Configurar variables de entorno:
   cp .env.example .env
   (Asegúrate de configurar la base de datos biblioteca_db en el archivo .env)

4. Generar clave de aplicación y clave secreta JWT:
   php artisan key:generate
   php artisan jwt:secret

5. Ejecutar migraciones:
   php artisan migrate

6. Iniciar el servidor de desarrollo:
   php artisan serve

## Endpoints de la API

### Autenticación (/api/auth)

- POST /api/auth/register - Registro de nuevos usuarios
- POST /api/auth/login - Inicio de sesión y obtención del Bearer Token
- GET /api/auth/me - Obtener datos del usuario autenticado (Protegido)
- POST /api/auth/logout - Cierre de sesión e invalidación de token (Protegido)

### Libros (/api/books) (Todos protegidos por JWT)

- GET /api/books - Listar todos los libros
- POST /api/books - Crear un nuevo libro
- GET /api/books/{id} - Obtener un libro específico
- PUT/PATCH /api/books/{id} - Actualizar un libro
- DELETE /api/books/{id} - Eliminar un libro
