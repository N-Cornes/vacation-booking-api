# Vacation Booking API

A Java and Spring Boot backend for managing vacation packages, excursions, customers, shopping carts, and checkout workflows through RESTful services backed by MySQL.

## Tech Stack

- Java 17
- Spring Boot
- Spring Data JPA
- Spring Data REST
- Hibernate
- MySQL
- Maven
- Lombok
- REST APIs

## Core Features

- REST-based access to vacation booking data
- Customer management
- Vacation package management
- Excursion management
- Country and division data relationships
- Shopping cart workflow
- Checkout processing
- Order-status updates
- Unique tracking-number generation
- MySQL persistence through JPA repositories

## Domain Model

The backend models several related booking entities, including:

- Customer
- Vacation
- Excursion
- Cart
- Country
- Division

The application uses Spring Data JPA repositories to manage persistence and expose REST-oriented data access.

## API Structure

Spring Data REST is configured under the `/api` base path.

A dedicated checkout endpoint handles purchase processing:

```text
POST /api/checkout/purchase
```

The checkout workflow validates the incoming purchase data, associates the cart with the customer, marks the cart as ordered, generates a unique tracking number, and persists the completed booking information.

## Checkout Flow

```text
Client Purchase Request
        ↓
Checkout Controller
        ↓
Purchase Validation
        ↓
Customer + Cart Association
        ↓
Cart Status = ordered
        ↓
UUID Tracking Number Generated
        ↓
JPA Persistence
        ↓
MySQL Database
```

## Data Initialization

The application includes startup logic for loading sample customer data while avoiding duplicate records. The initialization process also handles missing date values when needed so existing records remain usable.

## Architecture

```text
REST Client
    ↓
Spring REST / Controller Layer
    ↓
Business Logic
    ↓
Spring Data JPA Repositories
    ↓
Hibernate
    ↓
MySQL
```

## Technical Highlights

This project demonstrates backend API development with entity relationships, relational persistence, repository-driven data access, checkout business logic, request validation, and transactional-style order processing.

## Source Code

The original implementation is maintained in a private repository. Source access can be provided for professional review upon request.

## Author

**Nicholas Cornes**  
B.S. Software Engineering
