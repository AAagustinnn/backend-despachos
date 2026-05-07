# Backend Despachos - Innovatech Chile

API REST desarrollada en Spring Boot 3.4.4 con Java 17 para gestionar los despachos de productos.

## Tecnologías
- Java 17
- Spring Boot 3.4.4
- MySQL 8.0
- Docker (multi-stage build)
- GitHub Actions (CI/CD)

## Requisitos
- Docker Desktop
- Docker Compose

## Variables de entorno
| Variable | Descripción | Ejemplo |
|---|---|---|
| DB_ENDPOINT | Host de la base de datos | localhost |
| DB_PORT | Puerto de la base de datos | 3306 |
| DB_NAME | Nombre de la base de datos | despachos_db |
| DB_USERNAME | Usuario de la base de datos | root |
| DB_PASSWORD | Contraseña de la base de datos | Admin1234! |

## Cómo ejecutar localmente

1. Clonar el repositorio:
```bash
git clone https://github.com/AAagustinnn/backend-despachos.git
cd backend-despachos
```

2. Crear archivo `.env` basado en `.env.example`:
```bash
cp .env.example .env
```

3. Levantar los contenedores:
```bash
docker compose up --build
```

4. Verificar que funciona:
http://localhost:8081/swagger-ui.html
## Pipeline CI/CD
El pipeline se activa automáticamente al hacer push en la rama `deploy`:
- Build de la imagen Docker
- Push a Docker Hub
- Despliegue automático en EC2

## Endpoints principales
- `GET /api/v1/despachos` - Obtener todos los despachos
- `POST /api/v1/despachos` - Crear un despacho
- `GET /api/v1/despachos/{id}` - Obtener despacho por ID
- `PUT /api/v1/despachos/{id}` - Actualizar despacho
- `DELETE /api/v1/despachos/{id}` - Eliminar despacho