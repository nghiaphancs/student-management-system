# Student Management System

A student management application built with Spring Boot, Thymeleaf, and PostgreSQL. The project provides a web interface for viewing, searching, creating, updating, and deleting students, along with REST APIs for basic CRUD operations.

## Tech Stack

- Java 21
- Spring Boot 4
- Spring MVC
- Spring Data JPA / Hibernate
- Thymeleaf
- PostgreSQL
- Maven
- Docker

## Main Features

- Display the student list
- Search students by name
- View student details
- Add new students
- Update student information
- Delete students
- Manage students through REST APIs
- Highlight students under 18 years old in the list view

## Project Structure

```text
src/main/java/vn/edu/hcmut/cse/adse/lab
+-- controller
|   +-- DashboardController.java
|   +-- StudentController.java
|   +-- StudentWebController.java
+-- entity
|   +-- Student.java
+-- repository
|   +-- StudentRepository.java
+-- service
    +-- StudentService.java

src/main/resources
+-- application.properties
+-- templates
    +-- student-detail.html
    +-- student-form.html
    +-- students.html
```

## Database Configuration

The application uses PostgreSQL. Configure the database connection in `src/main/resources/application.properties`:

```properties
spring.datasource.url=${DATABASE_URL}
spring.datasource.username=${DB_USERNAME}
spring.datasource.password=${DB_PASSWORD}
spring.datasource.driver-class-name=org.postgresql.Driver

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.PostgreSQLDialect
```

## Run Locally

### Run with Maven

```bash
./mvnw spring-boot:run
```

On Windows:

```bash
mvnw.cmd spring-boot:run
```

After the application starts, open:

```text
http://localhost:8080/students
```

### Run with Docker

```bash
docker build -t student-management .
docker run -p 8080:8080 student-management
```

Then open:

```text
http://localhost:8080/students
```

## REST API

| Method | Endpoint             | Description              |
|--------|----------------------|--------------------------|
| GET    | `/api/students`      | Get all students         |
| GET    | `/api/students/{id}` | Get a student by ID      |
| POST   | `/api/students`      | Create a new student     |
| PUT    | `/api/students/{id}` | Update a student         |
| DELETE | `/api/students/{id}` | Delete a student         |

Example request body for creating a student:

```json
{
  "id": "2312001",
  "name": "Nguyen Van A",
  "email": "vana@example.com",
  "age": 20
}
```

## Screenshots

### Student List

![Student List](screenshots/students.png)

### Student Details

![Detail View](screenshots/student-detail.png)

### Add and Edit Student

![Add & Edit](screenshots/add-edit.png)
