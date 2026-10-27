# Enterprise-Book-Management-Service

### Project Overview
A Spring Boot RESTful API connected to MySQL implementing full CRUD operations for library books, integrated with Hibernate/JPA, Bean Validation, and OpenAPI 3 / Swagger UI documentation.

### Tech Stack
- **Java:** JDK 21+
- **Framework:** Spring Boot 3.4.3
- **ORM / Persistence:** Spring Data JPA / Hibernate
- **Database:** MySQL 8.0 (`library_db`)
- **Documentation:** springdoc-openapi (Swagger UI)
- **Validation:** Jakarta Validation (`@NotBlank`, `@PositiveOrZero`)
- **Testing:** Postman

### REST Endpoints
| HTTP Method | Endpoint | Description | Status Code |
|-------------|----------|-------------|-------------|
| `GET` | `/api/books` | List all books | `200 OK` |
| `GET` | `/api/books/{id}` | Get book by ID | `200 OK` / `404 Not Found` |
| `POST` | `/api/books` | Create a new book | `201 Created` / `400 Bad Request` |
| `PUT` | `/api/books/{id}` | Update existing book | `200 OK` / `404 Not Found` |
| `DELETE` | `/api/books/{id}` | Delete book by ID | `204 No Content` / `404 Not Found` |

### API Documentation (Swagger UI)
When the application is running:
- Swagger UI: `http://localhost:8080/swagger-ui.html`
- OpenAPI JSON: `http://localhost:8080/v3/api-docs`

### How to Run Locally
1. Ensure MySQL Server is running with database `library_db`.
2. Configure credentials in `src/main/resources/application.properties`.
3. Run the application:
   ```bash
   mvn spring-boot:run
   ```
   or using the Maven wrapper:
   ```bash
   ./mvnw spring-boot:run
   ```
