🔐 Authentication System

A secure user authentication system developed using Java, Spring Boot, Spring Security, Spring Data JPA, and MySQL.

This project provides user registration, encrypted password storage, login authentication, session management, protected user access, and logout functionality.

🚀 Features
User Registration
BCrypt password encryption
Secure Login Authentication
Session Management
Protected Profile API
Logout and Session Invalidation
MySQL Database Integration
Spring Data JPA
Spring Security
Password hidden from API responses
🛠️ Technologies Used
Java 17
Spring Boot
Spring Security
Spring Data JPA
Hibernate
MySQL
Maven
REST APIs
Postman
BCrypt
📁 Project Structure
authentication-system
│
├── src
│   └── main
│       ├── java
│       │   └── com.example.authentication_system
│       │       ├── config
│       │       │   └── SecurityConfig.java
│       │       │
│       │       ├── controller
│       │       │   └── AuthController.java
│       │       │
│       │       ├── dto
│       │       │   └── LoginRequest.java
│       │       │
│       │       ├── entity
│       │       │   └── User.java
│       │       │
│       │       ├── repository
│       │       │   └── UserRepository.java
│       │       │
│       │       └── service
│       │           ├── UserService.java
│       │           └── CustomUserDetailsService.java
│       │
│       └── resources
│           └── application.properties
│
├── pom.xml
└── README.md
🔗 API Endpoints
1. Register User

POST

/api/auth/register

Request:

{
    "username": "sakshi",
    "email": "sakshi@gmail.com",
    "password": "password123"
}

The password is encrypted using BCrypt before being stored in the database.

2. Login

POST

/api/auth/login

Request:

{
    "username": "sakshi",
    "password": "password123"
}

Response:

Login successful

A session is created after successful authentication.

3. Get Profile

GET

/api/auth/profile

Response:

Welcome sakshi

This endpoint is protected and requires an authenticated session.

4. Logout

POST

/api/auth/logout

Logout invalidates the active session and clears the session cookie.

After logout, accessing the protected profile endpoint is no longer allowed.

🔐 Security

Passwords are never stored as plain text.

Example database value:

$2a$10$...

The application uses BCryptPasswordEncoder to securely hash passwords.

Spring Security is also used to authenticate users and protect secured endpoints.

🗄️ Database Configuration

Create a MySQL database:

CREATE DATABASE authentication_system;

Configure the database connection in:

src/main/resources/application.properties

Example:

spring.datasource.url=jdbc:mysql://localhost:3306/authentication_system
spring.datasource.username=root
spring.datasource.password=YOUR_PASSWORD

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true

Important: Do not upload your real MySQL password to GitHub.

🧪 API Testing

The APIs were tested using Postman.

Tested flow:

Register
   ↓
Password encrypted in database
   ↓
Login
   ↓
Session created
   ↓
Access protected profile
   ↓
Logout
   ↓
Session invalidated
   ↓
Protected profile inaccessible
📌 Project Objective

The objective of this project is to implement a secure authentication system with password encryption and session management using Spring Boot and Spring Security.

👩‍💻 Author

Sakshi Dudhe

GitHub: https://github.com/Dudhesakshi

LinkedIn: https://www.linkedin.com/in/sakshi-dudhe/
