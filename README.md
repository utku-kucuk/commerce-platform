# Commerce Platform

An e-commerce backend built with Java 21 and Spring Boot 3.

> **Status: early stage / in progress.** The project currently contains the application skeleton and the first domain entities. No REST endpoints or business services are available yet.

## Tech stack

- Java 21
- Spring Boot 3 (Web, Actuator)
- Spring Data JPA / Hibernate
- H2 (in-memory database)
- Lombok
- Maven (wrapper included)

## Current domain model

Located in `com.utkukucuk.commerceplatform.entity`:

| Type          | Kind       | Notes                                                          |
| ------------- | ---------- | -------------------------------------------------------------- |
| `User`        | JPA entity | Name, email, phone, role, one-to-one `Address`, audit timestamps |
| `Address`     | JPA entity | Street, city, state, country, zip code, audit timestamps       |
| `UserRole`    | Enum       | `CUSTOMER`, `ADMIN`                                            |
| `OrderStatus` | Enum       | `PENDING`, `CONFIRMED`, `SHIPPED`, `DELIVERED`, `CANCELLED`    |
| `Product`     | Placeholder | Not yet mapped                                                |

## Getting started

Requirements: JDK 21+.

```bash
./mvnw spring-boot:run
```

The application starts on `http://localhost:8080` with an in-memory H2 database. The Actuator health endpoint is available at `/actuator/health`.

Run the tests:

```bash
./mvnw test
```

## Roadmap

- [ ] User module: repository, service and REST API
- [ ] Product catalog service
- [ ] Shopping cart
- [ ] Order service with status lifecycle
- [ ] JWT-based authentication and authorization
- [ ] Integration tests with Testcontainers
- [ ] Order events with Kafka
- [ ] Docker Compose setup for local development
- [ ] CI pipeline
