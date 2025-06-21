# airbnb-clone-project


![Airbnb Logo](https://upload.wikimedia.org/wikipedia/commons/6/69/Airbnb_Logo_Bélo.svg)

##  Project Overview

This is a backend clone of the Airbnb web application. The goal of the project is to understand and implement backend components of a full-stack web application including file storage, database management, RESTful APIs, authentication, and deployment. The backend project provides robust and scalabe management of user interactions, property listings, bookings, and payments. This project is designed by ensuring smooth experience of users in mind.

## Project Goals

- User Management: Implement a secure system for user registration, authentication, and profile management.
- Property Management: Develop features for property listing creation, updates, and retrieval.
- Booking System: Create a booking mechanism for users to reserve properties and manage booking details.
- Payment Processing: Integrate a payment system to handle transactions and record payment details.
- Review System: Allow users to leave reviews and ratings for properties.
- Data Optimization: Ensure efficient data retrieval and storage through database optimizations.

## Technology Stack

- Django: A high-level Python web framework used for building the RESTful API.
- Django REST Framework: Provides tools for creating and managing RESTful APIs.
- PostgreSQL: A powerful relational database used for data storage.
- GraphQL: Allows for flexible and efficient querying of data.
- Celery: For handling asynchronous tasks such as sending notifications or processing payments.
- Redis: Used for caching and session management.
- Docker: Containerization tool for consistent development and deployment environments.
- CI/CD Pipelines: Automated pipelines for testing and deploying code changes.

## Team Roles

- Backend Developer: Responsible for implementing API endpoints, database schemas, and business logic.
- Database Administrator: Manages database design, indexing, and optimizations.
- DevOps Engineer: Handles deployment, monitoring, and scaling of the backend services.
- QA Engineer: Ensures the backend functionalities are thoroughly tested and meet quality standards.
- Test automation Engineer: designs a test automation ecosystem, writes and maintains test scripts for automated testing.

## Database Design

### Key Entities and Fields

1. User : Represents people who use the platform (guests and hosts)
   - id
   - email
   - password
   - first_name
   - last_name
   - created_at
   - updated_at
2. Properties : Represents a listed property or space
   - id
   - user_id
   - created_at
3. City:
   - id
   - state_id
   - name
4. State:
   - id
   - name
5. Amenity: Represents a facility or service (e.g., Wi-Fi, TV)
   - id
   - name 
6. Review: Represents feedback from users about a place
   - id
   - user_id
   - palce_id
   - text
   - created_at

### Entity relationships

- A User can own multiple Places.
- A Place belongs to one City, and a City belongs to a State.
- A Place can have many Amenities (many-to-many).
- A User can write many Reviews on Places.
- A Place can have many Reviews.

## Feature breakdown

1. API Documentation
- OpenAPI Standard: All backend APIs are documented using the OpenAPI (Swagger) standard for clarity, consistency, and ease of client-side integration.
- Django REST Framework (DRF): A powerful and flexible toolkit for building Web APIs, used to provide RESTful endpoints for user and property data.
- GraphQL Support: Enables efficient, flexible data querying with reduced over-fetching compared to REST.

2.  User Authentication
- Endpoints:
   - POST /users/ – Register new users
   - GET/PUT/DELETE /users/{user_id}/ – Retrieve, update, or delete user profiles
- Features:
   - User registration and login
   - Token-based authentication
   - Profile management

3. Property Management
- Endpoints:
   - GET/POST /properties/ – List or create new property listings
   - GET/PUT/DELETE /properties/{property_id}/ – Retrieve, update, or delete a specific property
- Features:
   - Add new property listings
   - Update property information
   - Delete inactive or invalid listings

4. 📅 Booking System
- Endpoints:
   - GET/POST /bookings/ – View or create a new booking
   - GET/PUT/DELETE /bookings/{booking_id}/ – Manage individual bookings
- Features:
   - Book a property for specific dates
   - Update or cancel bookings
   - Manage check-in/check-out details

5. 💳 Payment Processing
- Endpoints:
   - POST /payments/ – Process a new payment transaction
- Features:
   - Handle secure payments for bookings
   - Integrate with payment gateways (e.g., Stripe or PayPal)

6. Review System
- Endpoints:
   - GET/POST /reviews/ – Submit or view reviews
   - GET/PUT/DELETE /reviews/{review_id}/ – Manage specific reviews
- Features:
   - Users can leave reviews for properties
   - Edit or delete past reviews
   - Ensure authenticity and transparency

 7. Database Optimizations
- Indexing: Strategic indexes applied to frequently queried fields (e.g., user ID, property location) to enhance database read speed.
- Caching: Use of caching layers (e.g., Redis) to store frequently accessed data and reduce database load, improving overall performance and response time.

