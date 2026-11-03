# Enterprise-Book-Management-Service

### Project Overview
A Spring Boot RESTful API connected to MySQL implementing full CRUD operations for library books, integrated with Hibernate/JPA, Bean Validation, and OpenAPI 3 / Swagger UI documentation, fully containerised with Docker and orchestrated using Docker Compose.

### Tech Stack
- **Java:** JDK 21+
- **Framework:** Spring Boot 3.4.3
- **ORM / Persistence:** Spring Data JPA / Hibernate
- **Database:** MySQL 8.4 (`library_db`)
- **Containerisation:** Docker & Docker Compose
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

### How to Run with Docker Compose (Recommended)
1. Copy `.env.example` to `.env`:
   ```bash
   cp .env.example .env
   ```
2. Build and start the containers in detached mode:
   ```bash
   docker compose up --build -d
   ```
3. Check status:
   ```bash
   docker compose ps
   ```
4. View application logs:
   ```bash
   docker compose logs api
   ```
5. Stop services (preserving data volume):
   ```bash
   docker compose down
   ```

### How to Run Locally (Without Docker)
1. Ensure MySQL Server is running with database `library_db`.
2. Configure credentials in `src/main/resources/application.properties`.
3. Run the application:
   ```bash
   ./mvnw spring-boot:run
   ```
