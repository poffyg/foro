# ForoHub

ForoHub es una API REST para gestionar un foro de discusión. Permite a los usuarios crear, leer, actualizar y eliminar tópicos.

## Tecnologías Utilizadas

- Java
- Spring Boot
- Spring Data JPA
- H2 Database
- Spring Security

## Requisitos Previos

- JDK 11 o superior
- Maven
- IntelliJ IDEA (opcional, pero recomendado)

## Instalación y Configuración

1. **Clonar el repositorio**:
    ```sh
    git clone https://github.com/tu-usuario/forohub.git
    cd forohub
    ```

2. **Configurar el proyecto en IntelliJ IDEA**:
    - Abrir IntelliJ IDEA.
    - Seleccionar `File -> Open` y elegir la carpeta del proyecto clonado.
    - Esperar a que IntelliJ IDEA descargue las dependencias de Maven.

3. **Configurar la base de datos**:
    - El proyecto está configurado para usar la base de datos en memoria H2 para desarrollo.
    - Puedes cambiar la configuración en `src/main/resources/application.properties` si deseas usar otra base de datos.

    ```properties
    spring.datasource.url=jdbc:h2:mem:forohub
    spring.datasource.driverClassName=org.h2.Driver
    spring.datasource.username=sa
    spring.datasource.password=password
    spring.jpa.database-platform=org.hibernate.dialect.H2Dialect
    spring.h2.console.enabled=true
    ```

## Ejecución

1. **Ejecutar la aplicación**:
    - En IntelliJ IDEA, abrir la clase `ForoHubApplication` y ejecutar el método `main`.

2. **Acceder a la consola H2**:
    - Abrir el navegador y visitar `http://localhost:8080/h2-console`.
    - Usar los siguientes datos de configuración para conectarse:
        - **JDBC URL**: `jdbc:h2:mem:forohub`
        - **User Name**: `sa`
        - **Password**: `password`

## Endpoints de la API

- **Crear un nuevo tópico** (POST): `/topics`
- **Mostrar todos los tópicos** (GET): `/topics`
- **Mostrar un tópico específico** (GET): `/topics/{id}`
- **Actualizar un tópico** (PUT): `/topics/{id}`
- **Eliminar un tópico** (DELETE): `/topics/{id}`

## Ejemplos de Solicitudes

### Crear un nuevo tópico

**Request**:
```sh
POST /topics
Content-Type: application/json

{
  "title": "Nuevo Tópico",
  "content": "Contenido del tópico",
  "author": "Autor"
}
