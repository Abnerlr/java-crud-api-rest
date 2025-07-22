# APIREST - Simple CRUD with Spring Boot, Hibernate & PostgreSQL

This project is a basic RESTful API that demonstrates a **CRUD (Create, Read, Update, Delete)** functionality for a `Producto` entity using:

- Java 21+
- Spring Boot
- Hibernate (JPA)
- PostgreSQL

---

## Project Structure

```
APIREST/
├── src/
│   ├── main/
│   │   └── java/com/abner/apirest/
│   │       ├── Controllers/
│   │       │   └── ProductoController.java
│   │       ├── Entities/
│   │       │   └── Producto.java
│   │       ├── Repositories/
│   │       │   └── ProductoRepository.java
│   │       └── ApirestApplication.java
│   └── resources/
│       └── application.properties
├── docker-compose.yml
├── .env
├── pom.xml
```

---

## Setup Instructions

### 1. Prerequisites

- Java 17+
- Maven
- PostgreSQL running locally or in Docker

### 2. Configure Database

Edit `src/main/resources/application.properties`:

```properties
spring.datasource.url=jdbc:postgresql://localhost:5432/apirest_db
spring.datasource.username=your_db_user
spring.datasource.password=your_db_password
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
```

Or use the `.env` file if running with Docker.

---

## Run the Application

```bash
# Option 1: Local run
mvn spring-boot:run

# Option 2: Dockerized PostgreSQL (if using docker-compose.yml)
docker-compose up -d
```

---

## API Endpoints

All endpoints are available under:  
`http://localhost:8080/api/productos`

| Method | Endpoint                    | Description            |
|--------|-----------------------------|------------------------|
| GET    | `/api/productos`            | Get all products       |
| GET    | `/api/productos/{id}`       | Get product by ID      |
| POST   | `/api/productos`            | Create a new product   |
| PUT    | `/api/productos/{id}`       | Update product by ID   |
| DELETE | `/api/productos/{id}`       | Delete product by ID   |

---

## Technologies Used

- Spring Boot (Web, JPA)
- Hibernate
- PostgreSQL
- Docker (optional)
- Maven

---

## Testing the API

You can use tools like:

- [Postman](https://www.postman.com/)
- [Insomnia](https://insomnia.rest/)
- `curl` in the terminal

Example:

```bash
curl -X POST http://localhost:8080/api/productos \
-H "Content-Type: application/json" \
-d '{"nombre": "Camiseta", "precio": 15.99}'
```

---

## License

This project is open-source and free to use under the MIT License.
