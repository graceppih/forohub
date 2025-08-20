# 📚 ForoHub

> 🚀 API REST para un sistema de foro.  
> Permite a los usuarios registrarse, crear tópicos, publicar respuestas y gestionar cursos.  

ForoHub está construido con **Spring Boot 3**, **Spring Security**, **JWT**, **Java 21** y **JPA/Hibernate**, siguiendo una arquitectura **limpia y modular** que asegura mantenibilidad y escalabilidad.

---

## ✨ Características

- 🔒 **Autenticación y Autorización** con JWT (Bearer Token).  
- 👥 **Gestión de Usuarios y Perfiles** con roles y permisos.  
- 📝 **Tópicos y Respuestas** estilo foro comunitario.  
- 🎓 **Administración de Cursos** asociados a usuarios y temas.  
- 📜 **Swagger/OpenAPI** para documentación interactiva.  
- 🗄️ **Persistencia** con JPA/Hibernate sobre **MySQL** (H2 para pruebas).  
- 🚀 **Arquitectura modular** en `controller`, `domain` e `infra`.  

---

## 🏛️ Arquitectura

El proyecto se organiza en **3 capas principales**:

controller → expone endpoints REST
domain → entidades, DTOs, servicios y repositorios
infra → seguridad, excepciones y utilidades

yaml
Copiar código

---

## 🗄️ Modelo de Datos

El sistema incluye **5 tablas principales** y sus relaciones:

- 📜 **Usuario ↔ Perfil** → Muchos a muchos  
- 🔒 **Usuario ↔ Tópico** → Uno a muchos  
- 👥 **Usuario ↔ Respuesta** → Uno a muchos  
- 🎓 **Curso ↔ Tópico** → Uno a muchos  
- 💬 **Tópico ↔ Respuesta** → Uno a muchos  

---

## 🛠️ Tecnologías utilizadas

- ☕ **Java 21**
- 🌱 **Spring Boot 3**
- 🔐 **Spring Security 6 + JWT**
- 🗄️ **Spring Data JPA (Hibernate)**
- 🐬 **MySQL / H2**
- 📜 **Swagger / OpenAPI 3**
- 📦 **Maven**

---

## 🚀 Instalación y Ejecución

### 1️⃣ Clonar repositorio
```bash
git clone https://github.com/graceppih/forohub.git
cd forohub
2️⃣ Configurar base de datos
Editar application.properties o application.yml en src/main/resources/:

properties
Copiar código
spring.datasource.url=jdbc:mysql://localhost:3306/forohub
spring.datasource.username=usuario
spring.datasource.password=contraseña
3️⃣ Compilar y ejecutar
bash
Copiar código
mvn clean install
mvn spring-boot:run
4️⃣ Acceder a la API
📖 Swagger UI → http://localhost:8080/swagger-ui.html

🌐 API Base → http://localhost:8080

📖 Endpoints principales
🔑 Autenticación
POST /auth/login → Generar token JWT

👤 Usuarios
POST /usuarios → Crear usuario

GET /usuarios → Listar usuarios

PUT /usuarios → Actualizar usuario

DELETE /usuarios/{id} → Eliminar usuario

📚 Cursos
POST /cursos → Crear curso

GET /cursos → Listar cursos

🗨️ Tópicos
POST /topicos → Crear tópico

GET /topicos → Listar tópicos

💬 Respuestas
POST /respuestas → Agregar respuesta

GET /respuestas → Listar respuestas

🔐 Seguridad con JWT
Autenticarse con POST /auth/login.

El servidor responde con un Bearer Token.

Todas las peticiones deben incluir el header:
