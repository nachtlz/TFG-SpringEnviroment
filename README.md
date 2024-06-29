# Entorno Spring para el TFG
El Trabajo de Fin de Grado (TFG) se centra en el diseño e implementación de un sistema basado en microservicios para desarrollar una aplicación web destinada a la creación de asistentes virtuales entrenados con conocimiento privado.

La base de datos de este proyecto almacena información de personas, quienes tienen asociados chats. Estos chats se entrenan utilizando archivos, por lo que es necesario mantener un registro de los archivos asociados a cada chat. Además, como es natural, entre el usuario y el asistente se produce una conversación, por lo que se guardan los mensajes de cada chat.

Para la persistencia de los datos, se ha creado un entorno Spring (Spring Data JPA), donde se implementa una API REST con una capa de seguridad mediante un proceso de autenticación.

El sistema cuenta principalmente con una API Gateway (Spring Cloud Gateway) que funciona como un Load Balancer y aplica un filtro de seguridad. Cuando llega una petición, la API Gateway la redirige al microservicio correspondiente y aplica el filtro de autenticación.

Este filtro de autenticación se basa en el estándar JWT, utilizando un microservicio que registra usuarios y crea y valida los tokens. Por lo tanto, antes de redirigir la petición a otro microservicio, la API Gateway valida el JWT con el microservicio de identidad (Spring Security).

Finalmente, se utiliza un registro de servicios mediante Netflix Eureka Client, donde cada microservicio del entorno se registra para facilitar la comunicación y coordinación entre ellos.

## Componentes
```
Spring Data JPA (APIREST): https://github.com/nachtlz/docugeniedb

Spring Security (Identity Service): https://github.com/nachtlz/identity-service

Spring Cloud Gateway (API Gateway): https://github.com/nachtlz/docugenie-gateway

Spring Eureka Client (Service registry): https://github.com/nachtlz/docugenie-service-registry
```
