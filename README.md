# Spring Boot MongoDB Demo Project

## Overview

This project is a Spring Boot application that demonstrates the integration of MongoDB. It includes authentication using Spring Security, CRUD operations, and transactional consistency.

## Features Implemented

 ### 1. Spring Boot Core Concepts

Dependency Injection and IoC

Use of @Component, @Service, @Repository, and @RestController

Managing configurations via application.properties

### 2. Database Integration

MongoDB (NoSQL Database)

Integrated with MongoDB Atlas using spring.data.mongodb.uri

Created collections (users, demoEntries)

Used @Document to define MongoDB documents

Used @DBRef for referencing related documents

Implemented MongoTransactionManager to maintain consistency

MySQL (SQL Database)

Configured MySQL database using spring.datasource.* properties

Used Hibernate ORM for persistence

Applied spring.jpa.hibernate.ddl-auto=update for schema management

 ### 3. Spring Security (Authentication & Authorization)

Implemented UserDetailsService for authentication

Used BCryptPasswordEncoder for secure password hashing

Configured security rules in SecurityFilterChain:

/public/** - Accessible by all

/demo/** and /user/** - Requires authentication

/admin/** - Requires ADMIN role

Disabled CSRF protection for simplicity

### 4. REST API Development

User & DemoEntry CRUD Operations

Implemented RESTful endpoints for:

Creating, retrieving, updating, and deleting DemoEntry

Fetching all user entries

Authentication-based access control

Used @RequestMapping, @GetMapping, @PostMapping, @PutMapping, and @DeleteMapping

Used ResponseEntity for proper HTTP status responses

### 5. Service & Repository Layer

Service Layer: Business logic is handled separately in DemoEntryService and UserService

Repository Layer: Used MongoRepository to interact with MongoDB

### 6. Weather API Integration

Implemented WeatherResponse model to handle external API responses

Utilized RestTemplate to fetch weather data from an external service

Used @JsonProperty to map JSON properties to Java fields

### 7. Testing (JUnit & Mockito)

Implemented unit tests for UserService using JUnit 5

Created UserArgumentProvider to supply test data dynamically

Used @Transactional in tests to maintain database consistency




## Setup & Run Instructions

### 1. Clone the Repository

git clone https://github.com/sangwanseema/SpringBootDemoMongoDB.git
cd SpringBootDemoMongoDB

### 2. Configure Databases

Update application.properties with your MongoDB Atlas 
 ### 3 Run the Application

 mvn spring-boot:run

The server will start on http://localhost:8080.

### 4. API Endpoints
##### GET --> /demo/health
Health check

##### GET --> /demo/getAll
Get all user entries

##### POST --> /demo/create
Create a new entry

##### GET --> /demo/getById/{id}
Get entry by ID

##### DELETE -->  /demo/deleteById/{id}
Delete entry

##### PUT-->  /demo/updateById/{id}
Update entry

#####  GET --> /user/health
User health check

##### GET --> /user/
Get all users

##### GET --> /user/getUser
Get authenticated user with weather info

##### DELETE --> /user/deleteUser
Delete authenticated user

##### PUT --> /user/updateUser
Update authenticated user


### Learnings & Challenges

Spring Security: Learned how to secure endpoints with roles & permissions.

MongoDB Transactions: Faced issues maintaining consistency, solved using @Transactional.

Ingerating Mongodb with springboot 

Unit Testing: Learned to write parameterized tests using ArgumentsProvider.


 ### Future Enhancements

Implement JWT-based authentication

Improve exception handling and logging

Add Swagger for API documentation
