# Library Management System

## Overview
This is a RESTful API-based Library Management System built using Spring Boot. It manages books, users, and the issuance and return of books in a library setting. The system supports multiple roles, such as Admin, Librarian, and User, with specific permissions for each role.

## Features
- **Books Management**: Add, update, delete, and view books.
- **User Management**: Sign up users, generate OTPs, and manage user roles.
- **Book Issuance**: Issue books to users and handle returns.
- **Role-Based Access Control**: Ensure that only Admin and Librarian roles can perform specific actions.

## Technologies Used
- **Java**: Core language used for development.
- **Spring Boot**: Framework used for creating the REST API.
- **MySQL**: Database used for storing data.
- **Maven**: Build and dependency management tool.
- **Tomcat**: Embedded server for running the application.

## Prerequisites
Before you begin, ensure you have the following installed:
- **Java**: JDK 11 or higher.
- **Maven**: Version 3.6.3 or higher.
- **MySQL**: Version 8.0 or higher.
- **IDE**: Eclipse or any other preferred Java IDE.
- **Postman**: For testing API endpoints.

## Setup and Installation

### Clone the Repository
```bash
git clone https://github.com/your-username/library-management-system.git

Configure Database 
--------------------

1. Create the Database
Run Script from schema/create_dms_library_management_springboot.sql

2. Create the Tables
Run scripts from Below files 
schema/books_details.sql
schema/books_to_user.sql
schema/user_details.sql
schema/user_otp_requests.sql
schema/user_tokens.sql

Configure Application Properties
------------------------------------
Edit src/main/resources/application.properties to include:

spring.datasource.url=jdbc:mysql://localhost:3306/library_db
spring.datasource.username=root
spring.datasource.password=your_password

Build the project:
-------------------
Use Maven to build the project.
mvn clean install

Run the application:
---------------------
mvn spring-boot:run

Access the application:
-----------------------
The application will be running at http://localhost:8080.

API Endpoints
--------------
1. Book Management:
Get Book by ID: GET /library-management/books/v1/{id}
Find Books: GET /library-management/books/v1
Create Book: POST /library-management/books/v1
Update Book: PUT /library-management/books/v1/{bookId}
Delete Book: DELETE /library-management/books/v1/{bookId}
Issue Book: POST /library-management/books/v1/issue/{bookId}
Return Book: POST /library-management/books/v1/return/{bookId}

2. User Management:
Sign Up: POST /user-management/signup
Generate New OTP: POST /user-management/new-otp
Get User Details: GET /user-management/user-details
Role-Based Access Control
ADMIN: Can perform all operations.
LIBRARIAN: Can manage books and issue/return books.
USER: Can view book details and their own issued books.

Postman API Testing :
-------------------
For testing the API endpoints, a Postman collection is provided. Below are the details of the collection:

Collection Name :
BookLibraryWithUser

Endpoints Covered in the Collection .

Error Handling :
---------------
The system uses custom exceptions to handle various error scenarios, such as invalid roles, missing tokens, and non-existent books.