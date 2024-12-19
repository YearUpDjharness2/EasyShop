# EasyShop Backend API

EasyShop is an e-commerce application backend built using Java, Spring Boot, and MySQL. This project represents the second version of the EasyShop backend API, focusing on fixing existing bugs and implementing new features.

## Features

- **API Functionality:** Manage user authentication, product data, shopping cart, and order processing.
- **Database Integration:** Utilizes a MySQL database for persistent data storage, with a provided `create_database.sql` script to set up the database schema and seed data.
- **Authentication:** Implements JWT for secure user authentication.
- **Starter Code:** Includes the backend API and a sample front-end application for testing.

## Getting Started

### Prerequisites
- Java Development Kit (JDK)
- MySQL Database Server
- Postman (or any API testing tool)
- Git

### Setup Instructions
1. Clone the repository into your working directory:
   ```bash
   git clone <repository-url>
   cd <project-folder>
   ```
2. Set up the MySQL database:
   - Import the `create_database.sql` script into MySQL Workbench and execute it to create the `easyshop` database.
   - The database includes several products and three demo users:
     - **Admin:** Username: `admin`, Password: `password`
     - **Users:** Username: `user`, Password: `password` | Username: `george`, Password: `password`
3. Run the application:
   ```bash
   ./mvnw spring-boot:run
   ```
4. Use Postman or the sample front-end to test API endpoints.

### Authentication Endpoints
- **Register a New User:**
   ```http
   POST http://localhost:8080/register
   ```
   Request Body:
   ```json
   {
      "username": "admin",
      "password": "password",
      "confirmPassword": "password",
      "role": "ADMIN"
   }
   ```
- **Login:**
   ```http
   POST http://localhost:8080/login
   ```
   Request Body:
   ```json
   {
      "username": "admin",
      "password": "password"
   }
   ```
   Response:
   - A JWT token will be returned, which must be used for subsequent authenticated requests.

## Project Details

### Bugs
The current API includes some bugs that need to be identified and resolved. Debugging and unit testing are recommended to address these issues before implementing new features.

### New Features
You are tasked with:
1. Developing new functionalities for the EasyShop API.
2. Testing and validating the new features with comprehensive test cases.

### Technologies Used
- **Backend:** Java, Spring Boot
- **Database:** MySQL
- **Testing:** Postman, JUnit
###
## Phase 1 - CategoriesController
  The task involves implementing a RESTful API for managing categories in an e-commerce application. The CategoriesController class needs to be completed with methods for creating, reading, updating, and deleting categories. The underlying data access layer, MySQLCategoriesDao, needs to be implemented to interact with the database. Security measures should be in place to ensure only authorized users can perform CRUD operations. The API should adhere to REST principles and handle errors gracefully.
###
### Phase 2 - Fix Bugs
 BUG 1.)
 The task involves fixing a bug in the `ProductsController` that is causing incorrect results in the product search functionality. To resolve this, we need to:

1. **Analyze the Code:** Review the code for the search functionality, checking for errors in SQL queries, data inconsistencies, or incorrect parameter handling.
2. **Write Test Cases:** Create unit and integration tests to cover different search scenarios and identify the root cause of the issue.
3. **Debug the SQL Queries:** If the issue lies in the SQL queries, use a database tool to execute them manually and inspect the results.
4. **Optimize Database Performance:** Consider adding indexes to frequently searched columns to improve query performance.
5. **Fix the Bug:** Once the root cause is identified, make the necessary code changes to correct the issue.
6. **Retest:** Re-run the tests to ensure that the fix has resolved the problem.

By following these steps, we can effectively debug and fix the issue with the product search functionality.

### BUG 2.) 

 The second bug, duplicate products, arises when updating a product multiple times, leading to the creation of new, nearly identical products instead of updating the original one. To address this, we need to:

Review Update Logic: Ensure that the update mechanism correctly identifies the existing product and modifies its attributes without creating a new one.
Implement Unique Constraints: Add unique constraints on relevant columns (e.g., product name, SKU) to prevent duplicate entries.
Consider Database Triggers: Use database triggers to enforce data integrity and prevent duplicate insertions.
Thorough Testing: Write comprehensive unit tests to cover various update scenarios and validate the correctness of the update logic.
By carefully analyzing the code and database, and by implementing these solutions, we can effectively prevent duplicate products and ensure data integrity.

## Contributing
Feel free to fork the repository, make improvements, and submit a pull request.

---

