
# Microservice Airline Booking System

This project is a microservice-based airline booking system that simplifies the process of managing flights, bookings, and notifications. The architecture ensures modularity, scalability, and maintainability. Each service is designed to handle a specific aspect of the airline booking workflow, communicating seamlessly via REST APIs and message queues.

----------

## Features

-   **Modular Services**: Each service is independently deployable and manageable.
-   **API Gateway**: A unified entry point for client requests, ensuring efficient routing.
-   **Database Interaction**: Uses Sequelize ORM for efficient database management.
-   **Messaging Queue**: RabbitMQ for asynchronous communication between services.

----------

## Project Structure

### Services

1.  **Api-Gateway**:
    
    -   Acts as the entry point for all client requests.
    -   Routes requests to the appropriate service.
2.  **FlightNotification**:
    
    -   Handles sending notifications related to flight bookings.
    -   Manages email, SMS, or app notifications.
3.  **Flights-Booking**:
    
    -   Manages booking workflows including creating, updating, and canceling bookings.
    -   Integrates payment functionality.
4.  **Flights-Service**:
    
    -   Handles flight data such as schedules, details, and seat availability.
    -   Updates and retrieves flight information.

----------

## Tech Stack

-   **Backend**: Node.js, Express.js
-   **Database**: Sequelize (ORM for relational databases like MySQL or PostgreSQL)
-   **Messaging**: RabbitMQ (for asynchronous communication)

----------

## API Endpoints

### **Api-Gateway**

Method

Endpoint

Description

POST

`/api/v1/flights`

Create a new flight.

GET

`/api/v1/flights`

Retrieve all flights.

GET

`/api/v1/flights/:id`

Get a specific flight by ID.

PATCH

`/api/v1/flights/:id/seats`

Update seat availability for a flight.

----------

### **Flights-Booking**

Method

Endpoint

Description

POST

`/api/v1/bookings`

Create a new booking.

POST

`/api/v1/bookings/payment`

Make a payment for a booking.

PATCH

`/api/v1/bookings/:id/cancel`

Cancel a booking.

----------

### **FlightNotification**

Method

Endpoint

Description

POST

`/api/v1/notifications`

Send a notification.

----------

## Folder Structure

### Core Folders

-   **`controllers/`**:  
    Handles incoming requests, passes data to the business layer, and structures API responses.
    
-   **`repositories/`**:  
    Contains logic for database interaction, including query management.
    
-   **`services/`**:  
    Handles business logic, processes data from repositories, and manages workflows.
    
-   **`utils/`**:  
    Contains helper methods, custom error classes, and other utility functions.
    

----------

## Installation and Setup

### Prerequisites

-   **Node.js** (v14 or later)
-   **RabbitMQ**
-   **Database**: MySQL/PostgreSQL

### Steps

1.  Clone the repository:
    
    bash
    
    Copy code
    
    `git clone https://github.com/your-repo/microservice-airline-booking.git
    cd microservice-airline-booking` 
    
2.  Install dependencies for each service:
    
    bash
    
    Copy code
    
    `cd api-gateway
    npm install
    cd ../flights-booking
    npm install

   
----------

## How It Works

1.  **Flight Management**:
    
    -   Create, retrieve, and manage flight details.
    -   Update seat availability dynamically.
2.  **Booking Management**:
    
    -   Handles user bookings and cancellations.
    -   Integrates with payment gateways for seamless transactions.
3.  **Notifications**:
    
    -   Asynchronous notifications for booking confirmations or updates via RabbitMQ.
4.  **API Gateway**:
    
    -   Ensures a streamlined client experience by routing requests to relevant services.
