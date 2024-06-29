# Spring enviroment for Final Degree Project
The Final Degree Project (TFG) focuses on the design and implementation of a microservices-based system to develop a web application for creating virtual assistants trained with private knowledge.

The database of this project stores information about individuals, who have associated chats. These chats are trained using files, so it is necessary to keep track of the files associated with each chat. Additionally, as expected, there is a conversation between the user and the assistant, so the messages in each chat are stored.

For data persistence, a Spring environment (Spring Data JPA) has been created, where a REST API is implemented with a security layer through an authentication process.

The system mainly includes an API Gateway (Spring Cloud Gateway) that functions as a Load Balancer and applies a security filter. When a request arrives, the API Gateway redirects it to the desired microservice and applies the authentication filter.

This authentication filter is based on the JWT standard, with a microservice that registers users and creates and validates tokens. Therefore, before redirecting the request to another microservice, the API Gateway validates the JWT with the identity microservice (Spring Security).

Finally, a service registry is used via Netflix Eureka Client, where each microservice in the environment registers to facilitate communication and coordination among them.

## Component Repositories

Spring Data JPA (APIREST): https://github.com/nachtlz/docugeniedb

Spring Security (Identity Service): https://github.com/nachtlz/identity-service

Spring Cloud Gateway (API Gateway): https://github.com/nachtlz/docugenie-gateway

Spring Eureka Client (Service registry): https://github.com/nachtlz/docugenie-service-registry

![Data](https://github.com/nachtlz/TFG-SpringEnviroment/assets/62239934/530062d6-839d-4d81-b9d6-a927abd313b9)
