# Proyecto RSD300012: CRUD Básico con Relación One-to-One (Bidirectional) en JPA/Hibernate

## Resumen del Proyecto

Este proyecto académico, enmarcado en el nivel Trainee de desarrollo con Spring Framework, sirve como una introducción práctica a la persistencia de datos en Java utilizando Spring Data JPA y Hibernate. El objetivo principal es implementar un sistema de Create, Read, Update, Delete (CRUD) para dos entidades, `Usuario` y `Perfil`, que se encuentran vinculadas por una relación `One-to-One` bidireccional. A través de este ejercicio, se exploran conceptos fundamentales de mapeo objeto-relacional (ORM), gestión de transacciones y la configuración de una base de datos Postgres v15 dentro de un ecosistema Spring Boot. La lógica de negocio se ejecuta mediante un `CommandLineRunner`, permitiendo una demostración clara y concisa de las operaciones de persistencia al iniciar la aplicación.


## 1. Introducción

La persistencia de datos es un pilar fundamental en el desarrollo de aplicaciones modernas. Spring Boot, en conjunto con Spring Data JPA, simplifica enormemente la interacción con bases de datos relacionales al abstraer gran parte del código repetitivo (boilerplate) asociado a JDBC o implementaciones JPA nativas.

Este proyecto se centra en el mapeo de una relación `One-to-One`, uno de los tipos de asociación más comunes. Se establece una correspondencia unívoca entre un `Usuario` y su `Perfil`. La bidireccionalidad de la relación implica que se puede navegar desde el `Usuario` a su `Perfil` y viceversa, manteniendo la consistencia del modelo de datos a través de la configuración de un "lado propietario" de la relación.

## 2. Fundamentos Teóricos

### 2.1. JPA (Jakarta Persistence API)
JPA es una especificación estándar de Java para el mapeo objeto-relacional (ORM) que define una API para gestionar datos relacionales en aplicaciones Java. Proporciona una abstracción sobre JDBC, permitiendo a los desarrolladores trabajar con objetos Java en lugar de sentencias SQL directas.

**Conceptos clave:**
- **Entity:** Clase Java anotada con `@Entity` que representa una tabla en la base de datos
- **Persistence Context:** Entorno gestionado donde las entidades son almacenadas y administradas
- **Entity Manager:** Interfaz principal para interactuar con el persistence context

### 2.2. Hibernate
Hibernate es la implementación más popular de JPA, proporcionando características adicionales más allá de la especificación JPA. Actúa como framework ORM que maneja la conversión automática entre objetos Java y registros de base de datos.

**Características principales:**
- Mapeo objeto-relacional transparente
- Consultas mediante HQL (Hibernate Query Language)
- Caching de primer y segundo nivel
- Generación automática de esquemas

### 2.3. Spring Data JPA
Spring Data JPA es parte del ecosistema Spring Data que simplifica el desarrollo de repositorios JPA. Reduce la cantidad de código boilerplate necesario para implementar operaciones de datos.

**Ventajas:**
- Generación automática de implementaciones de repositorio
- Soporte para métodos de consulta derivados
- Integración con características Spring (transacciones, etc.)
- Paginación y ordenación integradas

### 2.4. Relaciones JPA
Las relaciones en JPA definen cómo las entidades se conectan entre sí:

**Tipos de relaciones:**
- `@OneToOne`: Una entidad se relaciona exactamente con una instancia de otra entidad
- `@OneToMany` / `@ManyToOne`: Relaciones uno-a-muchos o muchos-a-uno
- `@ManyToMany`: Relaciones muchos-a-muchos

**Configuraciones importantes:**
- **Lado propietario:** Donde se define la clave foránea
- **Fetch Type:** EAGER (carga inmediata) vs LAZY (carga perezosa)
- **Cascade:** Define qué operaciones se propagan a entidades relacionadas
- **Orphan Removal:** Eliminación automática de entidades huérfanas

## 3. Pila Tecnológica

El desarrollo se sustenta en un conjunto de tecnologías modernas y estándares de la industria:

-   **Framework Principal:** Spring Boot 4.0.0
-   **Lenguaje de Programación:** Java 25
-   **Gestor de Dependencias:** Apache Maven
-   **Persistencia de Datos:** Spring Data JPA
-   **Implementación ORM:** Hibernate 6.4+
-   **Base de Datos:** Postgres v15
-   **Utilidades:** Project Lombok (para reducción de código boilerplate)