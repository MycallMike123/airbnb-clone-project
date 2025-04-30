This mis my project on developing a backed clone for airbnb

## 👥 Team Roles

- **Backend Developer**: Implements the API, handles database schemas, and builds core logic.
- **Database Administrator**: Designs and optimizes the database.
- **DevOps Engineer**: Manages deployment, CI/CD, and scaling.
- **QA Engineer**: Tests all features and ensures quality standards.

## ⚙️ Technology Stack

- **Django**: A high-level Python web framework used for building the backend and RESTful APIs.
- **Django REST Framework**: A powerful toolkit for building Web APIs in Django.
- **PostgreSQL**: A reliable and robust relational database system used for storing application data.
- **GraphQL**: A flexible query language for efficiently retrieving and updating data from the backend.
- **Celery**: A task queue used for handling asynchronous tasks such as background jobs and notifications.
- **Redis**: An in-memory data store used for caching and managing sessions.
- **Docker**: Used to containerize the application for consistent development and deployment across environments.
- **CI/CD Pipelines**: Automated systems for continuously testing and deploying code changes.

## 🗃️ Database Design

### Entities & Fields

**1. Users**
- `id`: Unique identifier for each user
- `username`: User’s display name
- `email`: User’s email address
- `password`: Hashed password for authentication
- `is_host`: Boolean to identify if the user is a host

**2. Properties**
- `id`: Unique identifier for the property
- `user_id`: Foreign key linking to the host (User)
- `title`: Title of the listing
- `description`: Detailed description of the property
- `location`: Address or geographic location

**3. Bookings**
- `id`: Unique booking ID
- `user_id`: Foreign key linking to the guest (User)
- `property_id`: Foreign key linking to the Property
- `start_date`: Check-in date
- `end_date`: Check-out date

**4. Reviews**
- `id`: Unique identifier for the review
- `user_id`: Foreign key to the reviewer (User)
- `property_id`: Foreign key to the reviewed Property
- `rating`: Numeric score (e.g., 1–5)
- `comment`: Text feedback

**5. Payments**
- `id`: Unique identifier for the payment
- `booking_id`: Foreign key linking to the Booking
- `amount`: Total payment amount
- `payment_date`: Timestamp of the transaction
- `status`: Status of the payment (e.g., completed, failed)

### Entity Relationships

- A **User** can create multiple **Properties**.
- A **User** can make multiple **Bookings**.
- A **Property** can have many **Bookings**.
- A **Booking** has one associated **Payment**.
- A **Property** can have multiple **Reviews**.
- A **Review** is written by a **User** for a **Property**.
