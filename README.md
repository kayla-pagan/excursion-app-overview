# excursion-app-overview

This project is a full-stack vacation booking platform with a Java Spring Boot backend, a MySQL database, and an Angular frontend. The platform allows customers to browse vacation packages, add excursions to their cart, and proceed to checkout. The backend is built with Java and Spring Boot to manage the business logic and handle communication between the frontend and the database.

Note: This repository does not contain the actual project code, as the code is proprietary and maintained privately. This README serves to document the project features, functionality, and my contributions for reference.

## Key Components
1. Entities  
Entities represent the tables in the MySQL database. I created individual entity classes for each table (e.g., Vacation, Excursion, Customer, Cart, etc.). Each entity is mapped to a corresponding table in the database, and relationships between these entities were defined using annotations.

For example:

One-to-Many relationship between Vacation and Excursion.
Many-to-One relationship between Cart and Customer.
By setting these relationships, the database structure reflects the associations between vacations, excursions, customers, and their carts.

2. Data Access Objects (DAOs)  
For each entity, I created a corresponding Data Access Object (DAO) file. The DAOs extend Spring Data JPA's JpaRepository interface to provide CRUD operations for each entity without requiring much boilerplate code.

Examples of DAO files include:

VacationRepository
ExcursionRepository
CustomerRepository
CartRepository

3. DTOs (Data Transfer Objects)  
DTOs are used to pass data between different layers of the application, particularly between the frontend and backend. I created DTOs for:

Purchaset: Captures the data when a customer checks out a vacation package with selected excursions.
PurchaseResponse: Provides feedback to the frontend about the success or failure of the purchase process.

4. Services  
The service layer contains the business logic of the application. I implemented two key services:

CheckoutService: This service manages the logic behind the purchase process when a customer adds a vacation and its excursions to their cart.
CheckoutServiceImpl: The implementation of the CheckoutService that handles tasks such as validating the cart, calculating total costs, and saving purchase details in the database.
