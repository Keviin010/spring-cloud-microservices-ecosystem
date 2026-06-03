# Arquitectura de Microservicios con Spring Boot y Spring Cloud

Este proyecto es un sistema distribuido que armé usando Spring Boot 3 y Spring Cloud para entender y aplicar cómo se comunican los servicios en la nube.

## Estructura del proyecto

El ecosistema está dividido en dos partes principales:

* **msvc-gateway-server (Eureka Server):** Es el servidor de descubrimiento. Se encarga de registrar todos los microservicios automáticos para que se puedan encontrar entre sí sin necesidad de configurar IPs o puertos a mano.
* **msvc-items (Microservicio Cliente):** Es el servicio que maneja la lógica de negocio y consume datos. Se conecta usando OpenFeign y WebClient, y tiene balanceo de carga automático del lado del cliente con Spring Cloud LoadBalancer.

## Tecnologías

* Java 21
* Spring Boot 3
* Spring Cloud Netflix Eureka
* Spring Cloud LoadBalancer
* OpenFeign y WebClient

## Cómo correrlo en local

### Requisitos
* JDK 21
* Maven

### Orden para levantarlo
Para que todo enganche bien, hay que iniciarlos en este orden:

1. Primero levanta **msvc-gateway-server**. Cuando esté activo, puedes entrar al panel de Eureka en el navegador.
2. Después levanta **msvc-items**, que se va a registrar solo en el servidor de Eureka al arrancar.
