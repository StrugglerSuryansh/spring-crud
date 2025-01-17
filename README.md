﻿# spring-crud
# Spring Boot PostgreSQL CRUD Application

This project is a basic CRUD (Create, Read, Update, Delete) application built with Spring Boot and PostgreSQL.

## Prerequisites

- Java JDK 11 or later
- Maven
- PostgreSQL

## Setup

1. Clone the repository:
   ```
   git clone https://github.com/yourusername/crud-demo.git
   cd crud-demo
   ```

2. Create a PostgreSQL database:
   ```
   psql -U postgres
   CREATE DATABASE cruddemo;
   \q
   ```

3. Update `src/main/resources/application.properties` with your PostgreSQL credentials:
   ```
   spring.datasource.url=jdbc:postgresql://localhost:5432/cruddemo
   spring.datasource.username=your_username
   spring.datasource.password=your_password
   ```

4. Build the project:
   ```
   mvn clean install
   ```

5. Run the application:
   ```
   mvn spring-boot:run
   ```

The application should now be running on `http://localhost:8080`.

## API Endpoints

- GET `/api/items`: Retrieve all items
- POST `/api/items`: Create a new item
- GET `/api/items/{id}`: Retrieve a specific item by ID
- PUT `/api/items/{id}`: Update an item
- DELETE `/api/items/{id}`: Delete an item

## Usage Example

To create a new item:

```bash
curl -X POST -H "Content-Type: application/json" -d '{"name":"Example Item","description":"This is an example item"}' http://localhost:8080/api/items
```

To retrieve all items:

```bash
curl http://localhost:8080/api/items
```

## Project Structure

```
src
├── main
│   ├── java
│   │   └── com
│   │       └── example
│   │           └── cruddemo
│   │               ├── CrudDemoApplication.java
│   │               ├── controller
│   │               │   └── ItemController.java
│   │               ├── model
│   │               │   └── Item.java
│   │               └── repository
│   │                   └── ItemRepository.java
│   └── resources
│       └── application.properties
```

## Contributing

Please feel free to submit issues and pull requests.

## License

This project is open source and available under the [MIT License](LICENSE).
