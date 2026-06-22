# Proyecto Fullstack - Sistema de Microservicios

## Integrantes

- Lorenzo Pérez
- Martin Gutiérrez
- Hanses Montilva

## Descripción

Proyecto desarrollado en Spring Boot bajo una arquitectura de microservicios. El sistema permite la gestión de clientes, productos, envíos, cupones, repartidores y autenticación mediante JWT.

La aplicación utiliza una arquitectura por capas:

- Controller (Presentación)
- Service (Lógica de negocio)
- Repository (Acceso a datos)

Además, incorpora documentación automática con Swagger y autenticación basada en JWT.

---

# Bibliotecas Utilizadas

### Dependencias principales

- Spring Boot
- Spring Web
- Spring Data JPA
- Spring Security
- MySQL Connector
- Lombok
- JWT (JJWT)
- SpringDoc OpenAPI (Swagger)
- JUnit 5
- Mockito

### Dependencia Swagger

```xml
<dependency>
    <groupId>org.springdoc</groupId>
    <artifactId>springdoc-openapi-starter-webmvc-ui</artifactId>
    <version>2.5.0</version>
</dependency>
```

---

# Herramientas de Instalación

Para ejecutar el proyecto es necesario instalar:

- Java JDK 17 o superior
- Maven
- MySQL Server
- IDE (IntelliJ IDEA, Eclipse o Visual Studio Code)
- Postman (para pruebas de API)
- Git

---

# Configuración del Proyecto

1. Clonar el repositorio:

```bash
git clone URL_DEL_REPOSITORIO
```

2. Ingresar al proyecto:

```bash
cd proyecto-fullstack
```

3. Configurar la base de datos MySQL.

4. Modificar el archivo:

```properties
application.properties
```

con las credenciales correspondientes.

5. Ejecutar cada microservicio.

---

# Servicio de Autenticación

El sistema utiliza autenticación Stateless mediante JWT (JSON Web Token).

## Ruta de Login

```http
POST /auth/login
```

### Ejemplo JSON

```json
{
  "nombreUsuario": "admin",
  "contrasena": "123456"
}
```

Al autenticarse correctamente se genera un token JWT que debe enviarse en las rutas protegidas:

```http
Authorization: Bearer TOKEN
```

---

# Ejemplos de Rutas API REST

## Microservicio Clientes

### Crear Cliente

```http
POST http://localhost:8080/clientes
```

### Listar Clientes

```http
GET http://localhost:8080/clientes
```

### Buscar Cliente por ID

```http
GET http://localhost:8080/clientes/{id}
```

### Actualizar Cliente

```http
PUT http://localhost:8080/clientes/{id}
```

### Eliminar Cliente

```http
DELETE http://localhost:8080/clientes/{id}
```

---

## Microservicio Productos

### Crear Producto

```http
POST http://localhost:8081/productos
```

### Listar Productos

```http
GET http://localhost:8081/productos
```

### Buscar Producto por ID

```http
GET http://localhost:8081/productos/{id}
```

### Actualizar Producto

```http
PUT http://localhost:8081/productos/{id}
```

### Eliminar Producto

```http
DELETE http://localhost:8081/productos/{id}
```

---

## Microservicio Envíos

### Crear Envío

```http
POST http://localhost:8082/envios
```

### Listar Envíos

```http
GET http://localhost:8082/envios
```

### Buscar Envío por ID

```http
GET http://localhost:8082/envios/{id}
```

### Actualizar Envío

```http
PUT http://localhost:8082/envios/{id}
```

### Eliminar Envío

```http
DELETE http://localhost:8082/envios/{id}
```

---

# Ejemplos de Rutas Swagger

Cada microservicio posee documentación automática mediante Swagger.

## Clientes

```http
http://localhost:8080/swagger-ui/index.html
```

## Productos

```http
http://localhost:8081/swagger-ui/index.html
```

## Envíos

```http
http://localhost:8082/swagger-ui/index.html
```

## Documentación JSON OpenAPI

```http
http://localhost:8080/v3/api-docs
```

```http
http://localhost:8081/v3/api-docs
```

```http
http://localhost:8082/v3/api-docs
```

---

# Testing

Se implementaron pruebas unitarias utilizando:

- JUnit 5
- Mockito

### Patrón AAA

#### Arrange

Preparación de datos de prueba.

#### Act

Ejecución de la acción a evaluar.

#### Assert

Verificación de resultados esperados.

Estas pruebas permiten validar el correcto funcionamiento de la lógica de negocio sin depender de la base de datos real.

---

# Tecnologías Utilizadas

- Java
- Spring Boot
- Spring Security
- JWT
- MySQL
- Maven
- Swagger OpenAPI
- JUnit
- Mockito
