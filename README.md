# Login_authentication_using_SpringBoot_h2
## Project Setup and Documentation
To set up and run the project, please follow the instructions below:

Navigate to the project directory:
```
cd spring-boot-security-login-jwt
```

Build the project using Maven:
```
mvn clean install
```

Run the project:
```
mvn spring-boot:run
```

The backend API will now be accessible at http://localhost:8080.

Configuration
Configure the H2 database connection in src/main/resources/application.properties:
```
spring.datasource.url=jdbc:h2:mem:testdb
spring.datasource.username=sa
spring.datasource.password=
spring.h2.console.enabled=true
spring.h2.console.path=/h2-console
```

Configure JWT properties in src/main/resources/application.properties:
```
jwt.secret=your-secret-key
jwt.expirationMs=86400000
```

jwt.secret: The secret key used for signing JWT tokens.
jwt.expirationMs: The expiration time for JWT tokens (in milliseconds).


# Endpoints
The following endpoints are available in the API:

**Registration: POST /api/register**

Register a new user with the provided username and password.
Request body:
```
{
  "username": "your-username",
  "password": "your-password"
}
```

**Login: POST /api/login**

Generate a JWT token for the authenticated user.
Request body:
```
{
  "username": "your-username",
  "password": "your-password"
}
```

**Logout: POST /api/logout**
Invalidate the JWT token and remove it from the client.

**User Info: GET /api/user**
Get the information of the authenticated user.

## Database
The project uses the H2 in-memory database for storing user account information. The database schema is automatically created based on the data models defined in the code.

### Dependencies
The project has the following dependencies:

1. Spring Boot: Framework for creating standalone, production-grade applications.
2.  Security: Provides authentication and authorization capabilities.
3. Spring Data JPA: Simplifies database access using the Java Persistence API.
4. H2 Database: In-memory database for storing user account information securely.
5. JSON Web Tokens (JWT): Library for generating and verifying web tokens.
6. Maven: Build and dependency management tool.


Ensure that you have these dependencies installed and configured properly before running the project.

## Directory Structure

The project follows a standard Spring Boot directory structure:
```
├── src
│   ├── main
│   │   ├── java
│   │   │   └── com
│   │   │       └── example
│   │   │           └── security
│   │   │               ├── config              // Security configurations
│   │   │               ├── controller          // API controllers
│   │   │               ├── dto                 // Data Transfer Objects
│   │   │               ├── model               // Entity models
│   │   │               ├── repository          // Data access components
│   │   │               ├── security            // Security components
│   │   │               └── service             // Business logic services
│   │   └── resources
│   │       ├── application.properties          // Application configuration
│   │       ├── data.sql                        // Initial database data
│   │       └── schema.sql                      // Database schema
│   └── test                                    // Unit and integration tests
└── pom.xml                                     // Maven project configuration
```
Please refer to the source code for detailed implementation and documentation of each component.

**Error Handling and Validation**
The code is designed to handle errors and perform validation where necessary. Proper exception handling is implemented, and input data is validated to ensure data integrity and security.

**License**
This project is licensed under the MIT License. Feel free to modify and use it for your own purposes.

**References**
Spring Boot Documentation
Spring Security Documentation
JSON Web Tokens (JWT) Introduction
H2 Database Documentation





