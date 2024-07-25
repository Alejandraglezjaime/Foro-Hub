
<img src="https://img.shields.io/badge/STATUS-FINALIZADO-green" display="inline" >


# Forum Hub

Forum Hub es una aplicación web de foro desarrollada con Spring Boot. Esta aplicación incluye funcionalidades CRUD (Crear, Leer, Actualizar, Eliminar) y utiliza JWT (JSON Web Token) para autenticación y autorización, asegurando así un acceso seguro a los recursos.

## Características

- **CRUD de Tópicos**: Permite crear nuevos tópicos, leer los existentes, actualizarlos y eliminarlos.
- **Autenticación y Autorización**: La seguridad está garantizada mediante el uso de tokens JWT, que verifican la identidad del usuario y autorizan el acceso a los recursos.
- **Validaciones**: Los datos de entrada son validados utilizando Jakarta Bean Validation para asegurar que cumplen con los requisitos necesarios antes de ser procesados.
- **Swagger**: La documentación de la API es generada automáticamente, facilitando la visualización y prueba de los endpoints disponibles.

## Base de datos
Necesitarás utilizar una base de datos para almacenar la información de la aplicación. Para crear un tópico necesitan las siguientes informaciones:

- id
- título
- mensaje
- fecha de creación
- status (estado del tópico)
- autor
- curso

La siguiente imágen muestra un diagrama para la creación de la base de datos con los campos requeridos por nuestro cliente.

 ![diagrama de la base de datos]()

 ## Funcionalidad 

 ### Registro de un nuevo tópico 

 La API debe contar con un endpoint (punto final) para el registro de tópicos, y debe aceptar solicitudes del tipo POST para la URI /tópicos.
Los datos del tópico (título, mensaje, autor y curso) deben ser enviados en el cuerpo de la solicitud, en formato JSON.

  → No olvides utilizar la anotación @RequestBody para que tu proyecto Spring reciba correctamente los datos del cuerpo de la solicitud.
  → Además, recuerda que el tópico debe ser guardado en la base de datos construida para el proyecto, así que aquí tienes el recordatorio de utilizar el método save del JpaRepository para realizar la persistencia de los datos del tópico creado.

Reglas de negocio

- Todos los campos son obligatorios, por lo tanto, es necesario verificar si todos los campos se están ingresando correctamente.
- La API no debe permitir el registro de tópicos duplicados (con el mismo título y mensaje).

### Listado de tópicos

La API debe contar con un punto final para el listado de todos los tópicos, y debe aceptar solicitudes del tipo GET para la URI /tópicos.

Los datos de los tópicos (título, mensaje, fecha de creación, estado, autor y curso) deben ser devueltos en el cuerpo de la respuesta, en formato JSON.

  → Recordando que al tratar con el CRUD es necesario trabajar con JpaRepository asociado al tópico, especialmente en la lista de datos de la base de datos utilizamos el método findAll.

###### Opcionales:

- [ ] Mostrar los primeros 10 resultados ordenados por fecha de creación del tópico en orden ASC
- [ ] Mostrar los resultados usando un criterio de búsqueda, listar por: nombre de curso y año específico.

## Dependencias Utilizadas

- **Swagger**: Para la generación de documentación de la API.
- **Lombok**: Simplifica el código eliminando el boilerplate como getters, setters y constructores.
- **Spring Web**: Proporciona las herramientas necesarias para construir aplicaciones web.
- **Spring Boot DevTools**: Ofrece herramientas de desarrollo que mejoran la productividad.
- **Spring Data JPA**: Facilita la interacción con la base de datos mediante JPA (Java Persistence API).
- **Flyway Migration**: Gestiona las migraciones de la base de datos.
- **MySQL Driver**: Controlador necesario para la conexión con bases de datos MySQL.
- **Validation**: Biblioteca para realizar validaciones de datos.
- **Spring Security**: Proporciona funcionalidades de autenticación y autorización.

