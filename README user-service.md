# User-service 

Api encargada del procesamiento de los usuarios de JayWay.

## Diseño de la Api

- #### Estructura de la API:

    - Se utiliza una arquitectura de estilo RESTful.
    - Se utiliza nombres de recursos en plural para representar colecciones de recursos.
        - /usuarios como el recurso base para las operaciones relacionadas con los usuarios.

- #### Verbos HTTP y sus usos:

    - Se utiliza el verbo POST para crear un nuevo usuario en la base de datos.
    - Se utiliza el verbo GET para obtener información de un usuario específico.
    - Se utiliza el verbo PUT para actualizar información de un usuario existente.
Utiliza el verbo DELETE para eliminar un usuario existente.

- #### Rutas de la API:

| Resource | POST | GET                                   | PUT | PATCH | DELETE                                                                
|----------|------- |---------------------------------------|------- |------- | ------ |
| /users   |	Crear un nuevo cliente | 	Recuperar todos los clientes         |	Actualización masiva de clientes | Error |	Eliminar todos los clientes
| /users/1 |	Error | 	Recuperar los detalles del usuario 1 | Error |	Actualizar los detalles del cliente 1 | si existe	Quitar al usuario 1


- #### Parámetros y cuerpos de solicitud:

Se utiliza el cuerpo de la solicitud para enviar los datos del usuario a crear o actualizar en formato JSON.
- Los datos necesarios para la creacion del usuario son:

| Datos
| ------- |
| *firebaseUserId*
| displayName
| phoneNumber

- Los datos necesarios para que el usuario pueda realizar una compra son:

| Datos
| ------- |
| *firebaseUserId*
| displayName
| phoneNumber
| birthDate
| email
| age
| gender
| district
| province
| region
| country

ESTOS DATOS DEBERAN SER ACTUALIZADOS ANTES DE PODER COMPRAR MEDIANTE PATCH

- #### Respuestas y códigos de estado:

Se devuelven respuestas apropiadas con códigos de estado HTTP para indicar el resultado de la operación. 
- 201 Created para respuestas exitosas de creación. Ademas de los datos del usuario creado.
- 200 OK para respuestas exitosas de obtención o actualización. Ademas de los datos del usuario actualizado u obtenido.
- 204 No Content para respuestas exitosas de eliminación.


 - #### Seguridad:
Se considera la implementación de mecanismos de autenticación y autorización para proteger la API y restringir el acceso no autorizado.

## Estructura del proyecto

#### ejemplo de estructura del proyecto
    - controlles
    - dtos
    - exceptions
    - models
    - repositories
    - services
        - interfaces
    - utils
        - constants
        - mappers
    - configs
    - security

## Formato de Codigo

#### Lenguaje:
    el lenguaje a utilizar es el Ingles

#### Nomeclatura:
    Las clases en singular, comienzan por mayuscula y se usa CamelCase.
    Los metodos comienzan por un verbo, expresan lo que hacen y utilizan CamelCase
    Los paquetes en minusculas y de preferencia en plural y solo una palabra
    Las constantes y los Enums en mayusculas, puedo usar abreviaciones y snake_case.
    Las Interfaces llevaran como prefijo la letra I y utilizan CamelCase.
    Las clases que implementen las interfaces llevan el sufijo Impl y utilizan CamelCase.
    Las variables deben ser autoDescriptivas, sustantivas, utilizan CamelCase. Las variables temporales utilizan el prefijo temp. Las variables para bucles deben ser i,j,k,l. Las variables para denotar tamaños son n,m

## Optimizacion
    - Utilizacion de principios SOLID
    - Patrones de Diseño
    - Metodo de desarrollo BDD

## Documentacion y Recursos

[Expresiones Regulares](https://regex101.com/)

[Repositorio Maven](https://mvnrepository.com/search?q=org.springframework/)

[Git Ignore](https://www.toptal.com/developers/gitignore/)

[Diseño de Api](https://learn.microsoft.com/es-es/azure/architecture/microservices/design/api-design)

[JIRA](https://jayway-peru-devs.atlassian.net/browse/JD-14)

[Git Flow](https://www.youtube.com/watch?v=3Fo2QRHuYDA)

[Open csv](https://www.baeldung.com/opencsv)