# Forohub

ForoHub es una API que te permite explorar y gestionar tópicos y usuarios en un foro, implementando operaciones CRUD y autenticación JWT.

<img src="https://github.com/Fernandofcsp/forohub/assets/73980852/961285d8-d11b-4090-b48b-94ebc35ae04a" alt="Animación" style="width:80%;">

<a href="https://drive.google.com/file/d/103Fyq_TgCgPU1gdl-7cTw2v0R_JeFMBk/view?usp=sharing">Video mostrando funcionalidad de endpoints para Tópicos</a>


## Comenzando 🚀

Para probar el proyecto clona el repositorio y abre el proyecto en tu IDE favorito.


### Pre-requisitos 📋

*JAVA SDK 17

*IDE (IntelliJ)

*Maven
  
*MySQL: versión 8 en adelante


### Instalación 🔧


1. Clona el repositorio: `git clone https://github.com/Fernandofcsp/forohub.git`
2. Crea la base de datos en mysql con el nombre forohub utiliza el comando en MySQLCommandLine `CREATE DATABASE forohub;`
3. Configura el archivo aplication.properties con el usuario y contraseña de mysql.
4. Arranca el proyecto: `mvn spring-boot:run`


### Funciones 📖

<div style="display: flex; align-items: flex-start;">
  <div style="flex: 1;">
    <ul>
      <li>Autenticación y autorización de usuarios</li>
      <img src="https://github.com/Fernandofcsp/forohub/assets/73980852/d1879d4d-dcff-4bc9-bc7a-4bc7095661fe" alt="Animación" style="width:50%;">
      <li>Crear, leer, actualizar y eliminar tópicos</li>
      <img src="https://github.com/Fernandofcsp/forohub/assets/73980852/6fcc06f7-a424-4504-9097-f07041056726" alt="Animación" style="width:50%;">
      <li>Crear, leer, actualizar y eliminar cursos</li>
      <img src="https://github.com/Fernandofcsp/forohub/assets/73980852/a7aed556-97c7-4252-8ae8-e96bf64b9afb" alt="Animación" style="width:50%;">
      <li>Crear, leer, actualizar y eliminar usuarios</li>
      <img src="https://github.com/Fernandofcsp/forohub/assets/73980852/00d9c9ca-1a43-466c-82e2-52d90be60dd6" alt="Animación" style="width:50%;">
      <li>Crear, leer, actualizar y eliminar respuestas a tópicos</li>
      <img src="https://github.com/Fernandofcsp/forohub/assets/73980852/f63a1db8-bcd9-4f30-9486-62843a0f9059" alt="Animación" style="width:50%;">
    </ul>
  </div>
</div>


## Estructura 💻
```
forohub/
├── pom.xml
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/alura/forohub/
│   │   │       ├── ForohubApplication.java
│   │   │       ├── config/
│   │   │       │   ├── OpenApiConfig.java
│   │   │       ├── controller/
│   │   │       │   ├── AuthController.java
│   │   │       │   ├── CursoController.java
│   │   │       │   ├── PerfilController.java
│   │   │       │   ├── RespuestaController.java
│   │   │       │   ├── TopicoController.java
│   │   │       │   ├── UsuarioController.java
│   │   │       │   ├── UsuarioPerfilController.java
│   │   │       ├── dto/
│   │   │       │   ├── UsuarioDto.java
│   │   │       ├── model/
│   │   │       │   ├── Curso.java
│   │   │       │   ├── Perfil.java
│   │   │       │   ├── Respuesta.java
│   │   │       │   ├── Topico.java
│   │   │       │   ├── Usuario.java
│   │   │       │   ├── UsuarioPerfil.java
│   │   │       │   ├── UsuarioPerfilId.java
│   │   │       ├── repository/
│   │   │       │   ├── CursoRepository.java
│   │   │       │   ├── PerfilRepository.java
│   │   │       │   ├── RespuestaRepository.java
│   │   │       │   ├── TopicoRepository.java
│   │   │       │   ├── UsuarioPerfilRepository.java
│   │   │       │   ├── UsuarioRepository.java
│   │   │       ├── security/
│   │   │       │   ├── JwtAuthenticationEntryPoint.java
│   │   │       │   ├── JwtRequestFilter.java
│   │   │       │   ├── JwtTokenUtil.java
│   │   │       │   ├── JwtUserDetailService.java
│   │   │       │   ├── SecurityConfig.java
│   │   │       │   ├── SecurityConstants.java
│   │   │       ├── ForohubApplication.java
│   │   │       ├── PasswordGenerator.java
│   │   └── resources/
│   │   │       ├── db.migration/
│   │   │       │   ├── V1__Init.sql
│   │       └── application.properties
```

##Descripción de los paquetes: 📦

Configuracion de swagger OpenApi (Actualmente en desarrollo pues no aparece la opcion de Authorize, las consultas a los endpoints se hacen en postman por el momento):

* config: Configuraciones del proyecto, como OpenAPI.
  
Controller: Controladores que manejan las solicitudes HTTP.

* AuthController.java: Maneja la autenticación.
* CursoController.java: Maneja las operaciones relacionadas con los cursos.
* PerfilController.java: Maneja las operaciones relacionadas con los perfiles.
* RespuestaController.java: Maneja las respuestas a los tópicos.
*TopicoController.java: Maneja las operaciones relacionadas con los tópicos.
* UsuarioController.java: Maneja las operaciones relacionadas con los usuarios.
* UsuarioPerfilController.java: Maneja las relaciones entre usuarios y perfiles.
  
DTO: Objetos de transferencia de datos.

* UsuarioDto.java: DTO para manejar los datos del usuario.
  
Model: Entidades del modelo de datos.

* Curso.java: Entidad para los cursos.
* Perfil.java: Entidad para los perfiles.
* Respuesta.java: Entidad para las respuestas.
* Topico.java: Entidad para los tópicos.
* Usuario.java: Entidad para los usuarios.
* UsuarioPerfil.java: Entidad para la relación entre usuarios y perfiles.
* UsuarioPerfilId.java: Clave compuesta para UsuarioPerfil.
  
Repository: Repositorios para interactuar con la base de datos.

* CursoRepository.java: Repositorio para cursos.
* PerfilRepository.java: Repositorio para perfiles.
* RespuestaRepository.java: Repositorio para respuestas.
* TopicoRepository.java: Repositorio para tópicos.
* UsuarioPerfilRepository.java: Repositorio para la relación entre usuarios y perfiles.
* UsuarioRepository.java: Repositorio para usuarios.
  
Security: Clases relacionadas con la seguridad y JWT.

* JwtAuthenticationEntryPoint.java: Punto de entrada para la autenticación.
* JwtRequestFilter.java: Filtro para JWT.
* JwtTokenUtil.java: Utilidad para manejar JWT.
* JwtUserDetailService.java: Servicio de detalles del usuario.
* SecurityConfig.java: Configuración de seguridad.
* SecurityConstants.java: Constantes de seguridad.

Resources:
* V1__Init.sql: Archivo sql para crear las bases de datos iniciales en automático
* application.properties: Archivo de configuración de la aplicación Spring Boot (conexión a la base de datos, puerto del servidor, etc.).


## Despliegue 📦

Compilar el proyecto con el plugin de spring-boot:run o start desde maven en IntelliJ, la configuracion del proyecto ya esta establecida en el archivo pom.xml

## Construido con 🛠️

* [IntelliJCommunity](https://www.jetbrains.com/idea/download/?section=windows) - Programación
* [Maven](https://maven.apache.org/) - Manejador de dependencias
* [JAVA](https://www.java.com/es/) - Lenguaje
* [Spring Boot](https://spring.io/projects/spring-boot) - Simplifica la creación de aplicaciones Spring, proporcionando configuración automática y herramientas integradas.
* [Spring Data JPA](https://spring.io/projects/spring-data-jpa) - Facilita el acceso a bases de datos relacionales en aplicaciones Spring, reduciendo la necesidad de escribir código SQL.
* [MYSQL](https://dev.mysql.com/downloads/installer/) - Gestor de base de datos.
* [Maven](https://maven.apache.org/) - Herramienta para gestionar proyectos de software Java, automatizando la compilación, las pruebas y la gestión de dependencias.

## Versionado 📌

1.0 (Git)

## Autor ✒️
* **Fernando Sandoval** - *Codificación y diseño* - [fernandofcsp](https://github.com/fernandofcsp)
  
