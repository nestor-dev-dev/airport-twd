# Panel Informativo de Estación (Frontend + API REST)

Aplicación web full-stack para la visualización en tiempo real y gestión administrativa de operaciones de vuelos (salidas, llegadas, puertas de embarque y estados), compuesta por un cliente web modular y una API REST documentada con OpenAPI.

Demo en vivo (Frontend): https://nestor-dev-dev.github.io/airport-twd/frontend/

## Stack Tecnológico
- **Frontend:** JavaScript (ES6 Modules), HTML5, CSS3 (Grid, Flexbox, diseño Mobile-First)
- **Backend:** API REST con PHP (Slim 4), Doctrine ORM, OpenAPI / Swagger
- **Base de Datos e Infraestructura:** MySQL, Docker, Docker Compose
- **Seguridad y Testing:** Autenticación JWT, control de acceso por roles y PHPUnit (156 tests automatizados)

## Arquitectura y Características Principales
- **Patrón MVC y Desacoplamiento:** Cliente estructurado en modelos, vistas y controlador, con una capa de servicios independiente para la comunicación HTTP y *mappers* DTO para traducir estructuras entre cliente y servidor.
- **Optimización de Rendimiento:** Sistema de caché en memoria RAM en el frontend para aplicar filtros y búsquedas de forma instantánea sin sobrecargar la API, sincronizando en segundo plano.
- **API REST Estándar:** Separación de responsabilidades en `QueryControllers` y `CommandControllers`, identificadores seguros en formato ULID, soporte de caché HTTP mediante `ETags` (304 Not Modified) y documentación interactiva en Swagger.
- **Seguridad y Robustez:** Protección de rutas de escritura mediante `JwtMiddleware` y validación de rol (`GESTOR` / `PÚBLICO`), validaciones preventivas de integridad referencial en cliente y gestión controlada de códigos HTTP.

## Ejecución Local

### 1. Backend (Docker)
1. Acceder a la carpeta `backend` y levantar los contenedores:
   ```bash
   docker-compose up -d
