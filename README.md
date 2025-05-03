
# Airbnb Clone Project

This is a full-stack clone of the Airbnb platform, designed to replicate key features including property listings, bookings, user accounts, payments, and reviews.

# project goals

-User Management: Implement a secure system for user registration, authentication, and profile management.

-Property Management: Develop features for property listing creation, updates, and retrieval.

-Booking System: Create a booking mechanism for users to reserve properties and manage booking details.

-Payment Processing: Integrate a payment system to handle transactions and record payment details.

-Review System: Allow users to leave reviews and ratings for properties.

-Data Optimization: Ensure efficient data retrieval and storage through database optimizations.

# Team Roles

-Backend Developer: Responsible for implementing API endpoints, database schemas, and business logic.

-Database Administrator: Manages database design, indexing, and optimizations.

-DevOps Engineer: Handles deployment, monitoring, and scaling of the backend services.

-QA Engineer: Ensures the backend functionalities are thoroughly tested and meet quality standards.
# Technology Stack

-Django: A high-level Python web framework used for building the RESTful API.

-Django REST Framework: Provides tools for creating and managing RESTful APIs.

-PostgreSQL: A powerful relational database used for data storage.

-GraphQL: Allows for flexible and efficient querying of data.

-Celery: For handling asynchronous tasks such as sending notifications or processing payments.

-Redis: Used for caching and session management.

-Docker: Containerization tool for consistent development and deployment environments.

-CI/CD Pipelines: Automated pipelines for testing and deploying code changes.

# 🗃️ Database Design

The database schema for this project is designed to support core Airbnb functionality, with a focus on scalability, normalization, and efficient data relationships.

## 🔑 Key Entities & Fields

### 1. **User**
Represents individuals using the platform as guests or hosts.
- `id`: Unique identifier (Primary Key)
- `name`: Full name of the user
- `email`: User’s email address (unique)
- `password`: Hashed password
- `role`: Host or Guest

### 2. **Property**
Represents a rental listing created by a host.
- `id`: Unique identifier
- `title`: Name/title of the property
- `description`: Detailed description
- `location`: Address or coordinates
- `price_per_night`: Cost of one night stay
- `host_id`: Foreign key linking to the User (host)

### 3. **Booking**
Represents a reservation made by a guest.
- `id`: Unique identifier
- `user_id`: Foreign key to the User (guest)
- `property_id`: Foreign key to the Property
- `start_date`: Check-in date
- `end_date`: Check-out date
- `total_price`: Calculated total for the booking

### 4. **Review**
Represents a review left by a guest after a stay.
- `id`: Unique identifier
- `user_id`: Reviewer (guest)
- `property_id`: Property being reviewed
- `rating`: Numerical rating (1-5)
- `comment`: Text feedback

### 5. **Payment**
Represents a payment transaction for a booking.
- `id`: Unique identifier
- `booking_id`: Foreign key to the Booking
- `amount`: Payment amount
- `payment_method`: Credit card, PayPal, etc.
- `payment_status`: Pending, Completed, Failed

## 🔗 Entity Relationships

- A **User** can be a **host** or a **guest**.
- A **User** (host) can have multiple **Properties**.
- A **User** (guest) can make multiple **Bookings**.
- A **Booking** is linked to one **Property** and one **User**.
- A **Review** belongs to a **Property** and is written by a **User**.
- A **Payment** is associated with one **Booking**.


